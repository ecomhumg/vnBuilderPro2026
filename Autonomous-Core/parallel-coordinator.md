# Parallel Coordinator

> **{WorkforceName}-Workforce** | Autonomous-Core
> **Standard**: vnBuilderProMax v2.3.3

---

## Purpose

Coordinate parallel worker execution with barrier synchronization.

---

## Parallel Modes

| Mode | Description | Tiers |
|------|-------------|-------|
| `full_parallel` | All workers run simultaneously | T2 |
| `partial_parallel` | Most parallel, one aggregator | T3 |
| `barrier_sync` | All must complete before next | T4 |

---

## Coordination Protocol

```yaml
full_parallel:
  start: Fork all workers
  sync: Wait for all complete
  merge: Combine outputs

partial_parallel:
  phase_1: Fork content workers (W09-W13)
  phase_2: Wait for all complete
  phase_3: Activate aggregator (W14)
  merge: Aggregated output

barrier_sync:
  start: Fork all analysis workers
  barrier: Atomic completion gate
  proceed: Only after all pass
```

---

## Resource Management

| Resource | Limit | Allocation |
|----------|-------|------------|
| Workers | 6 max | Dynamic |
| Memory | 100MB | Per worker |
| Timeout | 60min | Per tier |

---

*parallel-coordinator.md | Autonomous-Core | v2.3.3*
