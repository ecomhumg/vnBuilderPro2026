# SK-008: Structured Data Generation

> **SEO-AEO-GEO-EEAT-BlogWriter** | Skill | Technical Implementation

---

## Purpose

Generate valid JSON-LD structured data for rich results and AI comprehension.

## Schema Types

| Content | Required Schemas |
|---------|------------------|
| Blog Article | Article, FAQPage, Organization |
| Legal Content | Article, FAQPage, LegalService, Organization |
| How-To Guide | Article, HowTo, FAQPage |
| Local Business | LocalBusiness, Organization |

## Article Schema

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "[Title ≤110 chars]",
  "description": "[Meta description]",
  "author": {
    "@type": "Person",
    "name": "[Author Name]",
    "jobTitle": "[Title]"
  },
  "publisher": {
    "@type": "Organization",
    "name": "[Publisher]",
    "logo": {"@type": "ImageObject", "url": "[Logo URL]"}
  },
  "datePublished": "[YYYY-MM-DD]",
  "dateModified": "[YYYY-MM-DD]",
  "image": "[Image URL]"
}
```

## FAQPage Schema

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[Question 1]?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 40-60 words]"
      }
    }
  ]
}
```

## HowTo Schema

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "[How to Title]",
  "step": [
    {
      "@type": "HowToStep",
      "name": "[Step 1 Title]",
      "text": "[Step 1 Instructions]"
    }
  ]
}
```

## LegalService Schema

```json
{
  "@context": "https://schema.org",
  "@type": "LegalService",
  "name": "[Service Name]",
  "serviceType": "[Practice Area]",
  "areaServed": {"@type": "State", "name": "Texas"},
  "provider": {"@type": "Organization", "name": "[Firm]"}
}
```

## @graph Combined Schema

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {"@type": "Article", ...},
    {"@type": "FAQPage", ...},
    {"@type": "Organization", ...}
  ]
}
```

## Validation Rules

1. Valid JSON syntax
2. Required properties present
3. URLs are absolute (https://)
4. Dates in ISO 8601 format
5. headline ≤110 characters

## Output Format

### HTML Embed

```html
<script type="application/ld+json">
[JSON content]
</script>
```

### Documentation Block

```json
[Same JSON in fenced code block]
```

---

*SK-008-StructuredDataGeneration.md | v2.3.3*
