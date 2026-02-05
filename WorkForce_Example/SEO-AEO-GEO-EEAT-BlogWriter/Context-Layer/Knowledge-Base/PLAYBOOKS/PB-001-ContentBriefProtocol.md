# PB-001: Content Brief Protocol

> **SEO-AEO-GEO-EEAT-BlogWriter** | Playbook | Strategic Procedure

---

## Purpose

Resolve all input parameters and create a comprehensive content brief before article generation.

## Trigger

New content request received with topic and parameters.

## Input Requirements

| Parameter | Required | Description |
|-----------|----------|-------------|
| Topic | ✅ | Main subject of the article |
| Primary Keyword | ✅ | Target keyword for H1/meta |
| Secondary Keywords | ✅ | 5-12 supporting entities |
| Search Intent | ✅ | Informational/Commercial/Transactional/Navigational |
| Audience | ✅ | Target reader profile |
| Locale | ⬜ | Geographic focus (default: Texas) |
| Stage | ⬜ | Awareness/Consideration/Decision |
| Primary CTA | ⬜ | Call-to-action goal |
| Competitors | ⬜ | 1-3 competitor URLs to beat |
| Must-Cover | ⬜ | Required topics/entities |

## Procedure

### Step 1: Parameter Validation

1. Check all required fields are provided
2. Apply defaults for optional fields
3. Validate keyword format and intent alignment

### Step 2: Entity Extraction

1. Extract named entities from topic
2. Map secondary keywords to entity clusters
3. Identify knowledge graph connections

### Step 3: Intent Analysis

1. Classify primary search intent
2. Map to buyer journey stage
3. Determine content depth requirements

### Step 4: Competitor Gap Analysis

1. Analyze competitor content structure
2. Identify coverage gaps
3. Note differentiating opportunities

### Step 5: Brief Assembly

1. Compile all resolved inputs
2. Generate H1/H2/H3 outline suggestions
3. Define deliverable specifications

## Output

```yaml
brief:
  topic: [Resolved Topic]
  primary_keyword: [Validated Keyword]
  secondary_keywords: [5-12 entities]
  search_intent: [Intent Type]
  audience: [Target Profile]
  locale: [Geographic Focus]
  stage: [Buyer Stage]
  cta: [Primary CTA]
  competitors: [URL List]
  must_cover: [Entity List]
  outline_suggestions: [H2/H3 Structure]
  depth_requirement: [Word Count Range]
```

## Quality Gates

- [ ] All required parameters resolved
- [ ] Intent-keyword alignment verified
- [ ] Entity coverage ≥80% of must-cover list
- [ ] Outline contains ≥5 H2 sections

---

*PB-001-ContentBriefProtocol.md | v2.3.3*
