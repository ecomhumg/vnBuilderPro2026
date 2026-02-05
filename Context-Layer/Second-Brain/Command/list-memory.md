# list-memory

> **Command**: List memory entries
> **Syntax**: `list-memory [--type <sessions|decisions|patterns>] [--limit <n>]`

---

## Description

List memory entries by type or category.

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `--type` | `all` | Entry type filter |
| `--limit` | `10` | Maximum entries |
| `--category` | none | Category filter |

## Examples

```bash
# List all
list-memory

# List decisions only
list-memory --type decisions --limit 20

# List by category
list-memory --category {category}
```

---

*CLAWDBOT v2.3.2 | list-memory*
