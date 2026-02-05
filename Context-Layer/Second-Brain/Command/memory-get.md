# memory-get

> **Command**: Read specific memory content
> **Syntax**: `memory-get <path> [--section <name>]`

---

## Description

Read specific content from memory layers by path or identifier.

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `path` | required | Memory path or ID |
| `--section` | none | Specific section to retrieve |

## Examples

```bash
# Get full MEMORY.md
memory-get MEMORY.md

# Get specific section
memory-get MEMORY.md --section "{Section Name}"

# Get daily log
memory-get DailyLogs/YYYY-MM-DD.md

# Get by ID
memory-get {ID}
```

---

*CLAWDBOT v2.3.2 | memory-get*
