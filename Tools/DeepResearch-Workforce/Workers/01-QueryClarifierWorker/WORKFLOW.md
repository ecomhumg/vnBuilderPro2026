# W01 QueryClarifierWorker WORKFLOW

> **Query Analysis and Clarification**
> Tier 1: Research & Intelligence | 24 Agents

---

## Mission
Analyze research queries for clarity, identify ambiguities, and refine queries into actionable research specifications.

## ROMA Pipeline

| Stage | Agents | Function |
|-------|--------|----------|
| Intake | 4 | Receive and parse query |
| Analysis | 4 | Detect ambiguity, assess scope |
| Refinement | 4 | Generate clarifications |
| Validation | 4 | Confirm query quality |
| Output | 4 | Produce refined query |
| Handoff | 4 | Transfer to Tier 2 |

## Decision Framework
- **Proceed** (confidence > 0.8): Clear query
- **Refine** (0.6-0.8): Minor clarification
- **Clarify** (< 0.6): User input needed

## Output
```json
{
  "needs_clarification": boolean,
  "confidence_score": 0.0-1.0,
  "refined_query": "...",
  "focus_areas": []
}
```

---

*W01 QueryClarifierWorker v1.0 | DeepResearch-Workforce*
