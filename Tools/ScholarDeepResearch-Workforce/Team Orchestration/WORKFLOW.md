# Team Orchestration WORKFLOW

> **ScholarDeepResearch-Workforce v2.0.0**
> 22 Workers | 528 Agents | 8-Tier HierarchicalSwarm | Dynamic Auto-Persistence

---

## Overview

| Attribute | Value |
|-----------|-------|
| **Workers** | 22 |
| **Agents** | 528 |
| **Tiers** | 8 |
| **Swarm Type** | HierarchicalSwarm |
| **Efficiency** | arXiv:2601.14192v1 |
| **Auto-Persistence** | ✅ v2.0.0 Dynamic Folders |

---

## What's New in v2.0.0

### Dynamic Session Folder Naming

Each research session now saves to a **unique folder** named after the task content:

```
PhaseOutputs/
├── 2026-01-31_ai_in_education_2024_2026/
│   ├── session-metadata.json
│   ├── phase-01-query.json
│   ├── phase-02-strategy.json
│   ├── phase-03-search.json
│   ├── phase-04-extraction.json
│   ├── phase-05-reading.json
│   ├── phase-06-analysis.json
│   ├── phase-07-validation.json
│   └── phase-08-report.json
├── 2026-01-30_llm_progress_analysis/
│   └── ...
└── _legacy/
    └── (archived pre-v2.0 files)
```

**Naming format:** `{YYYY-MM-DD}_{sanitized_topic}`

---

## Execution Flow with Dynamic Session Folders

```mermaid
flowchart TD
    subgraph Tier1[Tier 1: Query & Intelligence]
        W1[01-QueryClarification]
        W2[02-DomainClassification]
        W3[03-MultimodalProcessing]
    end
    T1Save[📁 CREATE: {date}_{topic}/]
    T1Phase[💾 phase-01-query.json]
  
    subgraph Tier2[Tier 2: Search Strategy]
        W4[04-SearchStrategy]
        W5[05-SourcePrioritization]
    end
    T2Save[💾 phase-02-strategy.json]
  
    subgraph Tier3[Tier 3: Search Acquisition]
        W6[06-AdvancedScholarSearch]
        W7[07-ArxivSearch]
        W8[08-BiomedicalSearch]
        W21[21-PatentWebSearch]
    end
    T3Save[💾 phase-03-search.json]
  
    subgraph Tier4[Tier 4: Content Extraction]
        W9[09-ContentExtraction]
        W10[10-DatasetProcessing]
    end
    T4Save[💾 phase-04-extraction.json]
  
    subgraph Tier5[Tier 5: Critical Reading]
        W11[11-SummarizeQuestion]
        W12[12-CriticalInquiry]
        W13[13-ContrastAnalysis]
        W14[14-StructureVisualization]
    end
    T5Save[💾 phase-05-reading.json]
  
    subgraph Tier6[Tier 6: Analysis & Synthesis]
        W15[15-DataAnalysis]
        W16[16-Visualization]
        W17[17-FactCheck]
    end
    T6Save[💾 phase-06-analysis.json]
  
    subgraph Tier7[Tier 7: Quality Validation]
        W18[18-CitationValidation]
        W19[19-QualityAssurance]
    end
    T7Save[💾 phase-07-validation.json]
  
    subgraph Tier8[Tier 8: Delivery & Evolution]
        W20[20-ReportGeneration]
        W22[22-EvolutionEfficiency]
    end
    T8Save[💾 phase-08-report.json]
    T8Meta[📋 session-metadata.json]
  
    Tier1 --> T1Save --> T1Phase --> Tier2 --> T2Save --> Tier3 --> T3Save --> Tier4 --> T4Save --> Tier5 --> T5Save --> Tier6 --> T6Save --> Tier7 --> T7Save --> Tier8 --> T8Save --> T8Meta
```

---

## Dynamic Session Folder Generation

| Trigger | Action |
|---------|--------|
| **After Tier 1** | Extract `research_topic` from Memory Bus |
| | Generate slug: lowercase, replace spaces, remove special chars |
| | Create folder: `{YYYY-MM-DD}_{slug}` |
| **Each Phase** | Save to `PhaseOutputs/{session_folder}/phase-XX-*.json` |
| **After Tier 8** | Create `session-metadata.json` with summary |

### Naming Examples

| Research Topic | Session Folder |
|----------------|----------------|
| AI in Education (2024-2026) | `2026-01-31_ai_in_education_2024_2026` |
| LLM Progress: Recent Advances | `2026-01-30_llm_progress_recent_advances` |
| Climate Change Policy Analysis | `2026-01-29_climate_change_policy_analysis` |

