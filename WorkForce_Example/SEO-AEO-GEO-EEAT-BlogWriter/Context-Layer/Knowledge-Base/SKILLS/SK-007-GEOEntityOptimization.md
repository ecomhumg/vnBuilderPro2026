# SK-007: GEO Entity Optimization

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Optimize entity consistency and knowledge graph signals for Generative Engine Optimization.

## Entity Types

| Type | Examples | Priority |
|------|----------|----------|
| **Organization** | Business name, brand | Critical |
| **Person** | Author, expert reviewer | High |
| **Place** | City, state, address | High (local) |
| **Service** | Legal service, product | High |
| **Concept** | Industry terms, processes | Medium |

## Entity Consistency Rules

### Naming Consistency

Use identical naming throughout:

```markdown
✅ Consistent:
"Smith Law Firm" (first mention)
"Smith Law" (acceptable short form after first)
"we", "our firm" (pronouns after establishment)

❌ Inconsistent:
"Smith Law Firm" → "Smith Legal" → "the firm" → "SLF"
```

### NAP Consistency (Local)

```
Name:    [Exact Business Name]
Address: [Street], [City], TX [ZIP]
Phone:   [(XXX) XXX-XXXX]
```

## Brand Mention Strategy

### Frequency

- 2-3 natural mentions per 500 words
- First mention: Full name
- Subsequent: Short form or pronouns

### Natural Integration Patterns

```markdown
Pattern 1: Service Context
"[Brand] provides [service] for [audience] in [location]."

Pattern 2: Experience Context  
"At [Brand], we've handled [X number] of [cases/situations]."

Pattern 3: Q&A Context
"Can [Brand] help with [problem]? Yes, [Brand] specializes in..."

Pattern 4: Authority Context
"[Brand] has served [location] businesses since [year]."
```

## Knowledge Graph Signals

### Entity Attributes to Include

1. Official name
2. Type/category
3. Location (address)
4. Contact (phone, email)
5. Social profiles (sameAs)
6. Service types
7. Area served

### Relationship Mapping

```yaml
entity_relationships:
  organization:
    provides: [services]
    locatedIn: [place]
    employs: [persons]
    servedBy: [author]
```

## Local SEO Entities

### Geographic Entities

- City: Houston
- State: Texas
- Region: Greater Houston Area
- County: Harris County

### Service Area Markup

```json
"areaServed": [
  {"@type": "City", "name": "Houston"},
  {"@type": "State", "name": "Texas"}
]
```

## Quality Checks

- [ ] Business name consistent throughout
- [ ] NAP identical in all instances
- [ ] 2-3 brand mentions per 500 words
- [ ] Entity relationships clearly established
- [ ] Geographic entities correctly specified
- [ ] sameAs links prepared for schema

## Output

```yaml
entity_optimization:
  primary_entity:
    name: "[Official name]"
    type: "[Organization/Person/Place]"
    mentions: [count]
  consistency_check:
    variations_found: [list]
    issues: [list]
  nap:
    name: "[Exact name]"
    address: "[Full address]"
    phone: "[Formatted phone]"
  relationships:
    - type: "[relationship]"
      target: "[entity]"
  sameAs:
    - "[LinkedIn URL]"
    - "[Facebook URL]"
```

---

*SK-007-GEOEntityOptimization.md | v2.3.3*
