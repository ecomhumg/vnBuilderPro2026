# W10-DatasetProcessingWorker WORKFLOW

> **Worker ID**: W10
> **Tier**: 4 - Content Extraction
> **Agents**: 24
> **Tools**: extractUrl

---

## Overview

Processes dataset links and file parsing for data-driven research.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive dataset URLs
- Identify file types

### Stage 2: Design

- Plan parsing strategy
- Map to data formats

### Stage 3: Implement

- Download and parse datasets
- Extract structured data

### Stage 4: Configure

- Set parsing parameters
- Configure data validation

### Stage 5: Test

- Validate data integrity
- Check structure consistency

### Stage 6: Deploy

- Pass to analysis workers
- Store: `datasets.processed[]`

---

## Supported Formats

| Format | Parsing |
|--------|---------|
| CSV | pandas read_csv |
| JSON | json load |
| Excel | pandas read_excel |
| TSV | pandas read_csv |

---

*W10-DatasetProcessingWorker | Tier 4 | ScholarDeepResearch-Workforce*