---

## Worker Registry

| Tier | # | Worker | Agents | Tools |
|------|---|--------|--------|-------|
| 1 | 01 | QueryClarificationWorker | 24 | - |
| 1 | 02 | DomainClassificationWorker | 24 | - |
| 1 | 03 | MultimodalProcessingWorker | 24 | Vision |
| 2 | 04 | SearchStrategyWorker | 24 | - |
| 2 | 05 | SourcePrioritizationWorker | 24 | - |
| 3 | 06 | AdvancedScholarSearchWorker | 24 | advancedScholarSearch, scholarSearch |
| 3 | 07 | ArxivSearchWorker | 24 | arxivSearch, arxivFulltext |
| 3 | 08 | BiomedicalSearchWorker | 24 | searchPubMed, biorxivSearch |
| 3 | 21 | PatentWebSearchWorker | 24 | patentSearch, WebSearchReranked |
| 4 | 09 | ContentExtractionWorker | 24 | extractUrl |
| 4 | 10 | DatasetProcessingWorker | 24 | extractUrl |
| 5 | 11 | SummarizeQuestionWorker | 24 | Methods 1, 4, 7 |
| 5 | 12 | CriticalInquiryWorker | 24 | Methods 2, 9 |
| 5 | 13 | ContrastAnalysisWorker | 24 | Methods 3, 6 |
| 5 | 14 | StructureVisualizationWorker | 24 | Methods 5, 10 |
| 6 | 15 | DataAnalysisWorker | 24 | code_interpreter |
| 6 | 16 | VisualizationWorker | 24 | code_interpreter, image_gen |
| 6 | 17 | FactCheckWorker | 24 | Method 8 |
| 7 | 18 | CitationValidationWorker | 24 | - |
| 7 | 19 | QualityAssuranceWorker | 24 | - |
| 8 | 20 | ReportGenerationWorker | 24 | image generation |
| 8 | 22 | EvolutionEfficiencyWorker | 24 | §3-6 patterns |

---

## Auto-Persistence Configuration

| Tier | Output File | Memory Keys | Session Folder |
|------|-------------|-------------|----------------|
| 1 | phase-01-query.json | query.*, input.multimodal | **✅ Creates** |
| 2 | phase-02-strategy.json | search.strategy, sources.* | Uses existing |
| 3 | phase-03-search.json | results.* | Uses existing |
| 4 | phase-04-extraction.json | content.*, datasets.* | Uses existing |
| 5 | phase-05-reading.json | reading.* | Uses existing |
| 6 | phase-06-analysis.json | analysis.*, visuals.*, verification.* | Uses existing |
| 7 | phase-07-validation.json | validation.*, quality.* | Uses existing |
| 8 | phase-08-report.json | output.report, efficiency.* | **✅ Metadata** |

**Storage**: `Context-Layer/Second-Brain/Memory/PhaseOutputs/{session_folder}/`

---

## Session Metadata

At the end of each session, a `session-metadata.json` is created:

```json
{
    "session_folder": "2026-01-31_ai_in_education_2024_2026",
    "research_topic": "AI in Education (2024-2026)",
    "mode": "Deep",
    "started_at": "2026-01-31T12:40:00+07:00",
    "completed_at": "2026-01-31T13:15:00+07:00",
    "duration_minutes": 35,
    "total_phases": 8,
    "quality_score": 0.92,
    "workforce_version": "2.0.0"
}
```

---

## Quality Gates

| Gate | Location | Threshold |
|------|----------|-----------|
| Source Diversity | After Tier 3 | ≥3 databases |
| Fulltext Coverage | After Tier 4 | ≥80% |
| Citation Validity | After Tier 7 | 100% |
| E-O Score | After Tier 7 | ≥0.85 |

---

## Error Handling

1. Worker failure → Retry 2x with backoff
2. Quality gate failure → Return to previous tier
3. Critical error → Human escalation
4. **Session recovery** → Restore from session folder's last phase output

---

## Browsing Sessions

List all saved sessions:

```bash
ls Context-Layer/Second-Brain/Memory/PhaseOutputs/
```

View specific session:

```bash
cat "PhaseOutputs/2026-01-31_ai_in_education_2024_2026/session-metadata.json"
```

---

*Team Orchestration WORKFLOW | ScholarDeepResearch-Workforce v2.0.0*
