# W17-FactCheckWorker WORKFLOW

> **Worker ID**: W17
> **Tier**: 6 - Analysis & Synthesis
> **Agents**: 24
> **Methods**: ❌ Fact Check

---

## Overview

Verifies factual accuracy and identifies inaccuracies.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive claims to verify
- Extract factual statements

### Stage 2: Design

- Plan verification approach
- Identify sources

### Stage 3: Implement

- Cross-reference with sources
- Identify discrepancies
- List inaccuracies

### Stage 4: Configure

- Set verification strictness
- Configure evidence requirements

### Stage 5: Test

- Validate verification quality
- Check source reliability

### Stage 6: Deploy

- Flag inaccuracies
- Store: `verification.facts[]`

---

## Verification Levels

| Level | Evidence Required |
|-------|-------------------|
| High | 2+ independent sources |
| Medium | 1 reliable source |
| Low | Plausibility check |

---

*W17-FactCheckWorker | Tier 6 | ScholarDeepResearch-Workforce*
