# Auto-Persistence Patterns v2.0.0

> Dynamic session folder naming with automatic result saving after each phase execution.

---

## Overview

The auto-persistence system v2.0.0 captures Memory Bus state after each tier completes, enabling:

- **Session isolation** - Each research task has its own folder
- **No overwrites** - Historical sessions preserved
- **Content-based naming** - Folders named after research topic
- **Session recovery** - Resume from any phase
- **Quality audit trail** - Full history maintained
- **Evolution learning** - Cross-session pattern analysis

---

## What's New in v2.0.0

| Feature | v1.1.0 | v2.0.0 |
|---------|--------|--------|
| Storage | Flat folder | Dynamic session folders |
| Naming | Fixed filenames | `{date}_{topic}` folders |
| Overwrites | ✅ Yes | ❌ No |
| Session History | Lost | Preserved |
| Metadata | None | `session-metadata.json` |

---

## Dynamic Session Folder Architecture

```
PhaseOutputs/
├── 2026-01-31_ai_in_education_2024_2026/
│   ├── session-metadata.json
│   ├── phase-01-query.json
│   ├── phase-02-strategy.json
│   ├── phase-03-search.json
│   ├── phase-04-extraction.json
│   ├── phase-05-reading.json
│   ├── phase-06-analysis.json
│   ├── phase-07-validation.json
│   └── phase-08-report.json
├── 2026-01-30_llm_progress_analysis/
│   └── ...
├── 2026-01-29_climate_change_policy/
│   └── ...
└── _legacy/
    └── (archived v1.x flat files)
```

---

## Persistence Flow

```mermaid
flowchart TD
    A[Session Start] --> B[Tier 1 Execution]
    B --> C[Generate Session Folder]
    C --> D[Create: PhaseOutputs/{date}_{topic}/]
    D --> E[Save phase-01-query.json]
    E --> F{More Tiers?}
    F -->|Yes| G[Execute Next Tier]
    G --> H[Save Phase Output to Session Folder]
    H --> F
    F -->|No| I[Session Complete]
    I --> J[Create session-metadata.json]
    J --> K[Done]
```

---

## Session Folder Generation

### Trigger

Session folder is generated **after Tier 1 completes**, using the `research_topic` from the query phase.

### Slug Generation Rules

1. Extract `research_topic` from Memory Bus
2. Convert to lowercase
3. Replace spaces with underscores `_`
4. Remove special characters (keep `a-z`, `0-9`, `_`)
5. Collapse multiple underscores
6. Truncate to 50 characters
7. Prepend date: `{YYYY-MM-DD}_`

### Examples

| Input Topic | Output Folder |
|-------------|---------------|
| AI in Education (2024-2026) | `2026-01-31_ai_in_education_2024_2026` |
| LLM Progress: Recent Advances | `2026-01-30_llm_progress_recent_advances` |
| Climate Change & Policy Analysis | `2026-01-29_climate_change_policy_analysis` |

---

## Phase Output Schema

Each phase output file follows this structure:

```json
{
    "phase": "phase-01-query",
    "name": "Query Processing",
    "timestamp": "2026-01-31T12:40:00+07:00",
    "session_folder": "2026-01-31_ai_in_education_2024_2026",
    "workforce_version": "2.0.0",
    "duration_ms": 1500,
    "memory_snapshot": {
        "query.clarified": {...},
        "query.domain": "Educational Technology"
    },
    "quality_metrics": {
        "completeness": 1.0,
        "errors": 0
    }
}
```

---

## Session Metadata Schema

Created after Tier 8 completes:

```json
{
    "session_folder": "2026-01-31_ai_in_education_2024_2026",
    "research_topic": "AI in Education (2024-2026)",
    "mode": "Deep",
    "started_at": "2026-01-31T12:40:00+07:00",
    "completed_at": "2026-01-31T13:15:00+07:00",
    "duration_minutes": 35,
    "total_phases": 8,
    "phases_completed": ["tier_1", "tier_2", "tier_3", "tier_4", "tier_5", "tier_6", "tier_7", "tier_8"],
    "quality_score": 0.92,
    "workforce_version": "2.0.0",
    "efficiency_metrics": {
        "avg_phase_duration_ms": 2625,
        "total_tokens_used": 125000,
        "cache_hit_rate": 0.75
    }
}
```

---

## Hook Implementations

### Session Folder Generation Hook

