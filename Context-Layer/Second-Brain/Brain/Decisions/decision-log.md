# Decision Log

> **Pattern Selection & Architecture Decision Audit Trail**

---

## Log Format

| Field | Description |
|-------|-------------|
| `timestamp` | ISO 8601 datetime |
| `decision_id` | Unique identifier |
| `decision_type` | pattern_selection, swarm_choice, etc. |
| `worker` | Originating worker |
| `input_context` | Relevant inputs |
| `options_considered` | Alternatives evaluated |
| `selected_option` | Final choice |
| `confidence` | 0.0-1.0 score |
| `rationale` | Explanation |
| `outcome` | Result (filled post-execution) |

---

## Recent Decisions

*No decisions logged yet. This file is populated during workforce execution.*

```json
{
  "decisions": []
}
```

---

*Decision Log v1.0 | MASDesign-Workforce*
