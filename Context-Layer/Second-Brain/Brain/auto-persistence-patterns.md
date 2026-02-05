# Auto-Persistence Patterns v2.0.0

> **Purpose**: Template for implementing dynamic session folder persistence in generated workforces.

---

## Overview

This pattern enables generated workforces to automatically:

1. Create unique session folders for each task
2. Save phase outputs at tier completion
3. Generate session metadata summaries
4. Support session recovery and replay

---

## Configuration Template

Add to generated workforce's `swarm-router-config.json`:

```json
{
    "auto_persistence": {
        "enabled": true,
        "version": "2.0.0",
        "storage_path": "Context-Layer/Second-Brain/Memory/PhaseOutputs",
        "session_naming": {
            "format": "{date}_{topic_slug}",
            "max_length": 50,
            "sanitize": true
        },
        "phase_outputs": {
            "save_on_tier_complete": true,
            "include_memory_keys": true,
            "include_quality_score": true
        },
        "session_metadata": {
            "create_on_complete": true,
            "include_duration": true,
            "include_efficiency": true
        }
    }
}
```

---

## Session Folder Structure

```
PhaseOutputs/
├── {YYYY-MM-DD}_{topic_slug}/
│   ├── session-metadata.json
│   ├── phase-01-{tier1}.json
│   ├── phase-02-{tier2}.json
│   └── ... (up to phase-08)
└── _legacy/
```

---

## Integration Points

| Worker | Responsibility |
|--------|----------------|
| W01 | Extract topic, create session folder |
| W08-W20 | Save phase outputs after tier |
| W22 | Generate session-metadata.json |

---

## Memory Bus Keys

```
session.folder: string
session.topic: string
session.started_at: timestamp
session.mode: enum
phase.current: integer
phase.output.tier_N: object
```

---

*Auto-Persistence Patterns v2.0.0 | MASDesign-Workforce*
