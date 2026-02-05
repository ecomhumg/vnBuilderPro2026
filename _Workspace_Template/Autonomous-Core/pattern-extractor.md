# Pattern Extractor - Content Pattern Mining

> **SEO-AEO-GEO-EEAT-BlogWriter** | Autonomous-Core | vnBuilderProMax v2.3.3

---

## Core Identity

| Attribute | Value |
|-----------|-------|
| **Type** | L5 Pattern Mining Engine |
| **Trigger** | Post-delivery (high-quality content) |
| **Threshold** | Quality score ≥ 85 |
| **Output** | Reusable content patterns |

---

## Pattern Categories

| Category | Examples |
|----------|----------|
| **Structure** | H1/H2/H3 hierarchy, section flow |
| **SEO** | Keyword placement, meta patterns |
| **E-E-A-T** | Expert signals, trust indicators |
| **AEO** | Featured snippet formats, PAA patterns |
| **Voice** | Tone patterns, active voice structures |
| **Engagement** | Hook styles, CTA patterns |

---

## Extraction Logic

```
ON High_Quality_Delivery (score >= 85):
    
    1. LOAD content.integrated.final
    
    2. EXTRACT Structure Patterns:
        - H1 format (question/statement/how-to)
        - H2 count and naming patterns
        - Section length distribution
        - Intro/conclusion patterns
    
    3. EXTRACT SEO Patterns:
        - Primary keyword position (H1, first 100 words)
        - Secondary keyword distribution
        - Meta title/description templates
        - URL slug patterns
    
    4. EXTRACT E-E-A-T Patterns:
        - Expert citation patterns
        - Trust signal placements
        - Authority indicator formats
        - Experience demonstration styles
    
    5. EXTRACT AEO Patterns:
        - Featured snippet candidates
        - Definition box patterns
        - List/table optimization
        - PAA question-answer formats
    
    6. EXTRACT Engagement Patterns:
        - Opening hook styles
        - CTA placements and formats
        - Internal linking patterns
        - Visual break patterns
    
    7. SCORE each pattern by:
        - Quality contribution (0-100)
        - Reusability (0-100)
        - Domain specificity (low/medium/high)
    
    8. WRITE patterns to Learning/patterns.md
    
    9. UPDATE pattern index with metadata
```

---

## Pattern Schema

```yaml
pattern_id: "h1-question-how-to"
category: "structure"
type: "h1_format"
template: "How to [ACTION] [OBJECT] in [CONTEXT]"
examples:
  - "How to File Taxes in Texas as a Small Business"
  - "How to Navigate Employment Law in Houston"
quality_contribution: 85
reusability: 92
domain_specificity: "medium"
success_rate: 0.89
usage_count: 15
promoted: true
created_at: "2026-02-01"
last_used: "2026-02-05"
```

---

## Pattern Categories Detail

### Structure Patterns

```
PATTERN: intro-tldr-first
TEMPLATE: |
  [TL;DR: Single sentence summary]
  
  [Problem statement paragraph]
  
  [Solution preview paragraph]
QUALITY: 88
REUSABILITY: 95
```

### E-E-A-T Patterns

```
PATTERN: expert-inline-citation
TEMPLATE: |
  According to [Expert Name], [Title] at [Organization],
  "[Direct quote or paraphrase]" (Source: [Link]).
QUALITY: 91
REUSABILITY: 90
```

### AEO Patterns

```
PATTERN: definition-box
TEMPLATE: |
  **What is [Term]?** [Concise 1-2 sentence definition
  optimized for featured snippet extraction.]
QUALITY: 87
REUSABILITY: 93
```

---

## Pattern Promotion Logic

```
ON Pattern_Review (weekly):
    
    1. FOR EACH pattern in Learning/patterns.md:
        
        a. CALCULATE success_rate = 
           high_score_uses / total_uses
        
        b. IF success_rate >= 0.80 AND usage_count >= 5:
           - SET promoted = true
           - ADD to MEMORY.md (curated patterns)
        
        c. IF success_rate < 0.50 AND usage_count >= 5:
           - SET deprecated = true
           - REMOVE from active rotation
        
        d. UPDATE pattern metadata
```

---

## Output: Learning/patterns.md Structure

```markdown
# Curated Content Patterns

> Last updated: 2026-02-05
> Total patterns: 47 | Promoted: 23 | Active: 38

---

## Structure Patterns (12)

### PATTERN: h1-question-how-to
- **Template**: How to [ACTION] [OBJECT] in [CONTEXT]
- **Success Rate**: 89%
- **Uses**: 15
- **Status**: ✅ Promoted

...

## SEO Patterns (10)

...

## E-E-A-T Patterns (8)

...

## AEO Patterns (9)

...

## Engagement Patterns (8)

...
```

---

## Memory Integration

### Write Keys

```
learning.patterns.structure[]
learning.patterns.seo[]
learning.patterns.eeat[]
learning.patterns.aeo[]
learning.patterns.engagement[]
learning.patterns.promoted[]
learning.patterns.deprecated[]
```

### Read Dependencies

```
content.integrated.final
validation.quality.*
strategy.brief.*
```

---

*pattern-extractor.md | Autonomous-Core | v2.3.3*