```python
def generate_session_folder(memory_bus, config):
    """Generate session folder name from research topic after Tier 1."""
    import re
    import os
    from datetime import datetime
    
    # Extract topic from memory bus
    topic = memory_bus.get('research_topic') or \
            memory_bus.get('query.clarified') or \
            memory_bus.get('query.original') or \
            f"session_{int(datetime.now().timestamp())}"
    
    # Generate slug
    slug = topic.lower()
    slug = slug.replace(' ', '_')
    slug = re.sub(r'[^a-z0-9_]', '', slug)
    slug = re.sub(r'_+', '_', slug)
    slug = slug[:config['session_naming']['slug_rules']['max_length']]
    slug = slug.strip('_')
    
    # Add date prefix
    date_prefix = datetime.now().strftime('%Y-%m-%d')
    session_folder = f"{date_prefix}_{slug}"
    
    # Handle collision
    base_folder = session_folder
    counter = 2
    output_path = config['storage_path'].replace('{session_folder}/', '')
    full_path = os.path.join(output_path, session_folder)
    
    while os.path.exists(full_path):
        session_folder = f"{base_folder}_{counter:02d}"
        full_path = os.path.join(output_path, session_folder)
        counter += 1
        if counter > 99:
            session_folder = f"{base_folder}_{int(datetime.now().timestamp())}"
            full_path = os.path.join(output_path, session_folder)
            break
    
    # Create folder
    os.makedirs(full_path, exist_ok=True)
    
    # Store in memory bus for subsequent phases
    memory_bus['session.folder'] = session_folder
    memory_bus['session.path'] = full_path
    memory_bus['session.started_at'] = datetime.now().isoformat()
    
    return session_folder
```

### Phase Save Hook

```python
def after_tier_complete(tier_id, memory_bus, config):
    """Save phase output to session folder after each tier."""
    import json
    import os
    from datetime import datetime
    
    phase_config = config['phases'][f'tier_{tier_id}']
    if not phase_config.get('auto_save', True):
        return
    
    # Get session folder from memory bus
    session_folder = memory_bus.get('session.folder')
    if not session_folder:
        raise ValueError("Session folder not generated. Run Tier 1 first.")
    
    # Collect memory snapshot
    snapshot = {}
    for key in phase_config['memory_keys']:
        value = memory_bus.get(key)
        if value is not None:
            snapshot[key] = value
    
    # Build output path
    output_path = config['storage_path'].replace('{session_folder}', session_folder)
    output_file = os.path.join(output_path, phase_config['output_file'])
    
    # Write phase output
    phase_data = {
        "phase": phase_config['output_file'].replace('.json', ''),
        "name": phase_config['name'],
        "timestamp": datetime.now().isoformat(),
        "session_folder": session_folder,
        "workforce_version": "2.0.0",
        "memory_snapshot": snapshot,
        "quality_metrics": {
            "completeness": 1.0 if snapshot else 0.0,
            "keys_captured": len(snapshot)
        }
    }
    
    with open(output_file, 'w', encoding='utf-8') as f:
        json.dump(phase_data, f, indent=4, ensure_ascii=False)
    
    return output_file
```

### Session Metadata Hook

```python
def create_session_metadata(memory_bus, config):
    """Create session metadata after final tier completes."""
    import json
    import os
    from datetime import datetime
    
    session_folder = memory_bus.get('session.folder')
    session_path = memory_bus.get('session.path')
    started_at = memory_bus.get('session.started_at')
    
    metadata = {
        "session_folder": session_folder,
        "research_topic": memory_bus.get('research_topic', 'Unknown'),
        "mode": memory_bus.get('mode', 'Standard'),
        "started_at": started_at,
        "completed_at": datetime.now().isoformat(),
        "total_phases": 8,
        "quality_score": memory_bus.get('quality.score', 0.0),
        "workforce_version": "2.0.0"
    }
    
    metadata_file = os.path.join(session_path, 'session-metadata.json')
    with open(metadata_file, 'w', encoding='utf-8') as f:
        json.dump(metadata, f, indent=4, ensure_ascii=False)
    
    return metadata_file
```

---

## Recovery from Interruption

If a session is interrupted mid-execution:

1. **Detection**: List folders in `PhaseOutputs/`
2. **Identify**: Find session folder matching the research topic
3. **Check**: List phase files to find last completed tier
4. **Rehydration**: Restore memory bus from latest phase snapshot
5. **Resume**: Continue from next tier

```bash
# List available sessions
ls PhaseOutputs/

# Check a specific session
ls "PhaseOutputs/2026-01-31_ai_in_education_2024_2026/"

# Resume command
/recall 2026-01-31_ai_in_education_2024_2026 --resume
```

---

## Retention Policy

| Setting | Value | Description |
|---------|-------|-------------|
| `max_sessions` | 100 | Maximum saved sessions |
| `max_age_days` | 90 | Auto-delete after N days |
| `archive_after_days` | 30 | Compress sessions older than 30 days |
| `compress_old` | true | Enable compression |

---

## Migration from v1.x

Existing flat files in `PhaseOutputs/` should be moved to `_legacy/`:

```bash
mkdir PhaseOutputs/_legacy
mv PhaseOutputs/phase-*.json PhaseOutputs/_legacy/
```

---

*Auto-Persistence Patterns v2.0.0 | ScholarDeepResearch-Workforce*
