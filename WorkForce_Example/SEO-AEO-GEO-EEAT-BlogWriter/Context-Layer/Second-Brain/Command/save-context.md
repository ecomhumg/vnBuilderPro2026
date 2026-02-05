# Save Context Command

> **SEO-AEO-GEO-EEAT-BlogWriter** | Command | CLAWDBOT v2.3.2

---

## Usage

```
/save-context [options]
```

---

## Description

Saves current execution context to `Memory/ExecutionLogs/` for later resumption.

---

## Options

| Option | Description | Default |
|--------|-------------|---------|
| `--phase` | Specific phase to snapshot | current |
| `--full` | Save complete memory bus | false |
| `--tag` | Custom tag for identification | none |

---

## Examples

```bash
# Save current context
/save-context

# Save with full memory bus
/save-context --full

# Save with custom tag
/save-context --tag "before-major-edit"
```

---

## Output

```json
{
  "status": "saved",
  "session_id": "2026-02-05-051400",
  "path": "Memory/ExecutionLogs/2026-02-05-051400.json",
  "phase": 3,
  "bytes": 4096
}
```

---

## Integration

- Calls `Autonomous-Core/context-persistence.md`
- Writes to `Memory/ExecutionLogs/`
- Updates `Memory/ExecutionLogs/index.json`

---

## Auto-Execute (NEW)

> [!IMPORTANT]
> As of v2.3.3, `/save-context --full` is **automatically executed** on task completion.

**Trigger**: Phase 8 or Phase 9 completion
**Handler**: `Autonomous-Core/orchestrator.md`

This ensures all execution context is preserved for:

- Session resumption via `/load-context`
- Pattern extraction in `self-improvement-loop.md`
- Quality trend analysis

---

*save-context.md | Command | v2.3.3 Enhanced*
