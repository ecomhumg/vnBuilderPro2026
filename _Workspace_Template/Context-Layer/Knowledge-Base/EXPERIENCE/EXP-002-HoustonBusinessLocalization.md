# EXP-002: Houston Business Localization

> **SEO-AEO-GEO-EEAT-BlogWriter** | Experience | Best Practices

---

## Purpose

Local SEO and content localization guidelines for Houston, Texas market.

## Houston Market Profile

| Attribute | Value |
|-----------|-------|
| **Metro Population** | 7.3+ million (2025) |
| **Business Hub Rank** | #4 in USA |
| **Key Industries** | Energy, Healthcare, Manufacturing, Aerospace |
| **Business Districts** | Downtown, Galleria, Energy Corridor, Medical Center |

## Local Entities

### Geographic Terms

- Houston
- Greater Houston Area
- Houston metro
- Harris County
- The Bayou City (casual)

### Neighborhoods/Districts (for local SEO)

- Downtown Houston
- The Galleria / Uptown
- The Heights
- Montrose
- Midtown
- The Woodlands
- Sugar Land
- Katy

## NAP Consistency

### Standard Format

```
[Business Name]
[Street Address]
Houston, TX [ZIP]
(XXX) XXX-XXXX
```

### Common Houston ZIPs

- 77002 (Downtown)
- 77056 (Galleria)
- 77027 (River Oaks)
- 77030 (Texas Medical Center)
- 77084 (Energy Corridor)

## Local Content Signals

### Phrases to Include

- "Houston business owners"
- "serving the Greater Houston area"
- "Harris County [service]"
- "Houston-based [profession]"

### Local References

- "Unlike Dallas or Austin, Houston..."
- "Texas's largest city"
- "In the Houston market, we see..."

## Schema Local Markup

```json
{
  "@type": "LocalBusiness",
  "areaServed": [
    {
      "@type": "City",
      "name": "Houston",
      "containedInPlace": {
        "@type": "State",
        "name": "Texas"
      }
    }
  ],
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Address]",
    "addressLocality": "Houston",
    "addressRegion": "TX",
    "postalCode": "[ZIP]",
    "addressCountry": "US"
  }
}
```

## Houston-Specific Content Ideas

### Industry Angles

- Energy sector business law
- Healthcare practice management
- Real estate (Texas-specific rules)
- International trade (Port of Houston)

### Local Events/Context

- Houston Economic Development
- Texas state legislative sessions
- Harris County business requirements

---

*EXP-002-HoustonBusinessLocalization.md | v2.3.3*
