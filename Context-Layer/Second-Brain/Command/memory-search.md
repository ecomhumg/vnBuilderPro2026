# memory-search

> **Command**: Semantic memory search
> **Syntax**: `memory-search "<query>" [--layer <1|2|all>] [--limit <n>]`

---

## Description

Search memory using hybrid Vector + BM25 approach across both memory layers.

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `query` | required | Search query string |
| `--layer` | `all` | Layer to search (1, 2, or all) |
| `--limit` | `5` | Maximum results |
| `--category` | none | Filter by category |

## Examples

```bash
# Search all layers
memory-search "{domain-specific query}"

# Search Layer 2 only
memory-search "{query}" --layer 2

# Limit results
memory-search "{query}" --limit 3

# Filter by category
memory-search "{query}" --category {category}
```

## Output Format

```yaml
results:
  - source: MEMORY.md#{ID}
    score: 0.92
    content: |
      {Matched content}...
  - source: DailyLogs/YYYY-MM-DD.md
    score: 0.85
    content: |
      {Matched content}...
```

---

*CLAWDBOT v2.3.2 | memory-search*
