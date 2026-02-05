# Decision Matrix

> **Pattern Selection & Architecture Decision Framework**

---

## Pattern Selection Matrix

### By Problem Characteristics

| Problem Type | Primary Patterns | Secondary Patterns |
|--------------|------------------|-------------------|
| **Sequential Pipeline** | Chain-of-Thought, Plan-then-Execute | Discrete-Phase-Separation |
| **Parallel Processing** | Parallel-Tool-Execution, LLM-Map-Reduce | Distributed-Execution |
| **Research Intensive** | Agent-Driven-Research, EDR Loop | Agentic-Search-Embeddings |
| **Code Generation** | Code-First-Tool-Interface, Subagent-Compilation | Curated-Code-Context |
| **Multi-Agent Debate** | Opponent-Processor-Multi-Agent | Self-Critique-Evaluator |
| **Complex Reasoning** | Graph-of-Thoughts, LATS | Tree-of-Thought |
| **Long-Running Tasks** | Continuous-Autonomous-Loop | Extended-Coherence-Sessions |

### By Worker Count

| Worker Count | Recommended Swarm | Pattern Family |
|--------------|-------------------|----------------|
| 1-3 | SequentialWorkflow | Single-agent patterns |
| 4-8 | ConcurrentWorkflow | Parallel-Tool-Execution |
| 9-15 | HierarchicalSwarm | Sub-Agent-Spawning |
| 16-25 | SwarmRouter | Swarm-Migration |
| 26+ | HeavySwarm | Distributed-Execution |

---

## Swarm Type Decision Tree

```
START: Analyze Workforce Requirements
│
├── Is workflow strictly sequential?
│   └── YES → SequentialWorkflow
│
├── Can workers execute in parallel?
│   └── YES → ConcurrentWorkflow
│       └── More than 8 parallel workers?
│           └── YES → Consider HierarchicalSwarm
│
├── Is there a clear hierarchy?
│   └── YES → HierarchicalSwarm
│       └── More than 3 levels?
│           └── YES → Consider HeavySwarm
│
├── Need dynamic routing based on input?
│   └── YES → SwarmRouter
│
├── Research-intensive with many sources?
│   └── YES → HeavySwarm (with EDR)
│
└── DEFAULT → SwarmRouter (universal fallback)
```

---

## Architecture Decision Factors

| Factor | Weight | Scoring Criteria |
|--------|--------|------------------|
| **Complexity** | 25% | 1-5 workers (low) to 20+ (high) |
| **Parallelism** | 20% | Independent tasks vs dependencies |
| **Latency Sensitivity** | 20% | Real-time vs batch |
| **Resource Constraints** | 15% | Token limits, API costs |
| **Scalability Need** | 10% | Fixed vs growing |
| **Error Tolerance** | 10% | Critical vs retry-safe |

---

## Quick Reference: Top 10 Patterns

| Rank | Pattern | Best For |
|------|---------|----------|
| 1 | Plan-then-Execute | Standard workflows |
| 2 | Parallel-Tool-Execution | High throughput |
| 3 | Sub-Agent-Spawning | Complex decomposition |
| 4 | Graph-of-Thoughts | Reasoning tasks |
| 5 | Self-Critique-Evaluator | Quality assurance |
| 6 | Memory-Synthesis-from-Logs | Learning systems |
| 7 | Swarm-Migration | Scaling workforces |
| 8 | HITL-Approval-Framework | Human oversight |
| 9 | Skill-Library-Evolution | Adaptive systems |
| 10 | Progressive-Complexity | Gradual scaling |

---

*Decision Matrix v1.0 | MASDesign-Workforce*
