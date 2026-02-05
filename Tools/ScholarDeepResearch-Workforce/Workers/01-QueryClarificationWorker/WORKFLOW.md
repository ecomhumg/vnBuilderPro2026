# W01-QueryClarificationWorker WORKFLOW

> **Worker ID**: W01
> **Tier**: 1 - Query & Intelligence
> **Agents**: 24
> **Version**: 1.0.0

---

## Overview

Parses and disambiguates research queries for optimal search execution.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive user query
- Extract multimodal inputs (text, images, files)
- Log query metadata

### Stage 2: Design

- Identify ambiguous terms
- Classify research domain
- Determine intent (search, analysis, summary)

### Stage 3: Implement

- Parse query into structured format
- Generate Boolean search strings
- Map to database priorities

### Stage 4: Configure

- Set search parameters
- Define result count (default: 20)
- Configure timeframe filters

### Stage 5: Test

- Validate query structure
- Check for common errors
- Verify domain classification

### Stage 6: Deploy

- Pass clarified query to downstream workers
- Store in Memory Bus: `query.clarified`

---

## Agent Distribution (24)

| Role | Count | Function |
|------|-------|----------|
| Query Parser | 6 | Text extraction and tokenization |
| Domain Classifier | 6 | Research field identification |
| Intent Analyzer | 6 | Goal classification |
| Output Formatter | 6 | Structured output generation |

---

## Memory Bus Keys

| Key | Type | Direction |
|-----|------|-----------|
| `query.original` | String | IN |
| `query.clarified` | Object | OUT |
| `query.domain` | String | OUT |
| `query.intent` | String | OUT |

---

*W01-QueryClarificationWorker | Tier 1 | ScholarDeepResearch-Workforce*
