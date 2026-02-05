# Execution Flowcharts

> **vnBuilderProMax v2.3.2** | **6-Tier HierarchicalSwarm** | **Execution Pipeline Visualization**
>
> Tài liệu lưu đồ thực thi chi tiết cho workforce 528-agent

---

## Mục Lục

1. [Master 8-Phase Pipeline](#1-master-8-phase-pipeline)
2. [Tier 1: Strategy Sequential Flow](#2-tier-1-strategy-sequential-flow)
3. [Tier 2: Intelligence Parallel Flow](#3-tier-2-intelligence-parallel-flow)
4. [Tier 3: Content Creation Parallel Flow](#4-tier-3-content-creation-parallel-flow)
5. [Tier 4: Analysis Barrier Sync Flow](#5-tier-4-analysis-barrier-sync-flow)
6. [Tier 5: Validation Sequential Flow](#6-tier-5-validation-sequential-flow)
7. [Tier 6: Synthesis Sequential Flow](#7-tier-6-synthesis-sequential-flow)
8. [Worker Task Execution Template](#8-worker-task-execution-template)
9. [Memory Bus Interaction Flow](#9-memory-bus-interaction-flow)
10. [Context Injection Pipeline](#10-context-injection-pipeline)
11. [Autonomous Decision Loop](#11-autonomous-decision-loop)
12. [Error Recovery Flow](#12-error-recovery-flow)

---

## 1. Master 8-Phase Pipeline

> **Tổng quan toàn bộ quy trình thực thi workforce từ Phase 0 đến Phase 7**

```mermaid
graph TD
    START[Goal Input] --> P0[Phase 0: Bootstrap Context]
    P0 --> P0Q{Context Valid?}
    P0Q -->|No| ERR[Context Error]
    P0Q -->|Yes| P1[Phase 1: Strategy - T1]
    P1 --> P1Q{Quality >= 95%?}
    P1Q -->|No| R1[Retry T1]
    R1 --> P1
    P1Q -->|Yes| P2[Phase 2: Intelligence - T2]
    P2 --> P2Q{>= 10 Sources?}
    P2Q -->|No| R2[Expand Research]
    R2 --> P2
    P2Q -->|Yes| P3[Phase 3: Content - T3]
    P3 --> P3Q{Integration OK?}
    P3Q -->|No| R3[Fix Integration]
    R3 --> P3
    P3Q -->|Yes| P4[Phase 4: Analysis - T4]
    P4 --> P4Q{Paths Defined?}
    P4Q -->|No| R4[Define Paths]
    R4 --> P4
    P4Q -->|Yes| P5[Phase 5: Validation - T5]
    P5 --> P5Q{Compliance?}
    P5Q -->|No| R5[Remediation]
    R5 --> P5
    P5Q -->|Yes| P6[Phase 6: Synthesis - T6]
    P6 --> P6Q{Delivery >= 95%?}
    P6Q -->|No| R6[Complete Gaps]
    R6 --> P6
    P6Q -->|Yes| P7[Phase 7: Memory Logging]
    P7 --> FINISH[Execution Complete]
```

---

## 2. Tier 1: Strategy Sequential Flow

> **Sequential Execution**: W01 → W02 → W03 → W04

```mermaid
graph LR
    IN[Domain Brief] --> W01[W01: ResearchStrategy]
    W01 --> W02[W02: DomainPlanning]
    W02 --> W03[W03: StandardsAlignment]
    W03 --> W04[W04: IntegrationStrategy]
    W04 --> OUT[Strategic Blueprint]
```

**Detailed W01 Flow:**

```mermaid
graph LR
    A[Domain Brief] --> B[Intake]
    B --> C[Needs Assessment]
    C --> D[Strategic Planning]
    D --> E[Alignment Validation]
    E --> F[Research Blueprint]
```

---

## 3. Tier 2: Intelligence Parallel Flow

> **Parallel Execution with Barrier Sync**: W05, W06, W07, W08

```mermaid
graph TD
    IN[Strategic Blueprint] --> DISPATCH[Parallel Dispatch]
    DISPATCH --> W05[W05: ContentIntel]
    DISPATCH --> W06[W06: QualityIntel]
    DISPATCH --> W07[W07: TechIntel]
    DISPATCH --> W08[W08: TrendForecast]
    W05 --> SYNC[Barrier Sync]
    W06 --> SYNC
    W07 --> SYNC
    W08 --> SYNC
    SYNC --> OUT[Intelligence Package]
```

---

## 4. Tier 3: Content Creation Parallel Flow

> **Parallel with Aggregator Pattern**: W09-W13 parallel, W14 aggregator

```mermaid
graph TD
    IN[Intelligence Package] --> CREATE[Parallel Create]
    CREATE --> W09[W09: Primary Content]
    CREATE --> W10[W10: Secondary Content]
    CREATE --> W11[W11: Multimedia]
    CREATE --> W12[W12: Assessments]
    CREATE --> W13[W13: Documentation]
    W09 --> W14[W14: Integration]
    W10 --> W14
    W11 --> W14
    W12 --> W14
    W13 --> W14
    W14 --> OUT[Content Package]
```

---

## 5. Tier 4: Analysis Barrier Sync Flow

> **Barrier Sync Parallel**: W15, W16, W17, W18

```mermaid
graph TD
    IN[Content Package] --> ANALYZE[Parallel Analyze]
    ANALYZE --> W15[W15: DataAnalytics]
    ANALYZE --> W16[W16: PerfMapping]
    ANALYZE --> W17[W17: Personalization]
    ANALYZE --> W18[W18: ProgressTrack]
    W15 --> SYNC[Barrier Sync]
    W16 --> SYNC
    W17 --> SYNC
    W18 --> SYNC
    SYNC --> OUT[Analysis Package]
```

---

## 6. Tier 5: Validation Sequential Flow

> **Sequential Validation**: W19 → W20

```mermaid
graph LR
    IN[Analysis Package] --> W19[W19: QualityAssurance]
    W19 --> CHECK{Issues Found?}
    CHECK -->|Yes| FIX[Auto-Remediate]
    FIX --> W20[W20: Compliance]
    CHECK -->|No| W20
    W20 --> OUT[Validation Certificate]
```

---

## 7. Tier 6: Synthesis Sequential Flow

> **Sequential Synthesis**: W21 → W22

```mermaid
graph LR
    IN[Validation Cert] --> W21[W21: ReportGenerator]
    W21 --> SUMMARY[Executive Summary]
    W21 --> DETAIL[Detailed Reports]
    SUMMARY --> W22[W22: Certification]
    DETAIL --> W22
    W22 --> OUT[Certified Package]
```

---

## 8. Worker Task Execution Template

> **Generic Worker Execution Flow** - Áp dụng cho tất cả 22 workers

```mermaid
graph TD
    START[Worker Activated] --> CTX[Context Injection]
    CTX --> MEM_R[Memory Search]
    MEM_R --> TASK[Execute Primary Task]
    TASK --> AGENTS[Spawn 24 Agents]
    AGENTS --> AGG[Aggregate Results]
    AGG --> QC{Quality >= 0.85?}
    QC -->|No| RETRY[Retry with Context]
    RETRY --> TASK
    QC -->|Yes| ACCEPT[Accept Result]
    ACCEPT --> MEM_W[Memory Write]
    MEM_W --> PUB[Publish to Bus]
    PUB --> FINISH[Worker Complete]
```

---

## 9. Memory Bus Interaction Flow

> **Worker Read/Write Patterns với Namespace Routing**

```mermaid
graph LR
    WORKER[Worker] --> READ[memory-search]
    READ --> BUS[Memory Bus]
    BUS --> NS1[strategy namespace]
    BUS --> NS2[intel namespace]
    BUS --> NS3[content namespace]
    BUS --> NS4[analysis namespace]
    NS1 --> EXEC[Execute Task]
    NS2 --> EXEC
    NS3 --> EXEC
    NS4 --> EXEC
    EXEC --> WRITE[memory-write]
    WRITE --> L1[Layer 1: DailyLogs]
    WRITE --> L2[Layer 2: MEMORY.md]
```

---

## 10. Context Injection Pipeline

> **Phase 0 Bootstrap Context Loading Flow**

```mermaid
graph TD
    BOOT[Bootstrap Start] --> AGENTS[Load AGENTS.md]
    BOOT --> SOUL[Load SOUL.md]
    BOOT --> USER[Load USER.md]
    BOOT --> TOOLS[Load TOOLS.md]
    AGENTS --> CB[ContextBuilder]
    SOUL --> CB
    USER --> CB
    TOOLS --> CB
    CB --> SL[SkillsLoader]
    SL --> MS[MemoryStore]
    MS --> AL[AgentLoop Init]
    AL --> SM[SubagentManager]
    SM --> READY[Worker Context Ready]
```

---

## 11. Autonomous Decision Loop

> **L5 Full Autonomy Goal-Driven Execution Cycle**

```mermaid
graph TD
    GOAL[Goal Input] --> INTERPRET[Goal Interpretation]
    INTERPRET --> PLAN[Decision Planning]
    PLAN --> DISPATCH[Parallel Dispatch]
    DISPATCH --> EXECUTE[Execution Monitor]
    EXECUTE --> FEEDBACK[Feedback Collection]
    FEEDBACK --> IMPROVE[Self-Improvement]
    IMPROVE --> EVAL{Goal Achieved?}
    EVAL -->|No| OPTIMIZE[Optimize Parameters]
    OPTIMIZE --> PLAN
    EVAL -->|Yes| RESULT[Output Results]
    RESULT --> LEARN[Extract Learnings]
    LEARN --> STORE[Store to Memory]
```

---

## 12. Error Recovery Flow

> **Automatic Error Handling và Escalation Paths**

```mermaid
graph TD
    ERROR[Error Detected] --> TYPE{Error Type?}
    TYPE -->|Transient| RETRY[Retry 3x with Backoff]
    TYPE -->|Quality| ENHANCE[Enhance Context]
    TYPE -->|Resource| CHECKPOINT[Save Checkpoint]
    TYPE -->|Logic| ALT[Alternative Approach]
    TYPE -->|Critical| HALT[Emergency Halt]
    RETRY --> RESUME[Resume Execution]
    ENHANCE --> FALLBACK[Use Template]
    FALLBACK --> RESUME
    CHECKPOINT --> WAIT[Wait for Resources]
    WAIT --> RESUME
    ALT --> DELEGATE[Delegate to Peer]
    DELEGATE --> RESUME
    HALT --> LOG[Log for Review]
```

---

## Quick Reference

| Tier | Mode | Workers | Pattern |
|------|------|---------|---------|
| 1 | Sequential | W01-W04 | Chain |
| 2 | Parallel | W05-W08 | Barrier |
| 3 | Parallel+Agg | W09-W14 | Aggregator |
| 4 | Parallel | W15-W18 | Barrier |
| 5 | Sequential | W19-W20 | Chain |
| 6 | Sequential | W21-W22 | Chain |

---

*Execution Flowcharts v1.1 | vnBuilderProMax v2.3.2 | Basic Mermaid Syntax*
