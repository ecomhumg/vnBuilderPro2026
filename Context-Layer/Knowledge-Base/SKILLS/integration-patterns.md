---
vnbuilder:
  name: integration-patterns
  description: Worker integration and coordination techniques
  version: "2.0.0"
  always: false
  tier: [6]
---

# Integration Patterns Skills

> **Worker Integration & Coordination Techniques**
> **CoreModules Integration**: SubagentManager coordination patterns

---

## Integration Types

| Type | Description | Use Case |
|------|-------------|----------|
| **Sequential** | A → B → C | Pipeline |
| **Parallel** | A, B, C (concurrent) | Independent tasks |
| **Fan-Out** | A → [B, C, D] | Distribution |
| **Fan-In** | [B, C, D] → A | Aggregation |
| **Hierarchical** | Parent → Children | Delegation |

---

## Handoff Patterns

### Direct Handoff

```
Worker A completes → writes to memory bus → Worker B triggers
```

### Aggregated Handoff

```
Workers A, B, C complete → Aggregator collects → Worker D triggers
```

### Conditional Handoff

```
Worker A completes → Router evaluates → Routes to B or C
```

---

## Error Handling

| Scenario | Strategy |
|----------|----------|
| Worker timeout | Retry with backoff |
| Quality failure | Re-process or escalate |
| Missing dependency | Wait with timeout |
| Circular dependency | Detect and break |

---

*Integration Patterns Skills v1.0 | MASDesign-Workforce*
