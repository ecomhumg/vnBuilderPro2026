# save-all - Save Session State

> **CLAWDBOT v2.3.2** | Command | Session Operations

---

## Usage

```
/save-all
```

## Purpose

Save all current session state to daily log and memory.

## Process

1. **Capture Session State**
   - Current content brief
   - In-progress content
   - Decisions made
   - Errors encountered

2. **Write to Daily Log**
   - Append to `DailyLogs/YYYY-MM-DD.md`
   - Include timestamp

3. **Update Working Files**
   - Content drafts
   - Research notes

## Output

```
Session Saved:
- Daily log: [path]
- Entries: [X] new entries
- Timestamp: [ISO timestamp]
```

---

*save-all.md | CLAWDBOT v2.3.2*
