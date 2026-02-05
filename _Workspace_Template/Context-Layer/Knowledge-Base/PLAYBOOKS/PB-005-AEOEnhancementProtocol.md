# PB-005: AEO Enhancement Protocol

> **SEO-AEO-GEO-EEAT-BlogWriter** | Playbook | Strategic Procedure

---

## Purpose

Optimize content for Answer Engine Optimization (AEO) to maximize visibility in AI Overviews, ChatGPT, Perplexity, and voice assistants.

## AEO vs Traditional SEO

| Aspect | Traditional SEO | AEO |
|--------|-----------------|-----|
| **Goal** | Click-through to website | Be the cited answer |
| **Queries** | Keyword phrases | Conversational questions |
| **Metrics** | Rankings, CTR | Citations, zero-click visibility |
| **Format** | Any readable format | Extractable structured content |

## Voice Search Optimization

### Conversational Query Patterns

```
How do I...?
What is the best way to...?
Can you explain...?
Where can I find...?
Why does [X] happen?
```

### Voice-Ready Content Rules

1. **Natural Language**: Write as if speaking aloud
2. **Full Questions**: Use complete question format in H2s
3. **Concise Answers**: 40-60 words for immediate extraction
4. **Second Person**: Use "you/your" not "one/users"
5. **Local Context**: Include geographic specifics when relevant

## Extractive Answer Formatting

### Lists for Steps/Procedures

```markdown
## How to [Action]?

To [achieve outcome], follow these steps:

1. **[Action verb]** - [Brief explanation]
2. **[Action verb]** - [Brief explanation]
3. **[Action verb]** - [Brief explanation]
```

### Tables for Comparisons

```markdown
## [Comparison Question]?

| [Factor] | [Option A] | [Option B] |
|----------|------------|------------|
| Cost | $X | $Y |
| Time | X hours | Y hours |
| Best for | [Use case] | [Use case] |
```

### Definitions for "What is" Queries

```markdown
## What is [Term]?

[Term] is [category] that [function/purpose]. It is used for 
[primary application] and helps [benefit]. Key characteristics 
include [feature 1], [feature 2], and [feature 3].
```

## AI Overview Optimization

### Content Structure for SGE

1. **Definitive Answers**: State facts clearly, not hedged opinions
2. **Structured Data**: Use schema markup (Article, FAQ, HowTo)
3. **Clear Hierarchy**: H1 → H2 → H3 logical flow
4. **Short Paragraphs**: 2-4 sentences per paragraph
5. **Factual Tone**: Authoritative, not conversational

### Citation-Worthy Signals

- Include original data/research
- Cite authoritative sources
- Use specific numbers and statistics
- Provide unique insights not elsewhere

## Structured Data Requirements

### FAQ Schema Template

```json
{
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[Question text]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[40-60 word answer]"
      }
    }
  ]
}
```

### HowTo Schema Template

```json
{
  "@type": "HowTo",
  "name": "[How to title]",
  "step": [
    {
      "@type": "HowToStep",
      "name": "[Step title]",
      "text": "[Step instruction]"
    }
  ]
}
```

## Content Audit Checklist

### Voice Search Ready

- [ ] H2s are natural questions
- [ ] Answers are 40-60 words
- [ ] Content reads well aloud
- [ ] Uses "you/your" language

### AI Extraction Ready

- [ ] Clear list/table formatting
- [ ] Definitive answers (not hedged)
- [ ] Specific numbers/statistics
- [ ] Schema markup implemented

### Citation Ready

- [ ] Original insights included
- [ ] Authoritative sources cited
- [ ] Clear, structured format
- [ ] Entity consistency maintained

---

*PB-005-AEOEnhancementProtocol.md | v2.3.3*
