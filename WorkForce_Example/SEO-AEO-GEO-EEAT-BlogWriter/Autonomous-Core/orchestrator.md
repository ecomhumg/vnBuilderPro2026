# Orchestrator - L5 Autonomous Control

> **SEO-AEO-GEO-EEAT-BlogWriter** | Autonomous-Core | vnBuilderProMax v2.3.3

---

## Core Identity

| Attribute | Value |
|-----------|-------|
| **Type** | L5 Autonomous Orchestrator |
| **Decision Authority** | 100% Self-Decision |
| **Escalation Threshold** | Critical only |
| **Retry Policy** | 3 attempts with backoff |

---

## Responsibilities

1. **Route Tasks**: Direct work to appropriate tiers/workers
2. **Sync Barriers**: Manage parallel execution sync points
3. **Handle Errors**: Retry, fallback, or escalate
4. **Track Progress**: Monitor phase completion
5. **Commit Memory**: Trigger memory logging
6. **Save Outputs**: Trigger output persistence (NEW)
7. **Persist Context**: Save execution snapshots (NEW)
8. **Trigger Learning**: Initiate pattern extraction (NEW)

---

## Routing Logic

```text
IF new_request:
    → Start Phase 0 (Bootstrap)
    → CALL context-persistence.load_previous() if resuming
    → Route to T1 (Strategy)

IF tier_complete(T1):
    → CALL context-persistence.snapshot(phase=1)
    → Parallel-launch T2 (Intelligence)

IF tier_complete(T2):
    → CALL context-persistence.snapshot(phase=2)
    → Partial-parallel T3 (Content)
    → Wait for W14 (Aggregator)

IF tier_complete(T3):
    → CALL context-persistence.snapshot(phase=3)
    → Parallel-launch T4 (Analysis)

IF tier_complete(T4):
    → CALL context-persistence.snapshot(phase=4)
    → Sequential T5 (Validation)

IF tier_complete(T5):
    → CALL context-persistence.snapshot(phase=5)
    → Sequential T6 (Synthesis)

IF tier_complete(T6):
    → CALL output-saver.save_all()
    → Trigger Phase 7 (Memory + Context)

IF phase_7_complete:
    → IF quality_score >= 85:
        → CALL self-improvement-loop.extract_patterns()
        → CALL self-improvement-loop.update_metrics()
    → CALL /save-context --full (ALWAYS - Task Completion Hook)
    → Return deliverables
```

---

## Task Completion Hooks

> [!IMPORTANT]
> As of v2.3.3, `/save-context --full` is **automatically executed** on every task completion.

| Hook | Trigger | Function |
|------|---------|----------|
| `/save-context --full` | Phase 7/8 complete | Save complete memory bus state |

**Rationale**: Ensures all execution context is preserved for session resumption, pattern extraction, and quality trend analysis regardless of quality score.

---

## Error Handling

| Error Type | Action |
|------------|--------|
| Timeout | Retry (max 3) |
| Missing Input | Request from prior worker |
| Validation Fail | Flag + Continue or Remediate |
| Save Fail | Retry + In-memory fallback |
| Critical Fail | Halt + Escalate to User |

---

## Component Integration

### output-saver.md

- **Trigger**: Phase 6 completion
- **Function**: Save all 7 deliverables to `Outputs/`
- **Returns**: `persist.output.path`, `persist.output.manifest`

### context-persistence.md

- **Trigger**: Phase boundaries (0-6)
- **Function**: Save execution context snapshots
- **Returns**: `persist.context.session_id`, `persist.context.phase_snapshots`

### self-improvement-loop.md

- **Trigger**: Phase 7 complete (if quality ≥ 85)
- **Function**: Extract patterns, update metrics, evolve weights
- **Returns**: `learning.patterns.*`, `evolution.*`

---

## Memory Integration

### Write Points

- End of each phase (context snapshot)
- Phase 6 (output save)
- Phase 7 (execution log)
- Phase 8 (learning patterns)
- On error/recovery

### Read Points

- Phase 0 context injection
- Phase 0 context restoration (if resuming)
- Pattern lookup during generation
- Quality baseline comparison

---

*orchestrator.md | Autonomous-Core | v2.3.3 Enhanced*
