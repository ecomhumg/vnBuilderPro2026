# DailyLogs - Layer 1: Daily Session Logs

> **vnBuilderPro-MAS2026 | CLAWDBOT Memory System v2.2.0**
> Append-only daily logs for session context

---

## Overview

This directory contains **Layer 1** of the CLAWDBOT Two-Layer Memory Architecture. Each file represents one day's session logs in `YYYY-MM-DD.md` format.

---

## File Naming Convention

```
DailyLogs/
├── 2026-02-02.md
├── 2026-02-01.md
├── 2026-01-31.md
└── ...
```

---

## Daily Log Template

Each daily log follows this structure:

```markdown
# Daily Log: YYYY-MM-DD

## Session Summary
- Session start: HH:MM
- Session end: HH:MM
- Workers executed: [list]

## Key Activities
- [ ] Activity 1
- [x] Activity 2 (completed)

## Notes
Append-only notes during session...

## Learnings
### [CURATE] Important Learning
This entry will be promoted to MEMORY.md during compaction.

## Next Steps
- [ ] Planned task 1
- [ ] Planned task 2
```

---

## Curation Tags

| Tag | Purpose | Action |
|-----|---------|--------|
| `[CURATE]` | Promote to Layer 2 | Move to MEMORY.md during compaction |
| `[TEMPORARY]` | Session-only | Delete after compaction |
| `[REFERENCE]` | Keep in log | Remain in daily log indefinitely |

---

## Retention Policy

| Age | Action |
|-----|--------|
| 0-7 days | Full content retained |
| 8-30 days | Summarized content |
| 31-90 days | Curated entries only |
| 90+ days | Pruned (Cache-TTL) |

---

## Memory Flush Trigger

When the context window approaches the limit (~200K tokens):

1. **Pre-compaction**: Silent turn stores durable info to `DailyLogs/YYYY-MM-DD.md`
2. **Compaction**: Summarization triggered automatically or via `/compact`
3. **Promotion**: `[CURATE]` entries move to `MEMORY.md`

---

*vnBuilderPro-MAS2026 Memory Layer 1 | CLAWDBOT Standard v2.2.0*
