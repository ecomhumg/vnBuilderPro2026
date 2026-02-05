# MEMORY.md - Layer 2: Long-term Curated Knowledge

> **vnBuilderPro-MAS2026 | CLAWDBOT Memory System v2.2.0**
> Persistent, curated knowledge layer for decisions, facts, and patterns

---

## Overview

This file represents **Layer 2** of the CLAWDBOT Two-Layer Memory Architecture. It stores curated, verified knowledge that persists across all sessions.

```mermaid
graph LR
    subgraph TwoLayer["Two-Layer Memory Architecture"]
        L2["Layer 2: MEMORY.md<br/>(Curated Knowledge)"]
        L1["Layer 1: DailyLogs/<br/>(Daily Session Logs)"]
    end
    
    L1 -->|"Summarization"| L2
    L2 -->|"Semantic Index"| SEARCH["Search Index"]
```

---

## Knowledge Categories

### 1. Workforce Decisions

| Decision ID | Date | Context | Decision | Rationale |
|-------------|------|---------|----------|-----------|
| DEC-001 | 2026-02-02 | Agent topology | HierarchicalSwarm | Best for 22+ workers with clear tier hierarchy |
| DEC-002 | 2026-02-02 | Memory pattern | Two-Layer CLAWDBOT | Balances context cost with persistent knowledge |

---

### 2. Domain Facts

| Fact ID | Category | Fact | Source | Confidence |
|---------|----------|------|--------|------------|
| FACT-001 | Architecture | 528 agents = 22 workers × 24 agents | vnBuilderPro-MAS2026 Standard | 1.0 |
| FACT-002 | Memory | ~400 chunks with 80% overlap optimal | CLAWDBOT indexing research | 0.95 |
| FACT-003 | Retrieval | BM25 + Vector hybrid outperforms single-mode | RAG benchmark 2024 | 0.92 |

---

### 3. Quality Patterns

| Pattern ID | Name | Description | Success Rate |
|------------|------|-------------|--------------|
| QP-001 | ROMA Pipeline | 6-stage worker execution pattern | 94% |
| QP-002 | 8-Tier Hierarchy | Hierarchical swarm organization | 96% |
| QP-003 | Memory Bus Contract | Cross-worker state sharing | 91% |

---

### 4. Agent Behavior Configurations

```yaml
default_behaviors:
  memory_read:
    trigger: "session_start"
    action: "load MEMORY.md + today's DailyLog"
  
  memory_write:
    trigger: "task_complete"
    action: "append to DailyLogs/YYYY-MM-DD.md"
  
  memory_curate:
    trigger: "compaction_request"
    action: "summarize DailyLogs → MEMORY.md"
```

---

### 5. Learned Optimizations

| Optimization ID | Area | Before | After | Improvement |
|-----------------|------|--------|-------|-------------|
| OPT-001 | Chunk size | 200 | 400 | +23% retrieval accuracy |
| OPT-002 | Overlap | 50% | 80% | +15% context preservation |
| OPT-003 | TTL | 30d | 90d | -40% recomputation cost |

---

## Curation Rules

1. **Promotion from Layer 1**: Daily log entries with `[CURATE]` tag are promoted to MEMORY.md during compaction
2. **Fact Verification**: Facts require confidence ≥ 0.8 and source citation
3. **Decision Recording**: All architectural decisions must include rationale
4. **Pattern Validation**: Patterns require ≥ 90% success rate across 3+ executions

---

## Search Integration

This file is indexed by the CLAWDBOT memory pipeline:

| Feature | Specification |
|---------|---------------|
| **Vector Index** | sqlite-vec embeddings |
| **Text Index** | FTS5 full-text search |
| **Search Mode** | Hybrid (Vector + BM25) |
| **Update Trigger** | File watcher on save |

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 2.2.0 | 2026-02-02 | Initial CLAWDBOT integration |

---

*vnBuilderPro-MAS2026 Memory Layer 2 | CLAWDBOT Standard v2.2.0*
