# SK-010: E-E-A-T Audit

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Audit content for E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness) compliance.

## Scoring Framework

| Dimension | Weight | Max Score |
|-----------|--------|-----------|
| Experience | 25% | 25 |
| Expertise | 25% | 25 |
| Authoritativeness | 25% | 25 |
| Trustworthiness | 25% | 25 |
| **Total** | 100% | **100** |

## Experience Audit (25 points)

| Signal | Points | Check |
|--------|--------|-------|
| First-hand account/case study | 10 | ☐ |
| Specific real-world details | 5 | ☐ |
| Personal voice ("In my experience...") | 5 | ☐ |
| Unique insights not found elsewhere | 5 | ☐ |

## Expertise Audit (25 points)

| Signal | Points | Check |
|--------|--------|-------|
| Technical accuracy (fact-checked) | 10 | ☐ |
| Comprehensive topic coverage | 5 | ☐ |
| Appropriate domain terminology | 5 | ☐ |
| Original analysis/framework | 5 | ☐ |

## Authoritativeness Audit (25 points)

| Signal | Points | Check |
|--------|--------|-------|
| Author bio with credentials | 8 | ☐ |
| Expert reviewer (YMYL) | 7 | ☐ |
| Citations (2-4 reputable sources) | 5 | ☐ |
| Organization credentials mentioned | 5 | ☐ |

## Trustworthiness Audit (25 points)

| Signal | Points | Check |
|--------|--------|-------|
| Clear disclaimer (YMYL) | 7 | ☐ |
| Jurisdiction/applicability note | 5 | ☐ |
| Last updated timestamp | 5 | ☐ |
| Balanced view (acknowledges limitations) | 5 | ☐ |
| Contact/transparency info | 3 | ☐ |

## Passing Thresholds

| Content Type | Minimum Score |
|--------------|---------------|
| General content | 70/100 |
| YMYL content | 85/100 |
| Legal/Medical/Financial | 90/100 |

## Gap Analysis

### Missing Signals Template

```yaml
gaps:
  experience:
    missing: ["case study", "specific details"]
    recommendation: "Add real client scenario"
  expertise:
    missing: ["original framework"]
    recommendation: "Create proprietary process diagram"
  authoritativeness:
    missing: ["expert reviewer"]
    recommendation: "Add attorney reviewer byline"
  trustworthiness:
    missing: ["disclaimer"]
    recommendation: "Add legal disclaimer block"
```

## Output

```yaml
eeat_audit:
  scores:
    experience: [0-25]
    expertise: [0-25]
    authoritativeness: [0-25]
    trustworthiness: [0-25]
    total: [0-100]
  content_type: "[general/ymyl]"
  required_threshold: [number]
  pass: [yes/no]
  gaps:
    - dimension: "[E/E/A/T]"
      signal: "[missing signal]"
      impact: [points missing]
      fix: "[recommendation]"
  priority_fixes:
    1: "[Most impactful fix]"
    2: "[Second fix]"
    3: "[Third fix]"
```

---

*SK-010-EEATAudit.md | v2.3.3*
