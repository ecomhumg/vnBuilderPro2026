# Save All Command

> Persist current session state to memory.

## Usage

```bash
/save-all [--name <name>] [--include <components>]
```

## Options

| Option | Description | Default |
|--------|-------------|---------|
| `--name` | Session name | Auto-generated |
| `--include` | Components to save | all |

## Components

| Component | Flag | Description |
|-----------|------|-------------|
| `results` | `r` | Search results |
| `reading` | `d` | Critical reading outputs |
| `citations` | `c` | Citation list |
| `visuals` | `v` | Generated visualizations |
| `report` | `p` | Final report |
| `all` | `a` | Everything (default) |

## Examples

```bash
# Save everything with auto name
/save-all

# Save with custom name
/save-all --name "AI-Education-Review-2026"

# Save only results and citations
/save-all --include rc
```

## Output

```
✅ Session saved: session-003
   Path: Second-Brain/Memory/Sessions/session-003/
   Components: results, reading, citations, visuals, report
   Size: 2.4 MB
   Timestamp: 2026-01-31T12:00:00+07:00
```

---

*Save All Command v1.0 | ScholarDeepResearch-Workforce*
