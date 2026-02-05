# Load Context Command

> **SEO-AEO-GEO-EEAT-BlogWriter** | Command | CLAWDBOT v2.3.2

---

## Usage

```
/load-context <session_id> [options]
```

---

## Description

Restores execution context from a previous session stored in `Memory/ExecutionLogs/`.

---

## Arguments

| Argument | Description | Required |
|----------|-------------|----------|
| `session_id` | Session ID to restore (YYYY-MM-DD-HHMMSS) | Yes |

## Options

| Option | Description | Default |
|--------|-------------|---------|
| `--phase` | Resume from specific phase | last |
| `--dry-run` | Preview without applying | false |
| `--merge` | Merge with current context | false |

---

## Examples

```bash
# Restore last session
/load-context 2026-02-05-051400

# Resume from specific phase
/load-context 2026-02-05-051400 --phase 3

# Preview restoration
/load-context 2026-02-05-051400 --dry-run
```

---

## Output

```json
{
  "status": "restored",
  "session_id": "2026-02-05-051400",
  "topic": "Texas Employment Law Guide",
  "resumed_from_phase": 3,
  "memory_keys_restored": 47,
  "ready_to_continue": true
}
```

---

## Integration

- Reads from `Memory/ExecutionLogs/`
- Restores memory bus state
- Notifies orchestrator for phase resumption

---

*load-context.md | Command | v2.3.3*
