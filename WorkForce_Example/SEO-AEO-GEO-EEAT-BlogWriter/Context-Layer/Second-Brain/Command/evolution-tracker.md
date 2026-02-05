# Evolution Tracker Command

> **SEO-AEO-GEO-EEAT-BlogWriter** | Command | CLAWDBOT v2.3.2

---

## Usage

```
/evolution-tracker [action] [options]
```

---

## Description

Tracks and reports on quality evolution metrics and self-learning progress.

---

## Actions

| Action | Description |
|--------|-------------|
| `status` | Show current evolution metrics |
| `trends` | Display quality trends (7d/30d) |
| `patterns` | List top performing patterns |
| `focus` | Show improvement focus areas |
| `compare` | Compare two time periods |

---

## Examples

```bash
# Show current status
/evolution-tracker status

# View 30-day trends
/evolution-tracker trends --period 30d

# List top 10 patterns
/evolution-tracker patterns --top 10

# Compare two weeks
/evolution-tracker compare --from 2026-01-22 --to 2026-02-05
```

---

## Output: Status

```
═══════════════════════════════════════
     EVOLUTION STATUS - 2026-02-05
═══════════════════════════════════════

📊 Quality Trends
   SEO:   88.5 → 91.2 (+2.7) ↑
   AEO:   82.3 → 86.7 (+4.4) ↑
   GEO:   79.8 → 83.1 (+3.3) ↑
   EEAT:  85.2 → 88.9 (+3.7) ↑

📈 Sessions: 47 total | 12 this week
🎯 Focus Areas: geo-local-signals, expert-citations

🏆 Top Patterns (by success rate):
   1. numbered-list-faq (94%)
   2. tldr-opener (91%)
   3. h1-question-how-to (89%)

═══════════════════════════════════════
```

---

## Integration

- Reads from `Memory/Learning/metrics.json`
- Reads from `Memory/Learning/patterns.md`
- Calls `Autonomous-Core/self-improvement-loop.md`

---

*evolution-tracker.md | Command | v2.3.3*
