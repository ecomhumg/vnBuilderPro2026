# Agent Specifications

> **528 Agents across 22 Workers**
> DeepResearch-Workforce v2.1.0

---

## Agent Architecture

Each worker contains 24 agents following ROMA 6-stage pipeline:
- **Intake (4)**: Input processing
- **Processing (4)**: Core function
- **Analysis (4)**: Domain logic
- **Validation (4)**: Quality check
- **Output (4)**: Result generation
- **Handoff (4)**: State transfer

---

## Tier 1: Research & Intelligence (72 agents)

### W01-QueryClarifierWorker
| Agent | Function |
|-------|----------|
| QC-Intake-1..4 | Parse incoming query |
| QC-Analysis-1..4 | Detect ambiguity |
| QC-Refinement-1..4 | Generate clarifications |
| QC-Validation-1..4 | Confirm clarity |
| QC-Output-1..4 | Produce refined query |
| QC-Handoff-1..4 | Transfer to W02 |

### W02-DomainIntelligenceWorker
| Agent | Function |
|-------|----------|
| DI-Intake-1..4 | Receive query |
| DI-Mapping-1..4 | Map domains |
| DI-Context-1..4 | Build context |
| DI-Expertise-1..4 | Identify experts |
| DI-Output-1..4 | Domain report |
| DI-Handoff-1..4 | Transfer to W03 |

### W03-TechnologyScanWorker
| Agent | Function |
|-------|----------|
| TS-Intake-1..4 | Receive context |
| TS-Scanning-1..4 | Scan tech landscape |
| TS-Analysis-1..4 | Assess relevance |
| TS-Trends-1..4 | Detect trends |
| TS-Output-1..4 | Tech report |
| TS-Handoff-1..4 | Transfer to Tier 2 |

---

## Tier 2: Requirements Engineering (48 agents)

### W04-ResearchProtocolWorker
| Agent | Function |
|-------|----------|
| RP-Intake-1..4 | Receive intelligence |
| RP-Methodology-1..4 | Select approach |
| RP-Protocol-1..4 | Design protocol |
| RP-Criteria-1..4 | Define metrics |
| RP-Output-1..4 | Protocol doc |
| RP-Handoff-1..4 | Human gate |

### W05-SourceStrategyWorker
| Agent | Function |
|-------|----------|
| SS-Intake-1..4 | Receive protocol |
| SS-Mapping-1..4 | Map sources |
| SS-Priority-1..4 | Rank databases |
| SS-Parameters-1..4 | Define search |
| SS-Output-1..4 | Source strategy |
| SS-Handoff-1..4 | Transfer to Tier 3 |

---

## Tier 3: Search & Acquisition (96 agents)

### W06-AcademicSearchWorker (academic-researcher)
24 agents for academic database search

### W07-TechnicalSearchWorker (technical-researcher)
24 agents for GitHub/technical research

### W08-WebSearchWorker
24 agents for web/news search

### W21-EfficiencyArchitectWorker
24 agents for efficiency optimization

---

## Tier 4-8: (312 agents)

Standard ROMA 6-stage distribution across remaining workers.

---

*Agent Specifications v1.0 | DeepResearch-Workforce*
