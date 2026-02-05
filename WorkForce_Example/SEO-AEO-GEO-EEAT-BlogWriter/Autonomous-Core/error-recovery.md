# Error Recovery - Resilient Operation

> **SEO-AEO-GEO-EEAT-BlogWriter** | Autonomous-Core | vnBuilderProMax v2.3.3

---

## Recovery Strategies

### 3-Strike Protocol

| Strike | Action | Delay |
|--------|--------|-------|
| 1 | Retry with same parameters | 5s |
| 2 | Retry with adjusted parameters | 15s |
| 3 | Fallback or escalate | 30s |

---

## Error Categories

### Transient Errors (Auto-Retry)

- Timeout
- Rate limit
- Temporary unavailability

### Recoverable Errors (Adjust + Retry)

- Missing input (request from upstream)
- Format error (reformat + retry)
- Partial failure (retry failed portion)

### Critical Errors (Escalate)

- Missing required E-E-A-T signals (YMYL)
- Schema validation failure
- Compliance blocking issue

---

## Fallback Patterns

| Failure | Fallback |
|---------|----------|
| Keyword research timeout | Use provided keywords |
| Competitor analysis fail | Skip and continue |
| Schema validation fail | Regenerate schema |
| Voice check fail | Return for human review |

---

## Logging

All errors logged to:

- `DailyLogs/YYYY-MM-DD.md`
- `MEMORY.md` (if pattern emerges)

---

*error-recovery.md | Autonomous-Core | v2.3.3*
