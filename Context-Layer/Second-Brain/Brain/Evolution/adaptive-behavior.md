# Adaptive Behavior

> **Dynamic Behavior Adjustment Rules**

---

## Adaptation Triggers

| Trigger | Detection | Response |
|---------|-----------|----------|
| **Slow Performance** | Execution > 2x baseline | Reduce complexity |
| **Quality Drop** | Score < 0.75 | Increase validation |
| **High Error Rate** | Errors > 10% | Enable conservative mode |
| **Resource Pressure** | Memory > 85% | Prune context |

---

## Behavior Modes

| Mode | Description | Activation |
|------|-------------|------------|
| **Standard** | Default operation | Normal conditions |
| **Conservative** | Extra validation, careful | Detected issues |
| **Aggressive** | Parallel, fast | Time pressure |
| **Minimal** | Reduced features | Resource constraints |

---

## Mode Switching Rules

```python
def select_behavior_mode(context):
    if context.error_rate > 0.10:
        return "conservative"
    if context.time_remaining < context.time_expected * 0.5:
        return "aggressive"
    if context.memory_usage > 0.85:
        return "minimal"
    return "standard"
```

---

*Adaptive Behavior v1.0 | MASDesign-Workforce*
