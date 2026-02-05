# Decision Engine - Autonomous Logic

> **SEO-AEO-GEO-EEAT-BlogWriter** | Autonomous-Core | vnBuilderProMax v2.3.3

---

## Decision Framework

### L5 Autonomy Rules

1. **Default: Proceed** unless blocked by critical issue
2. **Auto-resolve** standard variations and minor gaps
3. **Flag-and-continue** for non-critical issues
4. **Escalate only** for compliance-blocking problems

---

## Decision Trees

### Quality Gate Decision

```
IF quality_score >= 90:
    → PASS (continue pipeline)
ELIF quality_score >= 70 AND content_type != YMYL:
    → PASS with FLAG
ELIF quality_score >= 85 AND content_type == YMYL:
    → PASS with FLAG
ELSE:
    → REMEDIATE (return to T3/T4)
```

### Error Decision

```
IF error_type == TIMEOUT:
    IF retry_count < 3:
        → RETRY with backoff
    ELSE:
        → ESCALATE
ELIF error_type == MISSING_INPUT:
    → REQUEST from upstream worker
ELIF error_type == VALIDATION_FAIL:
    IF critical:
        → HALT + ESCALATE
    ELSE:
        → FLAG + CONTINUE
```

---

## Confidence Thresholds

| Decision Type | Threshold | Action |
|---------------|-----------|--------|
| Auto-proceed | ≥90% | Execute |
| Proceed with flag | 70-89% | Execute + log |
| Seek clarification | 50-69% | Pause + request |
| Escalate | <50% | Halt + notify |

---

*decision-engine.md | Autonomous-Core | v2.3.3*
