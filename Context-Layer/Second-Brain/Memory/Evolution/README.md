# Evolution Tracking README

> **MASDesign-Workforce | Evolution Data Management**

---

## Files

| File | Purpose |
|------|---------|
| `evolution-log.json` | Track MAS pattern evolution over time |
| `learned-patterns.json` | Store discovered design patterns |
| `behavior-policies.json` | Configure adaptive behavior rules |

---

## Usage

### Adding Evolution Entry

```json
{
  "entry_id": "UUID",
  "timestamp": "ISO8601",
  "type": "pattern|topology|prompt|memory_bus|quality",
  "trigger": "Description of what triggered evolution",
  "before": { },
  "after": { },
  "impact_metric": 0.0,
  "status": "proposed|testing|adopted|rejected"
}
```

### Adding Learned Pattern

```json
{
  "pattern_id": "UUID",
  "category": "swarm|topology|memory|orchestration|quality",
  "name": "Pattern name from 107-pattern library",
  "indicators": [],
  "usage_count": 0,
  "success_rate": 0.0,
  "recommended_context": "When to apply this pattern"
}
```

### Behavior Policy Schema

```json
{
  "policy_name": {
    "enabled": true,
    "threshold": 0.0,
    "parameters": { }
  }
}
```

---

## Evolution Categories

| Category | Description |
|----------|-------------|
| `pattern` | MAS pattern selection improvements |
| `topology` | Agent topology optimizations |
| `prompt` | L6 prompt engineering refinements |
| `memory_bus` | Cross-worker communication tuning |
| `quality` | Quality gate threshold adjustments |

---

*MASDesign-Workforce Evolution Tracking v1.0*
