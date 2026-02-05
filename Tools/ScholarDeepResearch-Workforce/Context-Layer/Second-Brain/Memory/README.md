# Memory Hub

> Persistent storage for context, state, and execution history with **auto-persistence** after each phase.

## Structure

| Directory | Purpose |
|-----------|---------|
| `Context/` | Project-level context templates |
| `Evolution/` | Learning logs, patterns, behavior policies |
| `History/` | Execution logs, quality reports |
| `Sessions/` | Saved session snapshots |
| `State/` | Current memory bus, worker states |
| `PhaseOutputs/` | **Auto-saved outputs after each tier** |

## Auto-Persistence Feature

Results are automatically persisted after each phase completes:

| Phase | Tier | Auto-Saved Content |
|-------|------|-------------------|
| Query Processing | 1 | Clarified query, domain classification |
| Search Strategy | 2 | Keywords, source priorities |
| Search Acquisition | 3 | Raw results from all databases |
| Content Extraction | 4 | Fulltext content, extracted datasets |
| Critical Reading | 5 | Summaries, questions, contrasts, visuals |
| Analysis & Synthesis | 6 | Statistics, visualizations, fact-checks |
| Quality Validation | 7 | Citation validation, E-O scores |
| Report Generation | 8 | Final report, session metadata |

## Key Files

| File | Format | Description |
|------|--------|-------------|
| `memory-bus-snapshot.json` | JSON | Current state of all memory keys |
| `auto-persistence-config.json` | JSON | Auto-save configuration |
| `evolution-log.json` | JSON | Chronological adaptation records |
| `learned-patterns.json` | JSON | Promoted behavior patterns |

## Usage

- **Auto-Save**: Enabled by default after each tier
- **Manual Save**: `/save-all` for on-demand persistence
- **Restore**: `/recall` to rehydrate from session

---

*Memory Hub v1.0 | ScholarDeepResearch-Workforce*
