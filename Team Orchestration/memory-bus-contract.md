# Memory Bus Contract

> **MASDesign-Workforce | Cross-Worker Communication Schema**
> Enhanced with Context-Layer Integration

---

## Overview

The Memory Bus provides a shared state mechanism for cross-worker communication across the 8-tier, 22-worker MASDesign-Workforce. All keys follow the pattern `{namespace}.{domain}.{key}`.

---

## Namespaces

| Namespace | Owner | Purpose |
|-----------|-------|---------|
| `input` | User | Initial request |
| `research` | Workers 01-03 | Research & Intelligence |
| `requirements` | Workers 04-05 | Requirements Engineering |
| `architecture` | Workers 06-08, 21 | Architecture Design + Efficiency |
| `knowledge` | Workers 09-10 | Knowledge Engineering |
| `agents` | Workers 11-13 | Agent Engineering |
| `integration` | Workers 14-16 | Integration & Orchestration |
| `quality` | Workers 17-18 | Quality & Validation |
| `deployment` | Workers 19-20, 22 | Deployment & Evolution + Cost |
| `context` | Context-Layer | Context Retrieval |
| `efficiency` | W21, W22 | Efficiency Patterns |
| `memory` | Memory System | **CLAWDBOT Two-Layer Memory (NEW)** |
| `control` | Orchestrator | Control signals |
| `logs` | All | Execution logs |

---

## Key Definitions (200+ Keys)

### Input Keys

| Key | Type | Description |
|-----|------|-------------|
| `input.user_request` | string | Original user request |
| `input.domain` | string | Target domain |
| `input.constraints` | object | Project constraints |
| `input.template` | string | Template reference |

### Research Keys (Workers 01-03)

| Key | Type | Description |
|-----|------|-------------|
| `research.patterns.parsed_request` | object | Parsed pattern request |
| `research.patterns.domain_class` | string | Domain classification |
| `research.patterns.constraints` | object | Pattern constraints |
| `research.patterns.search_results` | array | Pattern search results |
| `research.patterns.match_scores` | array | Pattern match scores |
| `research.patterns.ranked_list` | array | Ranked pattern list |
| `research.patterns.analysis_summary` | object | Pattern analysis |
| `research.patterns.combinations` | array | Pattern combinations |
| `research.patterns.compatibility` | object | Compatibility matrix |
| `research.patterns.application_plan` | object | Application plan |
| `research.patterns.design_validated` | boolean | Validation status |
| `research.patterns.documentation` | string | Pattern documentation |
| `research.patterns.usage_guides` | array | Usage guidance |
| `research.patterns.examples` | array | Pattern examples |
| `research.patterns.references` | array | Pattern references |
| `research.patterns.quality_score` | float | Quality score |
| `research.patterns.approved` | boolean | Approval status |
| `research.patterns.output` | object | Final patterns output |
| `research.domain.knowledge` | object | Domain knowledge base |
| `research.domain.terminology` | object | Domain glossary |
| `research.domain.framework_mapping` | object | Framework mappings |
| `research.tech.scan_results` | array | Technology scan |
| `research.tech.trends` | array | Technology trends |
| `research.tech.recommendations` | object | Tech recommendations |

### Requirements Keys (Workers 04-05)

| Key | Type | Description |
|-----|------|-------------|
| `requirements.parsed` | object | Parsed requirements |
| `requirements.functional` | array | Functional requirements |
| `requirements.non_functional` | array | Non-functional requirements |
| `requirements.constraints` | object | Requirement constraints |
| `requirements.priorities` | object | Prioritization |
| `requirements.dependencies` | graph | Requirement dependencies |
| `requirements.validation` | object | Validation rules |
| `requirements.quality_score` | float | Quality score |
| `requirements.approved` | boolean | Approval status |
| `requirements.output` | object | Final requirements |
| `capabilities.identified` | array | Identified capabilities |
| `capabilities.mapped` | object | Capability mapping |
| `capabilities.gaps` | array | Capability gaps |
| `capabilities.priorities` | array | Prioritized capabilities |

### Architecture Keys (Workers 06-08)

| Key | Type | Description |
|-----|------|-------------|
| `architecture.swarm.selected` | string | Selected swarm type |
| `architecture.swarm.config` | object | Swarm configuration |
| `architecture.swarm.justification` | string | Selection rationale |
| `architecture.topology.graph` | object | Topology graph |
| `architecture.topology.tier_assignments` | object | Tier assignments |
| `architecture.topology.communication_paths` | array | Communication paths |
| `architecture.topology.agent_count` | integer | Total agent count |
| `architecture.topology.worker_count` | integer | Total worker count |
| `architecture.memory.schema` | object | Memory schema design |
| `architecture.memory.namespaces` | array | Namespace definitions |
| `architecture.memory.key_definitions` | array | Key definitions |
| `architecture.memory.data_flows` | array | Data flow specs |
| `architecture.quality_score` | float | Quality score |
| `architecture.approved` | boolean | Approval status |
| `architecture.output` | object | Final architecture |

### Knowledge Keys (Workers 09-10)

