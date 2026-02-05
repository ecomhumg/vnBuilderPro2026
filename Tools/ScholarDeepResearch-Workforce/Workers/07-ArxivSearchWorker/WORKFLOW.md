# W07-ArxivSearchWorker WORKFLOW

> **Worker ID**: W07
> **Tier**: 3 - Search Acquisition
> **Agents**: 24
> **Tools**: arxivSearch, arxivFulltext

---

## Overview

Searches arXiv preprint repository for CS, Physics, Math, and related fields.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive search strategy
- Check domain priority

### Stage 2: Design

- Map to arXiv categories
- Prepare API query

### Stage 3: Implement

- Execute arxivSearch
- Use arxivFulltext for PDF access

### Stage 4: Configure

- Set max_results
- Apply category filters

### Stage 5: Test

- Validate arXiv IDs
- Check PDF availability

### Stage 6: Deploy

- Merge with other results
- Store: `results.arxiv[]`

---

## ArXiv Categories

| Field | Categories |
|-------|------------|
| Machine Learning | cs.LG, stat.ML |
| AI | cs.AI, cs.CL |
| Physics | physics.*, hep-* |
| Mathematics | math.* |

---

*W07-ArxivSearchWorker | Tier 3 | ScholarDeepResearch-Workforce*
