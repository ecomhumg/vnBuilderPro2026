# Query Clarification Playbook

> **Query Analysis and Clarification Protocols**
> Based on user's query-clarifier agent specification

---

## Query Analysis Framework

### Systematic Analysis Criteria
1. **Ambiguity Detection**: Terms with multiple interpretations
2. **Scope Assessment**: Missing boundaries, timeframes, domains
3. **Objective Clarity**: Unclear goals or expected outcomes
4. **Specificity Level**: Too broad vs. appropriately focused

### Decision Thresholds
| Confidence | Action |
|------------|--------|
| > 0.8 | Proceed without clarification |
| 0.6 - 0.8 | Refine and proceed |
| < 0.6 | Request clarification |

---

## Clarification Question Design

### Question Types
- **Yes/No**: Quick disambiguation
- **Multiple Choice**: Constrained options
- **Open-ended**: Complex context gathering

### Best Practices
1. Limit to 1-3 critical questions
2. Explain why clarification matters
3. Offer sensible defaults when possible
4. Never overwhelm users

---

## Output Schema

```json
{
  "needs_clarification": boolean,
  "confidence_score": 0.0-1.0,
  "analysis": "Decision explanation",
  "questions": [{"question": "...", "type": "..."}],
  "refined_query": "Clarified version",
  "focus_areas": ["Area 1", "Area 2"]
}
```

---

*Query Clarification v1.0 | DeepResearch-Workforce*
