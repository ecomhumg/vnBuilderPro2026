# Search Command

> Search across results, sessions, and knowledge base.

## Usage

```bash
/search <query> [--scope <scope>] [--format <format>]
```

## Scopes

| Scope | Target |
|-------|--------|
| `results` | Current research results (default) |
| `sessions` | All saved sessions |
| `knowledge` | Knowledge-Base content |
| `all` | Everything |

## Formats

| Format | Output |
|--------|--------|
| `table` | Tabular results (default) |
| `json` | JSON export |
| `csv` | CSV export |

## Examples

```bash
# Search in current results
/search "machine learning" --scope results

# Search across all sessions
/search "transformer architecture" --scope sessions

# Export search results
/search "citation validation" --scope knowledge --format json
```

## Search Operators

| Operator | Example | Description |
|----------|---------|-------------|
| `AND` | `AI AND education` | Both terms |
| `OR` | `ML OR DL` | Either term |
| `NOT` | `AI NOT robotics` | Exclude term |
| `"..."` | `"deep learning"` | Exact phrase |
| `year:` | `year:2024-2026` | Year range |
| `author:` | `author:Smith` | Author filter |
| `doi:` | `doi:10.1234` | DOI search |

---

*Search Command v1.0 | ScholarDeepResearch-Workforce*
