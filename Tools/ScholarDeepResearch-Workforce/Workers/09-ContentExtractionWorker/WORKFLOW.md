# W09-ContentExtractionWorker WORKFLOW

> **Worker ID**: W09
> **Tier**: 4 - Content Extraction
> **Agents**: 24
> **Tools**: extractUrl

---

## Overview

Extracts fulltext content from URLs and documents.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive paper URLs from search results
- Prioritize fulltext needs

### Stage 2: Design

- Select extraction strategy
- Plan fallback chain

### Stage 3: Implement

- Execute extractUrl on each URL
- Handle various formats (HTML, PDF)

### Stage 4: Configure

- Set timeout limits
- Configure retry logic

### Stage 5: Test

- Validate extraction completeness
- Check content quality

### Stage 6: Deploy

- Pass fulltext to analysis workers
- Store: `content.fulltext[]`

---

## Fallback Chain

1. extractUrl (primary)
2. Platform-specific fulltext tool
3. Search for alternative source

---

*W09-ContentExtractionWorker | Tier 4 | ScholarDeepResearch-Workforce*
