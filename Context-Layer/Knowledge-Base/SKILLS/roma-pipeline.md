---
vnbuilder:
  name: roma-pipeline
  description: 6-Stage ROMA worker execution pipeline (Role-Orchestration-Methods-Activation)
  version: "2.0.0"
  always: true
  tier: [1,2,3,4,5,6,7,8]
---

# ROMA Pipeline Skills

> **6-Stage Recursive Open Meta-Agent Implementation**
> **CoreModules Integration**: AgentLoop, MemoryStore

---

## ROMA Stages

| Stage | Purpose | Key Activities |

|-------|---------|----------------|
| **INTAKE** | Parse & route | Validate input, classify, route |
| **ANALYZE** | Understand | Pattern match, score, synthesize |
| **DESIGN** | Architect | Plan structure, define components |
| **IMPLEMENT** | Build | Generate artifacts, write content |
| **VALIDATE** | Check | Test quality, verify correctness |
| **DELIVER** | Output | Package, document, handoff |

---

## Stage Flow

```
       ┌─────────────────────────────────────────┐
       │              Orchestrator               │
       └────────────────────┬────────────────────┘
                            │
    ┌───────┬───────┬───────┼───────┬───────┬───────┐
    ▼       ▼       ▼       ▼       ▼       ▼       │
 INTAKE → ANALYZE → DESIGN → IMPLEMENT → VALIDATE → DELIVER
    │              ▲                              │
    └──────────────┴──────── (feedback loop) ─────┘
```

---

## Agent Distribution (24 per Worker)

| Stage | Agents | Roles |
|-------|--------|-------|
| INTAKE | 4 | InputParser, InputValidator, RequestClassifier, TaskRouter |
| ANALYZE | 4 | DomainAnalyzer, PatternMatcher, RequirementScorer, AnalysisSynthesizer |
| DESIGN | 4 | SolutionDesigner, ComponentArchitect, DependencyPlanner, DesignValidator |
| IMPLEMENT | 4 | ContentGenerator, SpecWriter, FormatProcessor, ReferenceLinker |
| VALIDATE | 4 | QualityChecker, IntegrationTester, ConstraintValidator, ApprovalGate |
| DELIVER | 4 | OutputPackager, DocumentationWriter, HandoffManager, ExecutionLogger |

---

*ROMA Pipeline Skills v1.0 | MASDesign-Workforce*
