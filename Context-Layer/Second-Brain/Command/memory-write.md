# memory-write

> **Command**: Write/update memory content
> **Syntax**: `memory-write <content> --layer <1|2> [--category <name>] [--tags "<tags>"]`

---

## Description

Write new content to memory or update existing entries.

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `content` | required | Content to write |
| `--layer` | required | Target layer (1 or 2) |
| `--category` | `note` | Content category |
| `--tags` | none | Comma-separated tags |
| `--id` | auto | Custom identifier |

## Examples

```bash
# Write to Layer 1 (daily log)
memory-write "{content}" --layer 1 --category note

# Write decision to Layer 2
memory-write "{decision}" --layer 2 --category {category} --id {ID}

# Write pattern
memory-write "{pattern}" --layer 2 --category {category} --tags "{tags}"
```

---

*CLAWDBOT v2.3.2 | memory-write*
