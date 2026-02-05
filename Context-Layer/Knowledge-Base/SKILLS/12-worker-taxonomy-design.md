---
always: false
tier: [1,2]
description: "Domain-specific worker naming, tier assignment, and tool mapping patterns"
core_modules: [SubagentManager]
---

# SKILL: Worker Taxonomy Design

> **Purpose**: Domain-specific worker naming, tier assignment, and tool mapping patterns.

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Input** | Domain requirements |
| **Output** | Worker taxonomy with tier assignments |
| **Standard** | 24 agents per worker |

---

## Worker Naming Convention

### Pattern

```
{NN}-{FunctionName}Worker
```

### Components

| Component | Description | Example |
|-----------|-------------|---------|
| `NN` | 2-digit sequence number | `01`, `02`, `22` |
| `FunctionName` | PascalCase function | `QueryClarification` |
| `Worker` | Suffix (always) | `Worker` |

### Examples

| Domain | Worker Names |
|--------|--------------|
| Research | `01-QueryClarificationWorker`, `06-AdvancedScholarSearchWorker` |
| Operations | `01-InputValidationWorker`, `05-TransformationWorker` |
| Analytics | `01-DataIngestionWorker`, `12-DashboardVisualizationWorker` |

---

## 8-Tier Assignment Rules

### Tier Functions

| Tier | Function | Worker Focus |
|------|----------|--------------|
| 1 | Intelligence | Input processing, classification |
| 2 | Strategy | Planning, prioritization |
| 3 | Acquisition | Data gathering, search |
| 4 | Processing | Transformation, extraction |
| 5 | Analysis | Core domain logic |
| 6 | Synthesis | Aggregation, visualization |
| 7 | Validation | Quality, compliance |
| 8 | Delivery | Output, evolution |

### Worker Distribution

| Tier | Recommended Workers | Agent Count |
|------|---------------------|-------------|
| 1 | 2-3 | 48-72 |
| 2 | 2 | 48 |
| 3 | 3-4 | 72-96 |
| 4 | 2 | 48 |
| 5 | 3-4 | 72-96 |
| 6 | 2-3 | 48-72 |
| 7 | 2 | 48 |
| 8 | 2-3 | 48-72 |

---

## Tool Mapping by Domain

### Research Domain

| Worker | Tools |
|--------|-------|
| AdvancedScholarSearch | `advancedScholarSearch`, `scholarSearch` |
| ArxivSearch | `arxivSearch`, `arxivFulltext` |
| BiomedicalSearch | `searchPubMed`, `biorxivSearch` |
| ContentExtraction | `extractUrl` |
| DataAnalysis | `code_interpreter` |
| Visualization | `code_interpreter`, `image_gen` |

### Operations Domain

| Worker | Tools |
|--------|-------|
| DataIngestion | `file_read`, `api_call` |
| Transformation | `code_interpreter` |
| Monitoring | `metrics_collector` |
| Alerting | `notification_send` |

### Analytics Domain

| Worker | Tools |
|--------|-------|
| DataIngestion | `database_query`, `file_read` |
| StatisticalAnalysis | `code_interpreter` |
| Visualization | `chart_generator`, `dashboard_builder` |
| Reporting | `document_generator` |

---

## Worker WORKFLOW Template

```markdown
# {WorkerName} WORKFLOW

> **Tier {N}**: {Tier Name}

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Worker** | {NN}-{WorkerName} |
| **Tier** | {N} |
| **Agents** | 24 |
| **Tools** | {Tool list} |

---

## Execution Flow

1. **Input**: Receive from Memory Bus
2. **Process**: {Domain-specific processing}
3. **Output**: Write to Memory Bus

---

## Memory Bus Keys

| Key | Type | Description |
|-----|------|-------------|
| `{prefix}.input` | object | Input from previous tier |
| `{prefix}.output` | object | Output to next tier |

---

*{WorkerName} WORKFLOW | {DomainName}-Workforce*
```

---

## Efficiency Workers (arXiv:2601.14192v1)

Always include these efficiency workers:

| ID | Worker | Tier | Purpose |
|----|--------|------|---------|
| 21 | EfficiencyArchitectWorker | 3 | Memory/Tool/Planning optimization |
| 22 | CostBudgetOptimizationWorker | 8 | Cost tracking, Pareto optimization |

---

*SKILL v2.0.0 | Worker Taxonomy Design | MASDesign-Workforce*
