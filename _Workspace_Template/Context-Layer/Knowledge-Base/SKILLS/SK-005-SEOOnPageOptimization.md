# SK-005: SEO On-Page Optimization

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Optimize on-page SEO elements including meta tags, headings, URLs, and internal linking.

## Meta Title Optimization

### Rules

- **Length**: ≤60 characters (display limit)
- **Structure**: [Benefit/Topic] + [Primary Keyword] + [Brand]
- **Front-load**: Put keyword early

### Template

```
[Primary Keyword]: [Benefit/Hook] | [Brand]
```

### Examples

```
✅ Houston Business Lawyer: Expert Contract Review | [Firm]
✅ How to Form an LLC in Texas (2025 Guide) | [Firm]
❌ Welcome to Our Website - We Do Many Legal Services for You
```

## Meta Description Optimization

### Rules

- **Length**: ≤160 characters
- **Include**: Primary keyword, benefit, CTA
- **Tone**: Compelling, action-oriented

### Template

```
[Hook addressing user need]. Learn [benefit]. [CTA phrase]. [Differentiator].
```

### Example

```
Need a business lawyer in Houston? Get expert contract review 
and LLC formation. Free consultation. 20+ years experience.
```

## URL/Slug Optimization

### Rules

- **Length**: 3-5 words (50-60 chars max)
- **Format**: lowercase, hyphens, no stop words
- **Include**: Primary keyword

### Template

```
/[primary-keyword]-[modifier]
```

### Examples

```
✅ /houston-business-lawyer
✅ /texas-llc-formation-guide
❌ /our-services-for-business-law-in-the-houston-area
```

## Heading Structure

### H1 Rules

- One per page
- Contains primary keyword
- Clear topic statement

### H2/H3 Rules

- Use question format for PAA targeting
- Include secondary keywords naturally
- Logical content hierarchy

### Structure Template

```markdown
# [H1 with Primary Keyword]

## [H2 Question with Secondary Keyword]?
### [H3 Sub-topic]
### [H3 Sub-topic]

## [H2 Question with Secondary Keyword]?
...
```

## Internal Link Mapping

### Link Strategy

| Link Type | Target | Anchor Text |
|-----------|--------|-------------|
| Pillar → Cluster | Related deeper content | Descriptive phrase |
| Cluster → Pillar | Main topic page | Primary keyword |
| Related → Related | Topically similar | Natural phrase |

### Template

```yaml
internal_links:
  - anchor: "[Descriptive text]"
    target: "[URL]"
    context: "[Sentence it appears in]"
```

## External Link Guidelines

### Acceptable Sources

- .gov, .edu, statutory citations
- Reputable industry publications
- Primary sources (studies, data)

### Format

```markdown
[Source description] ([Publisher], [Year])
```

## Output

```yaml
seo_optimization:
  meta_title: "[≤60 chars]"
  meta_description: "[≤160 chars]"
  slug: "[url-friendly-slug]"
  canonical: "[full canonical URL]"
  og_title: "[social share title]"
  og_description: "[social share description]"
  internal_links:
    - anchor: "[text]"
      url: "[target]"
  external_links:
    - anchor: "[text]"
      url: "[source]"
      accessed: "[YYYY-MM-DD]"
```

---

*SK-005-SEOOnPageOptimization.md | v2.3.3*
