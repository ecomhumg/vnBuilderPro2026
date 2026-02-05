# Citation Validation Protocol

> **Playbook ID**: PLAYBOOK-SDR-003
> **Domain**: ScholarDeepResearch-Workforce
> **Version**: 1.0.0

---

## Overview

Ensures all citations are accurate, verifiable, and free from hallucinations.

---

## Citation Format Standard

```
*Author, A. (Year). Title. Journal, Vol(Issue), Pages. [DOI/Link]*
```

---

## Validation Pipeline

### Stage 1: Format Verification

```
FOR each citation:
  1. Check author format (Last, First Initial)
  2. Verify year is numeric and reasonable
  3. Confirm title is complete
  4. Validate journal name exists
  5. Check volume/issue/pages format
```

### Stage 2: DOI Verification

```
FOR each DOI:
  1. Validate DOI format (10.xxxx/...)
  2. Query DOI.org resolver
  3. Confirm landing page accessible
  4. Match metadata to citation
```

### Stage 3: Link Validation

```
FOR each URL:
  1. HTTP HEAD request
  2. Check for 200/301/302 status
  3. Verify content matches expected
  4. Flag dead links for replacement
```

---

## Anti-Hallucination Rules

| Rule | Implementation |
|------|----------------|
| No invented DOIs | Always verify via doi.org |
| No fake journals | Check against journal databases |
| No fabricated authors | Cross-reference with paper |
| No wrong years | Match publication date |

---

## Error Handling

| Error Type | Action |
|------------|--------|
| Invalid DOI | Search by title, request correction |
| Dead Link | Find alternative source |
| Metadata Mismatch | Flag for manual review |
| Non-existent Paper | Remove and document |

---

## Quality Gate

| Metric | Threshold |
|--------|-----------|
| DOI Validity | 100% |
| Link Accessibility | ≥95% |
| Metadata Accuracy | 100% |

---

*Playbook PLAYBOOK-SDR-003 | Citation Validation Protocol*
