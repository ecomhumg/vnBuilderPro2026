# List Memory Command

> View saved sessions and memory contents.

## Usage

```bash
/list-memory [--type <type>] [--limit <n>]
```

## Types

| Type | Contents |
|------|----------|
| `sessions` | Saved research sessions (default) |
| `reports` | Generated reports |
| `cache` | Cached search results |
| `all` | All memory contents |

## Examples

```bash
# List recent sessions
/list-memory --type sessions --limit 10

# List all reports
/list-memory --type reports

# Show all cached data
/list-memory --type cache
```

## Output

```
Session ID       | Date       | Query                    | Results
-----------------|------------|--------------------------|--------
session-001      | 2026-01-31 | AI in education          | 45
session-002      | 2026-01-30 | transformer architecture | 32
```

## Storage Location

| Type | Path |
|------|------|
| Sessions | `Second-Brain/Memory/Sessions/` |
| Reports | `Second-Brain/Memory/Reports/` |
| Cache | `Retrieval/cache/` |

---

*List Memory Command v1.0 | ScholarDeepResearch-Workforce*
