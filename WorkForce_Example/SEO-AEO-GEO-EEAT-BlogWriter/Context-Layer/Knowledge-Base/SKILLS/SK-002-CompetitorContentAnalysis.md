# SK-002: Competitor Content Analysis

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Analyze competitor content to identify gaps, opportunities, and differentiation strategies.

## Input

```yaml
keyword: "[Target keyword]"
competitors:
  - url: "[Competitor URL 1]"
  - url: "[Competitor URL 2]"
  - url: "[Competitor URL 3]"
```

## Analysis Framework

### Content Structure Analysis

| Element | Capture |
|---------|---------|
| H1 | Exact heading |
| H2 count | Number of sections |
| H2 topics | List of all H2s |
| Word count | Total words |
| Images | Count and alt text presence |
| Tables/Lists | Count |

### E-E-A-T Signals

| Signal | Present? |
|--------|----------|
| Author bio | Y/N |
| Credentials | Y/N |
| Citations | Y/N |
| Date published | Y/N |
| Date updated | Y/N |

### Content Quality

| Factor | Score (1-10) |
|--------|--------------|
| Depth | |
| Originality | |
| Readability | |
| Visual aids | |
| Actionable | |

## Gap Analysis

### Coverage Gaps

```yaml
missing_topics:
  - "[Topic not covered by competitors]"
  - "[Important question unanswered]"
```

### Depth Gaps

```yaml
shallow_coverage:
  - topic: "[Topic covered superficially]"
    opportunity: "[How to go deeper]"
```

### Format Gaps

```yaml
format_opportunities:
  - type: "table"
    topic: "[Comparison not in table form]"
  - type: "video"
    topic: "[Complex topic needing visual]"
```

## Differentiation Strategy

### Unique Value Propositions

1. **Local expertise**: Texas/Houston-specific insights
2. **First-hand experience**: Real case studies
3. **Deeper analysis**: More comprehensive coverage
4. **Better format**: Tables, step-by-step, visuals
5. **Updated information**: More recent data/laws

## Output

```yaml
competitor_analysis:
  top_performer:
    url: "[URL]"
    strengths: ["list"]
    weaknesses: ["list"]
  gaps:
    content: ["list"]
    format: ["list"]
    trust: ["list"]
  differentiation:
    primary: "[Main differentiator]"
    secondary: ["list"]
  recommendations:
    structure: "[H1/H2 suggestion]"
    depth: "[Word count target]"
    unique_angle: "[How to stand out]"
```

---

*SK-002-CompetitorContentAnalysis.md | v2.3.3*
