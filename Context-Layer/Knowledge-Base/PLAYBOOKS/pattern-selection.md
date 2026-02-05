# Pattern Selection Playbook

> **Framework for Choosing from 107 MAS Patterns**

---

## Pattern Library Overview

| Category | Count | Examples |
|----------|-------|----------|
| Orchestration & Control | 15 | Autonomous-Workflow, Plan-then-Execute |
| Reasoning & Cognition | 12 | Graph-of-Thoughts, LATS, Self-Critique |
| Memory & State | 10 | Episodic-Memory, Filesystem-State |
| Tool Use | 8 | Parallel-Tool-Execution, Code-First |
| Scaling & Distribution | 10 | Swarm-Migration, Distributed-Execution |
| Learning & Evolution | 8 | Skill-Library-Evolution, RLAIF |
| Human Interaction | 7 | HITL-Approval, Progressive-Autonomy |
| Security & Safety | 5 | Egress-Lockdown, PII-Tokenization |
| Multi-Agent | 12 | Sub-Agent-Spawning, Multi-Agent-Debate |
| Other | 20 | Various specialized patterns |

---

## Selection Decision Tree

```
START: What is the primary workflow characteristic?
│
├── Sequential processing?
│   └── plan-then-execute-pattern.md
│       └── Need phases? → discrete-phase-separation.md
│
├── Parallel processing?
│   └── parallel-tool-execution.md
│       └── Many workers? → distributed-execution-cloud-workers.md
│
├── Complex reasoning?
│   ├── Exploration needed? → graph-of-thoughts.md
│   ├── Search with backtrack? → language-agent-tree-search-lats.md
│   └── Self-improvement? → self-critique-evaluator-loop.md
│
├── Dynamic sub-tasks?
│   └── sub-agent-spawning.md
│       └── Many levels? → hierarchical delegation
│
├── Research-intensive?
│   └── agent-driven-research.md
│       └── Vector search? → agentic-search-over-vector-embeddings.md
│
├── Long-running?
│   └── continuous-autonomous-task-loop-pattern.md
│       └── Need context? → extended-coherence-work-sessions.md
│
└── Human oversight needed?
    └── human-in-loop-approval-framework.md
        └── Progressive trust? → progressive-autonomy-with-model-evolution.md
```

---

## Pattern Matching by Problem Type

### For Workforce Generation

| Requirement | Primary Pattern | Secondary |
|-------------|-----------------|-----------|
| Multi-worker system | sub-agent-spawning | swarm-migration |
| Knowledge synthesis | agent-driven-research | memory-synthesis |
| Prompt generation | self-rewriting-meta-prompt-loop | specification-driven |
| Quality assurance | self-critique-evaluator-loop | criticgpt-style |
| Adaptive systems | skill-library-evolution | progressive-autonomy |

### For Code Generation

| Requirement | Primary Pattern | Secondary |
|-------------|-----------------|-----------|
| Complex edits | multi-model-orchestration | curated-code-context |
| Testing | subagent-compilation-checker | spec-as-test-feedback |
| Security | deterministic-security-scanning | egress-lockdown |
| Large codebases | curated-file-context-window | context-minimization |

---

## Pattern Compatibility Matrix

| Pattern A | Compatible With | Incompatible With |
|-----------|----------------|-------------------|
| Parallel-Tool-Execution | Distributed-Execution | Sequential-Only |
| Graph-of-Thoughts | Self-Critique | Simple-Chain |
| HITL-Approval | Progressive-Autonomy | Full-Autonomy |
| Sub-Agent-Spawning | Hierarchical-Swarm | Flat-Structure |

---

## Pattern Application Checklist

- [ ] Identify primary pattern need
- [ ] Check compatibility with constraints
- [ ] Verify secondary pattern synergy
- [ ] Confirm no anti-pattern conflicts
- [ ] Document rationale in decision log

---

*Pattern Selection Playbook v1.0 | MASDesign-Workforce*
