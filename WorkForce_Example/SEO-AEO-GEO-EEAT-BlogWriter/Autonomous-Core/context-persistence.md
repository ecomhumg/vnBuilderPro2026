# Context Persistence - Execution State Management

> **SEO-AEO-GEO-EEAT-BlogWriter** | Autonomous-Core | vnBuilderProMax v2.3.3

---

## Core Identity

| Attribute | Value |
|-----------|-------|
| **Type** | L5 Context Manager |
| **Trigger** | Phase boundaries + on-demand |
| **Auto-Execute** | Yes |
| **Retention** | 30 days (configurable) |

---

## Storage Locations

```
Memory/
├── ExecutionLogs/                    # Full session logs
│   ├── [SESSION-ID].json
│   └── index.json
├── ContextSnapshots/                 # Phase-level snapshots
│   └── [SESSION-ID]/
│       ├── phase-0-bootstrap.json
│       ├── phase-1-strategy.json
│       ├── phase-2-intel.json
│       ├── phase-3-content.json
│       ├── phase-4-analysis.json
│       ├── phase-5-validation.json
│       └── phase-6-synthesis.json
```

---

## Execution Logic

### Save Context (Auto-triggered)

```
ON Phase_Complete(phase_num):
    
    1. COLLECT current memory bus state
    
    2. GENERATE snapshot = {
        session_id: current_session,
        phase: phase_num,
        timestamp: now(),
        memory_state: filtered_bus_keys,
        worker_outputs: tier_outputs,
        quality_metrics: current_metrics
    }
    
    3. WRITE to ContextSnapshots/{session_id}/phase-{phase_num}.json
    
    4. IF phase_num == 6:
        a. AGGREGATE all phase snapshots
        b. WRITE full ExecutionLog to ExecutionLogs/{session_id}.json
        c. UPDATE index.json
```

### Load Context (On-demand)

```
ON /load-context [session_id]:
    
    1. READ ExecutionLogs/{session_id}.json
    
    2. RESTORE memory bus state
    
    3. SET current_phase = last_completed_phase + 1
    
    4. NOTIFY orchestrator: "Context restored, resuming from Phase {n}"
    
    5. RETURN restored state summary
```

### Save Full Context on Task Complete (Auto-triggered)

> [!IMPORTANT]
> As of v2.3.3, this trigger is **ALWAYS executed** on task completion.

```
ON Task_Complete:
    
    1. CALL /save-context --full
    
    2. WRITE final snapshot with ALL memory bus keys
    
    3. UPDATE index.json with completion status = "COMPLETE"
    
    4. LOG to DailyLogs with "TASK_COMPLETE" marker
    
    5. RETURN confirmation: {
        status: "saved",
        session_id: current_session,
        path: "Memory/ExecutionLogs/{session_id}.json",
        memory_keys_saved: count(all_keys),
        marker: "TASK_COMPLETE"
    }
```

---

## Execution Log Schema

```json
{
  "session_id": "2026-02-05-051400",
  "topic": "Texas Employment Law Guide",
  "started_at": "2026-02-05T05:14:00Z",
  "completed_at": "2026-02-05T05:48:00Z",
  "duration_minutes": 34,
  "phases": {
    "phase_0": {"status": "complete", "duration": 12},
    "phase_1": {"status": "complete", "duration": 180},
    "phase_2": {"status": "complete", "duration": 420},
    "phase_3": {"status": "complete", "duration": 900},
    "phase_4": {"status": "complete", "duration": 300},
    "phase_5": {"status": "complete", "duration": 180},
    "phase_6": {"status": "complete", "duration": 120}
  },
  "memory_snapshot": {
    "strategy.brief.topic": "...",
    "content.integrated.final": "...",
    "validation.compliance.certified": true
  },
  "quality_scores": {
    "seo_score": 92,
    "eeat_score": 90
  },
  "output_path": "Outputs/texas-employment-law-guide/2026-02-05-051400/"
}
```

---

## Context Snapshot Schema

```json
{
  "session_id": "2026-02-05-051400",
  "phase": 3,
  "phase_name": "Content Development",
  "timestamp": "2026-02-05T05:32:00Z",
  "tier": "T3",
  "workers_completed": ["W09", "W10", "W11", "W12", "W13", "W14"],
  "memory_keys": {
    "content.outline.structure": "...",
    "content.body.optimized": "...",
    "content.integrated.final": "..."
  },
  "next_phase": 4,
  "resumable": true
}
```

---

## Error Handling

| Error Type | Action |
|------------|--------|
| Write Failure | Retry (max 3) + in-memory fallback |
| Corrupt Snapshot | Skip + log warning |
| Missing Phase | Interpolate from adjacent phases |
| Index Update Fail | Rebuild index on next load |

---

## Memory Integration

### Write Keys

```
persist.context.session_id
persist.context.phase_current
persist.context.phase_snapshots[]
persist.context.execution_log
persist.context.resumable
```

### Commands

| Command | Function |
|---------|----------|
| `/save-context` | Manual context save |
| `/load-context [id]` | Restore from session |
| `/list-contexts` | List available sessions |

---

*context-persistence.md | Autonomous-Core | v2.3.3*
