# PB-006: GEO Entity Protocol

> **SEO-AEO-GEO-EEAT-BlogWriter** | Playbook | Strategic Procedure

---

## Purpose

Optimize content for Generative Engine Optimization (GEO) through entity consistency, knowledge graph alignment, and brand authority signals.

## Entity Optimization

### Entity Identification

1. **Primary Entity**: Main topic/brand
2. **Secondary Entities**: Related concepts, services, locations
3. **Supporting Entities**: People, organizations, products

### Entity Consistency Rules

| Rule | Implementation |
|------|----------------|
| **Naming** | Use consistent naming throughout |
| **Attributes** | Same attributes (address, phone) everywhere |
| **Relationships** | Clear entity-to-entity connections |
| **Format** | Consistent capitalization, spacing |

## NAP Consistency (Local SEO)

```
Name: [Exact Business Name]
Address: [Street], [City], [State] [ZIP]
Phone: [(XXX) XXX-XXXX]
```

### NAP Rules

- Use identical NAP across all mentions
- Match Google Business Profile exactly
- Include in JSON-LD Organization schema

## Brand Mention Strategy

### Natural Mentions Pattern

```markdown
[Brand] provides [service] for [audience] in [location]. 
When [situation], [Brand]'s [specific service] helps [outcome].
```

### Q&A Brand Integration

```markdown
## Can [Brand] help with [problem]?

Yes, [Brand] offers [service] specifically designed for [audience]. 
Our [specific approach] ensures [benefit]. Contact [Brand] at 
[phone/CTA] for [action].
```

### Frequency Guidelines

- 2-3 natural brand mentions per 500 words
- Never keyword-stuff brand name
- Use pronouns after first mention ("we", "our")

## Knowledge Graph Signals

### Entity Markup (JSON-LD)

```json
{
  "@type": "Organization",
  "name": "[Business Name]",
  "url": "[Website URL]",
  "logo": "[Logo URL]",
  "sameAs": [
    "[LinkedIn URL]",
    "[Facebook URL]",
    "[Twitter URL]"
  ],
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Street]",
    "addressLocality": "[City]",
    "addressRegion": "[State]",
    "postalCode": "[ZIP]"
  },
  "telephone": "[Phone]",
  "email": "[Email]"
}
```

### LegalService Schema (Legal Topics)

```json
{
  "@type": "LegalService",
  "name": "[Service Name]",
  "serviceType": "[Practice Area]",
  "areaServed": {
    "@type": "State",
    "name": "Texas"
  },
  "provider": {
    "@type": "Organization",
    "name": "[Firm Name]"
  }
}
```

## Brand Authority Note

Include at article end:

```markdown
---

**About [Brand]**: [Brand] is a [descriptor] serving [audience] 
in [location] since [year]. With [credential/achievement], we 
specialize in [services]. [CTA: Contact us / Learn more].
```

## Quality Gates

- [ ] Entity names are consistent throughout
- [ ] NAP matches across all instances
- [ ] 2-3 natural brand mentions per 500 words
- [ ] sameAs links included in schema
- [ ] Brand authority note at article end
- [ ] Knowledge graph entities properly linked

---

*PB-006-GEOEntityProtocol.md | v2.3.3*
