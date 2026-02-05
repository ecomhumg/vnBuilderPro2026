# PB-007: JSON-LD Generation Protocol

> **SEO-AEO-GEO-EEAT-BlogWriter** | Playbook | Strategic Procedure

---

## Purpose

Generate valid, comprehensive JSON-LD structured data for Google Rich Results following 2025 standards.

## Required Schema Types

| Content Type | Schema Types |
|--------------|--------------|
| Blog Article | Article, FAQPage, Organization |
| Legal Content | Article, FAQPage, LegalService, Organization |
| How-To Guide | Article, HowTo, FAQPage |

## Schema Templates

### Article Schema

```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "[Article Title - max 110 chars]",
  "description": "[Meta description]",
  "author": {
    "@type": "Person",
    "name": "[Author Name]",
    "jobTitle": "[Title/Credentials]",
    "url": "[Author Page URL]"
  },
  "publisher": {
    "@type": "Organization",
    "name": "[Publisher Name]",
    "logo": {
      "@type": "ImageObject",
      "url": "[Logo URL]"
    }
  },
  "datePublished": "[YYYY-MM-DD]",
  "dateModified": "[YYYY-MM-DD]",
  "image": "[Featured Image URL]",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "[Canonical URL]"
  }
}
```

### FAQPage Schema

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "[Question 1]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 1 - 40-60 words]"
      }
    },
    {
      "@type": "Question",
      "name": "[Question 2]",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[Answer 2 - 40-60 words]"
      }
    }
  ]
}
```

### Organization Schema

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "[Business Name]",
  "url": "[Website URL]",
  "logo": "[Logo URL]",
  "sameAs": [
    "[LinkedIn]",
    "[Facebook]",
    "[Twitter]"
  ],
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Street]",
    "addressLocality": "[City]",
    "addressRegion": "TX",
    "postalCode": "[ZIP]"
  },
  "telephone": "[Phone]",
  "email": "[Email]"
}
```

### LegalService Schema

```json
{
  "@context": "https://schema.org",
  "@type": "LegalService",
  "name": "[Service Name]",
  "serviceType": "[Practice Area]",
  "areaServed": [
    {
      "@type": "State",
      "name": "Texas"
    },
    {
      "@type": "City",
      "name": "Houston"
    }
  ],
  "provider": {
    "@type": "Organization",
    "name": "[Firm Name]"
  }
}
```

## @graph Implementation

For legal/YMYL content, combine schemas using @graph:

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Article",
      ...
    },
    {
      "@type": "FAQPage",
      ...
    },
    {
      "@type": "Organization",
      ...
    },
    {
      "@type": "LegalService",
      ...
    }
  ]
}
```

## Output Format

### In Article

```html
<script type="application/ld+json">
{JSON content here}
</script>
```

### Documentation (immediately after)

```json
{Same JSON in fenced code block}
```

## Validation Rules

1. **Valid JSON**: No syntax errors, proper escaping
2. **Required Fields**: Include all mandatory properties
3. **URL Format**: Use absolute URLs (https://)
4. **Date Format**: ISO 8601 (YYYY-MM-DD)
5. **Text Limits**: headline ≤110 chars

## Quality Gates

- [ ] Article schema includes author, publisher, dates
- [ ] FAQPage has 3-5 Q&A pairs
- [ ] Organization schema has NAP + sameAs
- [ ] LegalService included for legal topics
- [ ] JSON validates in Google Rich Results Test
- [ ] Both script tag and code block provided

---

*PB-007-JSONLDGenerationProtocol.md | v2.3.3*
