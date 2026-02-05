# SK-001: Keyword & Entity Research

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Extract and validate primary keyword, secondary keywords, and entity clusters for SEO optimization.

## Input

```yaml
topic: "[Topic description]"
seed_keyword: "[Initial keyword]"
industry: "[Industry/niche]"
locale: "[Geographic focus]"
```

## Process

### Step 1: Primary Keyword Validation

1. Check search volume (minimum 100/month)
2. Assess keyword difficulty
3. Verify search intent alignment
4. Confirm topic relevance

### Step 2: Secondary Keyword Extraction

1. Generate semantic variations
2. Identify long-tail variants
3. Extract LSI (Latent Semantic Indexing) keywords
4. Target 5-12 secondary keywords

### Step 3: Entity Identification

1. Extract named entities from topic
2. Identify related entities (people, places, products)
3. Map entity relationships
4. Verify knowledge graph presence

### Step 4: Cluster Analysis

1. Group keywords by intent
2. Create topic clusters
3. Identify pillar/cluster relationships
4. Map internal linking opportunities

## Output

```yaml
keywords:
  primary:
    term: "[Keyword]"
    volume: [Number]
    difficulty: [1-100]
    intent: "[informational/commercial/transactional]"
  secondary:
    - term: "[Keyword 1]"
      type: "[variation/long-tail/lsi]"
    - term: "[Keyword 2]"
      type: "[variation/long-tail/lsi]"
    # ... 5-12 total
entities:
  primary: "[Main entity]"
  secondary:
    - name: "[Entity 1]"
      type: "[person/place/organization/concept]"
    - name: "[Entity 2]"
      type: "[person/place/organization/concept]"
clusters:
  - name: "[Cluster name]"
    keywords: ["kw1", "kw2"]
```

## Quality Criteria

- [ ] Primary keyword validated for volume/difficulty
- [ ] 5-12 secondary keywords extracted
- [ ] Named entities identified and typed
- [ ] Keyword-intent alignment verified

---

*SK-001-KeywordEntityResearch.md | v2.3.3*
