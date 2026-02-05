# SK-003: Search Intent Classification

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Classify search intent and map to buyer journey stage for content optimization.

## Intent Types

| Intent | User Goal | Content Type |
|--------|-----------|--------------|
| **Informational** | Learn/understand | Guide, explanation, how-to |
| **Commercial** | Compare/evaluate | Comparison, review, best-of |
| **Transactional** | Buy/hire/act | Landing page, service page |
| **Navigational** | Find specific page | Brand content |

## Intent Signals

### Informational Indicators

- "What is...", "How to...", "Why does..."
- "Guide", "Tutorial", "Explained"
- Question words (who, what, when, where, why, how)

### Commercial Indicators

- "Best", "Top", "vs", "comparison"
- "Review", "alternatives"
- "[Product/service] + [city/location]"

### Transactional Indicators

- "Buy", "hire", "book", "get"
- "Cost", "price", "quote"
- "Near me", "in [city]"

### Navigational Indicators

- Brand name + [product/page]
- "[Company] login", "[Company] contact"

## Buyer Journey Mapping

| Stage | Characteristics | Content Focus |
|-------|-----------------|---------------|
| **Awareness** | Just discovered problem | Education, definition |
| **Consideration** | Evaluating options | Comparison, features |
| **Decision** | Ready to act | Pricing, testimonials, CTA |

## Classification Process

### Step 1: Query Analysis

1. Extract modifier words
2. Identify question patterns
3. Check for commercial signals

### Step 2: SERP Analysis

1. Review current top 10 results
2. Note dominant content type
3. Identify featured snippet format

### Step 3: Intent Assignment

1. Primary intent (dominant)
2. Secondary intent (supporting)
3. Confidence score

## Output

```yaml
intent_classification:
  query: "[Analyzed query]"
  primary_intent: "[informational/commercial/transactional/navigational]"
  secondary_intent: "[optional secondary]"
  confidence: [0.0-1.0]
  stage: "[awareness/consideration/decision]"
  content_recommendations:
    format: "[guide/comparison/landing]"
    depth: "[comprehensive/focused]"
    cta: "[appropriate cta type]"
  serp_analysis:
    featured_snippet: "[yes/no]"
    snippet_format: "[paragraph/list/table]"
    paa_questions: ["list"]
```

---

*SK-003-SearchIntentClassification.md | v2.3.3*
