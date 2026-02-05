# W05-SourcePrioritizationWorker WORKFLOW

> **Worker ID**: W05
> **Tier**: 2 - Search Strategy  
> **Agents**: 24
> **Version**: 1.0.0

---

## Overview

Maps and prioritizes sources across 6+ academic databases.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive domain from W02
- Get search strategy from W04

### Stage 2: Design

- Rank database priority
- Allocate search quotas

### Stage 3: Implement

- Generate source priority list
- Set per-database counts
- Configure parallel execution

### Stage 4: Configure

- Define minimum diversity (≥3 sources)
- Set recency balance (50% from 5 years)

### Stage 5: Test

- Validate source coverage
- Check allocation balance

### Stage 6: Deploy

- Dispatch to Tier 3 search workers
- Store: `sources.priority[]`

---

## Source Registry

| Priority | Database | Tool | Allocation |
|----------|----------|------|------------|
| 1 | Google Scholar | advancedScholarSearch | 30% |
| 2 | ArXiv | arxivSearch | 20% |
| 3 | PubMed | searchPubMed | 20% |
| 4 | bioRxiv | biorxivSearch | 10% |
| 5 | Patents | patentSearch | 10% |
| 6 | Web | WebSearchReranked | 10% |

---

## Agent Distribution (24)

| Role | Count | Function |
|------|-------|----------|
| Priority Ranker | 8 | Database ordering |
| Quota Allocator | 8 | Count distribution |
| Diversity Monitor | 8 | Coverage validation |

---

*W05-SourcePrioritizationWorker | Tier 2 | ScholarDeepResearch-Workforce*
