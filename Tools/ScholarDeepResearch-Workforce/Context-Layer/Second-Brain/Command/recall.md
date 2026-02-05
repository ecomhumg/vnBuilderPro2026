# Recall Command

> Recall and restore previous research sessions.

## Usage

```bash
/recall <session-id> [--merge]
```

## Options

| Option | Description |
|--------|-------------|
| `--merge` | Merge with current session instead of replacing |

## Examples

```bash
# Restore specific session
/recall session-001

# Merge session into current
/recall session-002 --merge

# Recall most recent
/recall last
```

## Session Contents Restored

| Component | Restored |
|-----------|----------|
| Search results | ✅ |
| Critical reading outputs | ✅ |
| Citation list | ✅ |
| Generated visualizations | ✅ |
| Memory bus state | ✅ |

## Merge Behavior

When using `--merge`:

- Results are deduplicated by DOI
- Latest critical reading outputs take precedence
- Citations are combined
- Visualizations are preserved from both

---

*Recall Command v1.0 | ScholarDeepResearch-Workforce*
