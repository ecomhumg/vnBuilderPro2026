# PB-004: PAA Research Protocol

> **SEO-AEO-GEO-EEAT-BlogWriter** | Playbook | Strategic Procedure

---

## Purpose

Research and structure content to capture People Also Ask (PAA) positions with high-quality, extractable answers.

## PAA Question Categories

| Category | Example Pattern | Priority |
|----------|-----------------|----------|
| **Definition** | What is [X]? | High |
| **Process** | How do you [action]? | High |
| **Comparison** | What is the difference between X and Y? | Medium |
| **Cost** | How much does [X] cost? | Medium |
| **Duration** | How long does [X] take? | Medium |
| **Requirement** | Do I need [X] for [Y]? | Medium |
| **Consequence** | What happens if [X]? | Low |

## Research Process

### Step 1: Seed Query Analysis

1. Enter primary keyword in Google
2. Note all PAA questions displayed
3. Click each to expand and reveal more
4. Capture 10-15 related questions

### Step 2: Question Clustering

1. Group questions by category (above)
2. Prioritize by search volume and relevance
3. Select 4-7 for direct targeting

### Step 3: Answer Research

1. Review top 3 current answers per question
2. Identify gaps and improvements
3. Note answer format (paragraph/list/table)

## Answer Formatting

### Standard PAA Answer Template

```markdown
## [PAA Question as H2]?

[Direct answer: 40-60 words. Start with the key fact. 
No filler. Complete, extractable answer.]

### [Detail Sub-heading]

[Expanded explanation with specifics...]
```

### Answer Quality Criteria

| Criterion | Standard |
|-----------|----------|
| Length | 40-60 words for direct answer |
| Format | Starts with key fact |
| Completeness | Self-contained, extractable |
| Voice | Active, second person ("you") |
| Reading Level | Grade 7-9 |

## PAA Answer Examples

### Good Example

```markdown
## How much does a business lawyer cost in Texas?

A business lawyer in Texas typically charges $150-$400 per hour, 
or $1,500-$5,000 for flat-fee services like LLC formation or 
contract review. Rates vary based on experience, location, and 
complexity. Houston attorneys generally charge 10-20% more than 
rural areas.
```

### Bad Example

```markdown
## How much does a business lawyer cost in Texas?

That's a great question! The cost of a business lawyer can vary 
significantly depending on many factors. In this comprehensive 
guide, we'll explore everything you need to know about legal fees...
```

## Content Integration

### Structure Pattern

```markdown
# [H1 with Primary Keyword]

[Direct answer + TL;DR]

## [PAA Question 1 as H2]?
[40-60 word answer + details]

## [PAA Question 2 as H2]?
[40-60 word answer + details]

## [Logical Topic H2]
[In-depth coverage]

## [PAA Question 3 as H2]?
[40-60 word answer + details]

...

## FAQs
[3-5 additional questions NOT used as H2s]
```

## Deliverable: PAA Section

```yaml
paa_questions:
  - question: "[Question text]"
    answer: "[40-60 word answer]"
    format: paragraph/list/table
  - question: "[Question text]"
    answer: "[40-60 word answer]"
    format: paragraph/list/table
  # 4-7 total questions
```

## Quality Gates

- [ ] 4-7 PAA questions researched
- [ ] Answers are 40-60 words each
- [ ] Answers start with key fact (no filler)
- [ ] Answers are unique from FAQ section
- [ ] Question format used as H2 headings

---

*PB-004-PAAResearchProtocol.md | v2.3.3*
