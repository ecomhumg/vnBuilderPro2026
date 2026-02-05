# W11-SummarizeQuestionWorker WORKFLOW

> **Worker ID**: W11
> **Tier**: 5 - Critical Reading
> **Agents**: 24
> **Methods**: 📜 Summarize & Question, 🗝️ Key Concept Clarity, 💬 Reflective Quotation

---

## Overview

Applies summarization and questioning methods to documents.

---

## ROMA 6-Stage Pipeline

### Stage 1: Intake

- Receive fulltext documents
- Identify key sections

### Stage 2: Design

- Select applicable methods
- Plan summary structure

### Stage 3: Implement

- Generate 50+ word summaries
- Formulate 3 stimulating questions
- Extract key concepts
- Select notable quotations

### Stage 4: Configure

- Set word count minimums
- Configure question types

### Stage 5: Test

- Validate summary quality
- Check question depth

### Stage 6: Deploy

- Pass to synthesis tier
- Store: `reading.summaries[]`

---

## Output Format

```markdown
## Summary
[50+ word summary]

## Key Questions
1. [Question 1]
2. [Question 2]
3. [Question 3]

## Key Concepts
- [Concept 1]: [Explanation]

## Notable Quotations
> "[Quote]"
*Commentary: [Insight]*
```

---

*W11-SummarizeQuestionWorker | Tier 5 | ScholarDeepResearch-Workforce*
