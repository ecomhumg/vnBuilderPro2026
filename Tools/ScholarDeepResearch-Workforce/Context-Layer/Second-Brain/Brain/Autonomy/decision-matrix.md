# Decision Matrix

> Routing logic for autonomous vs. supervised decisions.

## Decision Categories

### Category A: Full Autonomy

| Decision | Confidence Threshold | Fallback |
|----------|----------------------|----------|
| Database query execution | N/A | Retry with modified params |
| Domain classification | > 90% | Human review |
| Citation validation | 100% match | Flag for review |
| Deduplication | > 95% | Fuzzy matching |
| Critical reading method application | N/A | Apply all methods |

### Category B: Delegated with Sampling

| Decision | Sample Rate | Override Trigger |
|----------|-------------|------------------|
| Search result ranking | 10% random | Relevance score < 0.7 |
| Summary generation | 5% random | Quality score < 0.8 |
| Visualization selection | 15% random | User preference conflict |

### Category C: Human Required

| Decision | Escalation Path |
|----------|-----------------|
| Query clarification (ambiguous) | User |
| Conflicting evidence synthesis | Domain Expert |
| Report format selection | User |
| E-O score override | Quality Reviewer |

## Routing Logic

```python
def route_decision(decision_type, confidence, context):
    if decision_type in CATEGORY_A:
        if confidence >= threshold[decision_type]:
            return "AUTONOMOUS"
        return "HUMAN_REVIEW"
    
    if decision_type in CATEGORY_B:
        if random.random() < sample_rate[decision_type]:
            return "HUMAN_SAMPLE"
        return "AUTONOMOUS"
    
    return "HUMAN_REQUIRED"
```

---

*Decision Matrix v1.0.0 | ScholarDeepResearch-Workforce*
