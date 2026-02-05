# W06-AdvancedScholarSearchWorker WORKFLOW

> **Worker ID**: W06
> **Tier**: 3 - Search Acquisition
> **Agents**: 24
> **Tools**: advancedScholarSearch, scholarSearch

---

## Overview

Executes Google Scholar searches with AI reranking.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive search strategy from W04
- Get allocated count from W05

### Stage 2: Design

- Select tool (advancedScholarSearch vs scholarSearch)
- Prepare query parameters

### Stage 3: Implement

- Execute advancedScholarSearch for broad queries
- Execute scholarSearch for exact titles
- Collect results

### Stage 4: Configure

- Apply reranking filters
- Set result limit (default: 20)

### Stage 5: Test

- Validate result quality
- Check relevance scores

### Stage 6: Deploy

- Pass results to consolidation
- Store: `results.scholar[]`

---

## Tool Selection

| Scenario | Tool |
|----------|------|
| Broad query | advancedScholarSearch |
| Exact title | scholarSearch |
| Citation lookup | scholarSearch |

---

*W06-AdvancedScholarSearchWorker | Tier 3 | ScholarDeepResearch-Workforce*
