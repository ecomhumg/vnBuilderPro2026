---
always: false
tier: [1,2,3,4,5,6,7,8]
description: "Implement tier-based phase output saving with JSON serialization"
core_modules: [MemoryStore, AgentLoop]
---

# SKILL: Phase Output Persistence

> **Purpose**: Implement tier-based phase output saving with JSON serialization.

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Trigger** | After each tier completes |
| **Output** | `phase-{NN}-{tier-name}.json` |
| **Storage** | `PhaseOutputs/{session_folder}/` |

---

## Phase Output Schema

```json
{
    "$schema": "phase-output-v2.0.0",
    "phase": 1,
    "tier_name": "Query & Intelligence",
    "tier_label": "query",
    "workers_executed": [
        {
            "id": "W01",
            "name": "QueryClarificationWorker",
            "status": "completed",
            "duration_seconds": 45
        }
    ],
    "started_at": "2026-01-31T12:40:00+07:00",
    "completed_at": "2026-01-31T12:45:00+07:00",
    "duration_seconds": 300,
    "memory_snapshot": {
        "query.original": "...",
        "query.clarified": "...",
        "domain.classification": "..."
    },
    "quality_metrics": {
        "completeness": 0.95,
        "accuracy": 0.92,
        "tier_score": 0.93
    },
    "status": "completed",
    "errors": []
}
```

---

## Save Trigger Implementation

### After Each Tier

```python
def save_phase_output(tier_number: int, tier_name: str, session_folder: str):
    output = {
        "phase": tier_number,
        "tier_name": tier_name,
        "tier_label": tier_name.lower().replace(" ", "_"),
        "workers_executed": collect_worker_results(),
        "started_at": tier_start_time,
        "completed_at": datetime.now().isoformat(),
        "memory_snapshot": get_relevant_memory_keys(tier_number),
        "quality_metrics": calculate_tier_quality(),
        "status": "completed"
    }
    
    filename = f"phase-{tier_number:02d}-{output['tier_label']}.json"
    path = f"PhaseOutputs/{session_folder}/{filename}"
    
    with open(path, 'w') as f:
        json.dump(output, f, indent=2)
```

---

## Tier-to-File Mapping

| Tier | Tier Name | Output File |
|------|-----------|-------------|
| 1 | Query & Intelligence | `phase-01-query.json` |
| 2 | Search Strategy | `phase-02-strategy.json` |
| 3 | Search Acquisition | `phase-03-search.json` |
| 4 | Content Extraction | `phase-04-extraction.json` |
| 5 | Critical Reading | `phase-05-reading.json` |
| 6 | Analysis & Synthesis | `phase-06-analysis.json` |
| 7 | Quality Validation | `phase-07-validation.json` |
| 8 | Delivery & Evolution | `phase-08-report.json` |

---

## Memory Key Selection

Each phase saves relevant memory keys:

| Phase | Memory Keys Pattern |
|-------|---------------------|
| 1 | `query.*`, `input.*`, `domain.*` |
| 2 | `search.strategy`, `sources.*` |
| 3 | `results.*`, `papers.*` |
| 4 | `content.*`, `datasets.*` |
| 5 | `reading.*`, `analysis.*` |
| 6 | `synthesis.*`, `visuals.*` |
| 7 | `validation.*`, `quality.*` |
| 8 | `output.*`, `efficiency.*` |

---

## Recovery from Phase Outputs

```python
def recover_session(session_folder: str, from_phase: int = None):
    """Resume session from last completed phase."""
    phases = sorted(glob(f"PhaseOutputs/{session_folder}/phase-*.json"))
    
    if from_phase:
        last_phase = from_phase
    else:
        last_phase = len(phases)
    
    # Load last phase output
    with open(phases[last_phase - 1]) as f:
        last_output = json.load(f)
    
    # Restore memory state
    restore_memory_keys(last_output['memory_snapshot'])
    
    # Continue from next tier
    return last_phase + 1
```

---

*SKILL v2.0.0 | Phase Output Persistence | MASDesign-Workforce*
