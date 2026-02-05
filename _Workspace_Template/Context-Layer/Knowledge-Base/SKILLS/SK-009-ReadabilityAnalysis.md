# SK-009: Readability Analysis

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Analyze and optimize content readability for Grade 7-9 level with varied sentence structure.

## Readability Metrics

| Metric | Target | How to Calculate |
|--------|--------|------------------|
| Flesch-Kincaid Grade | 7-9 | 0.39(words/sentences) + 11.8(syllables/words) - 15.59 |
| Avg Sentence Length | 15-20 words | Total words / total sentences |
| Paragraph Length | 2-4 sentences | Visual inspection |
| Active Voice | ≥80% | Active / total sentences |

## Sentence Length Variety

### Target Distribution

- Short (5-10 words): 25%
- Medium (11-20 words): 50%
- Long (21-30 words): 25%

### Rhythm Pattern

```markdown
Short. (5-10 words)
Medium sentence with more detail. (11-20 words)
Longer sentence that builds on the previous point with examples or nuance. (21-30 words)
Short again. (5-10 words)
```

## Vocabulary Guidelines

### Use | Avoid

| Simple | Complex |
|--------|---------|
| use | utilize |
| get | obtain |
| help | facilitate |
| need | require |
| show | demonstrate |
| enough | sufficient |
| about | approximately |

## Active vs Passive Voice

### Active (Preferred)

```markdown
"The lawyer reviewed the contract."
"We handle business formations daily."
"You should consult a professional."
```

### Passive (Avoid)

```markdown
"The contract was reviewed by the lawyer."
"Business formations are handled by our firm."
"A professional should be consulted."
```

## Analysis Process

1. Calculate total words
2. Count sentences
3. Calculate average sentence length
4. Measure sentence length variance
5. Count passive constructions
6. Apply Flesch-Kincaid formula

## Output

```yaml
readability_analysis:
  word_count: [number]
  sentence_count: [number]
  avg_sentence_length: [number]
  flesch_kincaid_grade: [number]
  sentence_distribution:
    short_pct: [percentage]
    medium_pct: [percentage]
    long_pct: [percentage]
  active_voice_pct: [percentage]
  issues:
    - type: "[issue type]"
      location: "[sentence/paragraph]"
      suggestion: "[fix]"
  overall_score: [1-10]
```

## Quality Criteria

- [ ] Grade level 7-9
- [ ] Sentence length varies (short/medium/long)
- [ ] Active voice ≥80%
- [ ] Paragraphs 2-4 sentences
- [ ] No complex vocabulary unnecessarily

---

*SK-009-ReadabilityAnalysis.md | v2.3.3*
