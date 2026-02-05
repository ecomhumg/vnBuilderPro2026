# W19-QualityAssuranceWorker WORKFLOW

> **Worker ID**: W19
> **Tier**: 7 - Quality Validation
> **Agents**: 24

---

## Overview

Enforces academic integrity and quality standards.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive complete research output
- Extract quality metrics

### Stage 2: Design

- Plan quality assessment
- Map to standards

### Stage 3: Implement

- Check source diversity (≥8 sources)
- Verify summary lengths (≥50 words)
- Assess citation accuracy (100%)
- Calculate E-O score

### Stage 4: Configure

- Set E-O threshold (≥0.85)
- Configure quality gates

### Stage 5: Test

- Run quality checklist
- Validate scores

### Stage 6: Deploy

- Pass/Fail decision
- Store: `quality.score`

---

## Quality Gates

| Metric | Threshold |
|--------|-----------|
| Sources | ≥8 academic |
| Summaries | ≥50 words each |
| Citations | 100% valid |
| E-O Score | ≥0.85 |

---

*W19-QualityAssuranceWorker | Tier 7 | ScholarDeepResearch-Workforce*
