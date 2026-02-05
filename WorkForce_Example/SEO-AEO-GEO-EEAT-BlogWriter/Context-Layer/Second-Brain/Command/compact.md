# compact - Memory Compaction Command

> **CLAWDBOT v2.3.2** | Command | Memory Pipeline

---

## Usage

```
/compact
```

## Purpose

Compact daily logs into curated MEMORY.md entries, removing redundancy and preserving key decisions.

## Process

1. **Scan Daily Logs**: Read all files in `DailyLogs/`
2. **Extract Patterns**: Identify recurring themes, decisions, learnings
3. **Deduplicate**: Remove redundant entries
4. **Categorize**: Group by topic (SEO, AEO, GEO, E-E-A-T)
5. **Write to MEMORY.md**: Append curated entries

## Compaction Rules

| Source | Action |
|--------|--------|
| Repeated patterns (3+ times) | Elevate to MEMORY.md |
| One-time observations | Keep in daily log only |
| Key decisions | Always elevate |
| Errors and fixes | Elevate if patterns emerge |

## Output

```
Compaction complete:
- Scanned: [X] daily logs
- Extracted: [Y] patterns
- Added to MEMORY.md: [Z] entries
```

---

*compact.md | CLAWDBOT v2.3.2*
