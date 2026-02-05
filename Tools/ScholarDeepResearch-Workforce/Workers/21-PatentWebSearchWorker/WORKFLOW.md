# W21-PatentWebSearchWorker WORKFLOW

> **Worker ID**: W21
> **Tier**: 3 - Search Acquisition
> **Agents**: 24
> **Tools**: patentSearch, WebSearchReranked

---

## Overview

Searches patent databases and non-academic web content.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive search strategy for patents/web
- Get allocated quotas

### Stage 2: Design

- Prepare patent queries
- Plan web search scope

### Stage 3: Implement

- Execute patentSearch for IP
- Execute WebSearchReranked for tech docs
- Collect results

### Stage 4: Configure

- Set jurisdiction filters (patents)
- Configure credibility checks (web)

### Stage 5: Test

- Validate patent IDs
- Check web source quality

### Stage 6: Deploy

- Merge with academic results
- Store: `results.patents[]`, `results.web[]`

---

## Use Cases

| Source | Content |
|--------|---------|
| Patents | IP, prior art |
| Web | Tech docs, blogs |

---

*W21-PatentWebSearchWorker | Tier 3 | ScholarDeepResearch-Workforce*
