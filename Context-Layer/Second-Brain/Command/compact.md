# compact

> **Command**: Compress and optimize memory
> **Syntax**: `compact [--layer <1|2|all>] [--force]`

---

## Description

Compress daily logs and optimize memory storage.

## Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `--layer` | `all` | Layer to compact |
| `--force` | false | Bypass thresholds |

## Examples

```bash
# Auto compact
compact

# Force Layer 1 compaction
compact --layer 1 --force
```

---

*CLAWDBOT v2.3.2 | compact*
