# Context-Layer

> **Unified Intelligence Hub for ScholarDeepResearch-Workforce v1.1.0**

---

## Overview

| Component | Purpose |
|-----------|---------|
| **Knowledge-Base/** | 3-tier domain knowledge (PLAYBOOKS, SKILLS, EXPERIENCE) |
| **Second-Brain/** | Intelligence hub with Auto-Persistence |
| **Research-Integration/** | Multi-database research connection layer |
| **Retrieval/** | Context retrieval engine |

---

## Directory Structure

```
Context-Layer/
├── Knowledge-Base/
│   ├── PLAYBOOKS/        (10 playbooks)
│   ├── SKILLS/           (12 skills)
│   └── EXPERIENCE/       (6 patterns)
├── Second-Brain/
│   ├── Brain/            (7 files - Autonomy, Coordination, Evolution)
│   ├── Memory/           (Auto-Persistence)
│   │   ├── PhaseOutputs/ (💾 auto-saved phase results)
│   │   ├── Sessions/     (saved session snapshots)
│   │   ├── State/        (memory bus state)
│   │   ├── Context/      (project context)
│   │   ├── Evolution/    (learning logs)
│   │   └── History/      (execution history)
│   ├── Command/          (4 commands: search, recall, save-all, list-memory)
│   ├── Scripts/
│   └── Conversation/
├── Research-Integration/
│   ├── research-config.json
│   └── integration-patterns.md
└── Retrieval/
    ├── retrieval-engine.md
    └── index-config.json
```

---

## 💾 Auto-Persistence Feature

Results are automatically saved after each tier:

| Phase | Output File |
|-------|-------------|
| Tier 1 | phase-01-query.json |
| Tier 2 | phase-02-strategy.json |
| Tier 3 | phase-03-search.json |
| Tier 4 | phase-04-extraction.json |
| Tier 5 | phase-05-reading.json |
| Tier 6 | phase-06-analysis.json |
| Tier 7 | phase-07-validation.json |
| Tier 8 | phase-08-report.json |

See `Memory/auto-persistence-config.json` for configuration.

---

## Available Commands

| Command | Description |
|---------|-------------|
| `/search` | Search across results, sessions, knowledge |
| `/recall` | Restore previous research session |
| `/save-all` | Manual full session save |
| `/list-memory` | View saved sessions and reports |

---

*Context-Layer v1.1.0 | ScholarDeepResearch-Workforce*
