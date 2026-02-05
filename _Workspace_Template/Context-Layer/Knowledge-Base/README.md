# Knowledge-Base README

> **_Workspace_Template** | Context-Layer/Knowledge-Base | vnBuilderProMax v2.3.3

---

## Overview

Knowledge-Base là kho tri thức 3 lớp cho các Workers, bao gồm:

| Type | Prefix | Count | Purpose |
|------|--------|-------|---------|
| **PLAYBOOKS** | PB-XXX | 8 | Protocols, checklists, SOPs |
| **SKILLS** | SK-XXX | 10 | Technical implementation guides |
| **EXPERIENCE** | EXP-XXX | 4+ | Curated patterns from Outputs (auto-growing) |

---

## Directory Structure

```
Knowledge-Base/
├── PLAYBOOKS/                    # 8 protocol files
│   ├── PB-001-ContentBriefProtocol.md
│   ├── PB-002-EEATComplianceChecklist.md
│   └── ...
├── SKILLS/                       # 10 skill files
│   ├── SK-001-KeywordEntityResearch.md
│   ├── SK-002-CompetitorContentAnalysis.md
│   └── ...
├── EXPERIENCE/                   # Auto-growing experience files
│   ├── EXP-001-TexasLegalContent.md
│   └── ...
├── knowledge-base-index.json     # Auto-discovery index
├── knowledge-loader.md           # Loading instructions
└── README.md                     # This file
```

---

## Worker Access

| Tier | PLAYBOOKS | SKILLS | EXPERIENCE |
|------|-----------|--------|------------|
| T1 Strategy | PB-001, 002, 008 | SK-001, 003 | ❌ |
| T2 Intelligence | PB-001, 004 | SK-001, 002, 003 | ❌ |
| T3 Content | PB-003, 005-008 | SK-004 to 008 | ✅ Read All |
| T4 Analysis | PB-002, 008 | SK-009, 010 | ❌ |
| T5 Validation | PB-002 | SK-010 | ❌ |
| T6 Synthesis | PB-007 | SK-008 | ✅ Read/Write |

---

## Learning Pipeline

High-quality Outputs (score ≥ 90) → Pattern extraction → New EXPERIENCE files

```
Outputs/[topic]/ → outputs-learner.md → EXPERIENCE/EXP-XXX.md
```

---

## Usage

See `knowledge-loader.md` for Worker integration details.

---

*Knowledge-Base v2.3.3 | Auto-growing with Learning Pipeline*
