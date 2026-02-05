# SK-006: AEO Answer Formatting

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Format content for optimal extraction by AI Overview, voice assistants, and answer engines.

## Answer Types

| Query Type | Format | Length |
|------------|--------|--------|
| What is... | Definition paragraph | 40-60 words |
| How to... | Numbered steps | 4-8 steps |
| Best/Top... | Bulleted list | 5-10 items |
| X vs Y | Comparison table | 3-5 rows |
| How much... | Direct + range | 40-60 words |

## Definition Format

```markdown
## What is [Term]?

[Term] is a [category] that [primary function]. It is used for 
[main application] and helps [key benefit]. In [context/location], 
[Term] typically involves [specific detail]. Key characteristics 
include [feature 1], [feature 2], and [feature 3].
```

## How-To Format

```markdown
## How to [Action]?

To [achieve outcome], follow these [number] steps:

1. **[Verb] [object]** — [Brief explanation]
2. **[Verb] [object]** — [Brief explanation]
3. **[Verb] [object]** — [Brief explanation]
4. **[Verb] [object]** — [Brief explanation]
```

## List Format

```markdown
## [Number] Best [Items] for [Use Case]

Top [items] to consider:

- **[Item 1]**: [One-line description]
- **[Item 2]**: [One-line description]
- **[Item 3]**: [One-line description]
- **[Item 4]**: [One-line description]
- **[Item 5]**: [One-line description]
```

## Comparison Table Format

```markdown
## [X] vs [Y]: [Comparison Question]?

| Feature | [Option X] | [Option Y] |
|---------|------------|------------|
| Cost | [Value] | [Value] |
| Time | [Value] | [Value] |
| Best For | [Use case] | [Use case] |
| Pros | [Key advantage] | [Key advantage] |
```

## Voice Search Optimization

### Natural Language Rules

1. Write as if answering verbally
2. Use complete sentences
3. Avoid abbreviations
4. Include "you/your" pronouns
5. Start with the answer, not context

### Read-Aloud Test

Content should sound natural when read aloud:

```markdown
❌ "The aforementioned LLC formation process involves..."
✅ "Forming an LLC in Texas takes about two weeks..."
```

## Extractability Checklist

- [ ] Answer appears in first 2 sentences
- [ ] Uses structured format (list/table/steps)
- [ ] Complete, self-contained answer
- [ ] Natural spoken language
- [ ] No filler phrases
- [ ] Specific numbers/data included

## Output

```yaml
aeo_content:
  query_type: "[definition/howto/list/comparison/number]"
  format_used: "[paragraph/steps/bullets/table]"
  answer_length: [word count]
  extractable: [yes/no]
  voice_ready: [yes/no]
  content: "[Formatted answer]"
```

---

*SK-006-AEOAnswerFormatting.md | v2.3.3*
