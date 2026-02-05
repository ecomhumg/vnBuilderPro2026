# W18-CitationValidationWorker WORKFLOW

> **Worker ID**: W18
> **Tier**: 7 - Quality Validation
> **Agents**: 24

---

## Overview

Verifies citation accuracy and prevents hallucinations.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive all citations from report
- Extract DOIs and URLs

### Stage 2: Design

- Plan verification pipeline
- Prioritize by risk

### Stage 3: Implement

- Validate DOI format and resolution
- HTTP check all links
- Match metadata to sources

### Stage 4: Configure

- Set 100% DOI validity threshold
- Configure retry logic

### Stage 5: Test

- Run full validation suite
- Document failures

### Stage 6: Deploy

- Flag invalid citations
- Store: `validation.citations`

---

## Anti-Hallucination Rules

- ❌ No invented DOIs
- ❌ No fake journals
- ❌ No fabricated authors
- ❌ No dead links

---

*W18-CitationValidationWorker | Tier 7 | ScholarDeepResearch-Workforce*
