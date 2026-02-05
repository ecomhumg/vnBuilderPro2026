# W04-SearchStrategyWorker WORKFLOW

> **Worker ID**: W04
> **Tier**: 2 - Search Strategy
> **Agents**: 24
> **Version**: 1.0.0

---

## Overview

Designs comprehensive search protocols and keyword engineering strategies.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive domain classification
- Get clarified query

### Stage 2: Design

- Engineer search keywords
- Design Boolean queries
- Plan database coverage

### Stage 3: Implement

- Generate query variants
- Create database-specific queries
- Set search parameters

### Stage 4: Configure

- Configure result counts (min 20)
- Set date filters
- Define quality filters

### Stage 5: Test

- Validate query syntax
- Check database compatibility

### Stage 6: Deploy

- Dispatch to search workers
- Store: `search.strategy`

---

## Query Engineering

| Technique | Example |
|-----------|---------|
| Phrase Match | "machine learning" |
| Boolean AND | term1 AND term2 |
| Boolean OR | term1 OR synonym |
| Exclusion | -unwanted |
| Wildcards | optim* |

---

## Agent Distribution (24)

| Role | Count | Function |
|------|-------|----------|
| Keyword Engineer | 8 | Search term optimization |
| Query Builder | 8 | Boolean query construction |
| Strategy Optimizer | 8 | Coverage maximization |

---

*W04-SearchStrategyWorker | Tier 2 | ScholarDeepResearch-Workforce*