| Key | Type | Description |
|-----|------|-------------|
| `knowledge.playbooks.templates` | array | Playbook templates |
| `knowledge.playbooks.decision_trees` | array | Decision logic |
| `knowledge.playbooks.content` | array | Generated playbooks |
| `knowledge.skills.catalog` | array | Skills catalog |
| `knowledge.skills.documentation` | array | Skill documentation |
| `knowledge.experience.patterns` | array | Experience patterns |
| `knowledge.quality_score` | float | Quality score |
| `knowledge.approved` | boolean | Approval status |
| `knowledge.output` | object | Final knowledge base |

### Agent Keys (Workers 11-13)

| Key | Type | Description |
|-----|------|-------------|
| `agents.specifications` | array | Agent specifications |
| `agents.prompts.l6` | array | L6 prompts |
| `agents.prompts.examples` | array | Few-shot examples |
| `agents.behaviors.definitions` | array | Behavior definitions |
| `agents.behaviors.triggers` | array | Behavior triggers |
| `agents.behaviors.responses` | array | Response patterns |
| `agents.quality_score` | float | Quality score |
| `agents.approved` | boolean | Approval status |
| `agents.output` | object | Final agent specs |

### Integration Keys (Workers 14-16)

| Key | Type | Description |
|-----|------|-------------|
| `integration.orchestration.design` | object | Orchestration design |
| `integration.orchestration.workflow` | object | Workflow definition |
| `integration.orchestration.routing` | object | Routing rules |
| `integration.memory.contract` | object | Memory bus contract |
| `integration.memory.validation` | object | Contract validation |
| `integration.test.specifications` | array | Test specifications |
| `integration.test.cases` | array | Test cases |
| `integration.test.results` | array | Test results |
| `integration.quality_score` | float | Quality score |
| `integration.approved` | boolean | Approval status |
| `integration.output` | object | Final integration |

### Quality Keys (Workers 17-18)

| Key | Type | Description |
|-----|------|-------------|
| `quality.gates` | array | Quality gate definitions |
| `quality.checklists` | array | Quality checklists |
| `quality.scores` | object | Quality scores by tier |
| `quality.issues` | array | Identified issues |
| `quality.compliance.patterns` | object | Pattern compliance |
| `quality.compliance.standards` | object | Standards compliance |
| `quality.approved` | boolean | Approval status |
| `quality.output` | object | Final quality report |

### Deployment Keys (Workers 19-20)

| Key | Type | Description |
|-----|------|-------------|
| `deployment.package.structure` | object | Package structure |
| `deployment.package.manifest` | object | Deployment manifest |
| `deployment.package.artifacts` | array | Package artifacts |
| `deployment.evolution.plan` | object | Evolution plan |
| `deployment.evolution.experiments` | array | A/B experiments |
| `deployment.evolution.monitoring` | object | Monitoring config |
| `deployment.quality_score` | float | Quality score |
| `deployment.approved` | boolean | Approval status |
| `deployment.output` | object | Final deployment |

### Control Keys

| Key | Type | Description |
|-----|------|-------------|
| `control.session_id` | string | Active session |
| `control.current_tier` | integer | Current tier (1-8) |
| `control.current_worker` | string | Active worker |
| `control.status` | string | Execution status |
| `control.quality_gate` | string | Active quality gate |
| `control.error` | object | Error state |

---

## Data Flow Diagram

```mermaid\ngraph LR\n    R1[Tier 1 Research] --> R2[patterns]\n    R2 --> R3[domain]\n    R3 --> R4[tech]\n    R4 --> REQ[Tier 2 Requirements]\n    REQ --> CAP[capabilities]\n    CAP --> SWM[Tier 3 Architecture]\n    SWM --> TOP[topology]\n    TOP --> MEM[memory]\n    MEM --> KB[Tier 4-5 Knowledge + Agents]\n    KB --> INT[Tier 6 Integration]\n    INT --> QA[Tier 7 Quality]\n    QA --> DEPLOY[Tier 8 Deployment]\n```

---

## Session Management Keys (Auto-Persistence v2.0.0)

| Key | Type | Description |
|-----|------|-------------|
| `session.folder` | string | Current session folder name |
| `session.topic` | string | Original task topic |
| `session.started_at` | timestamp | Session start time |
| `session.mode` | enum | Deep/Standard/Quick |
| `session.completed_at` | timestamp | Session completion time |
| `session.duration_minutes` | integer | Total session duration |
| `session.quality_score` | float | Overall session quality |
| `phase.current` | integer | Current phase (1-8) |
| `phase.output.tier_1` | object | Tier 1 phase output |
| `phase.output.tier_2` | object | Tier 2 phase output |
| `phase.output.tier_3` | object | Tier 3 phase output |
| `phase.output.tier_4` | object | Tier 4 phase output |
| `phase.output.tier_5` | object | Tier 5 phase output |
| `phase.output.tier_6` | object | Tier 6 phase output |
| `phase.output.tier_7` | object | Tier 7 phase output |
| `phase.output.tier_8` | object | Tier 8 phase output |

---

*MASDesign-Workforce Memory Bus Contract v2.0.0 | Auto-Persistence Enhanced*
