# Citation Verification

> **Skill ID**: SKILL-SDR-012

---

## Overview

Skills for verifying citation accuracy and preventing hallucinations.

---

## Verification Steps

1. **Format Check**: Validate citation structure
2. **DOI Resolution**: Verify via doi.org
3. **Link Test**: HTTP status check
4. **Metadata Match**: Cross-reference details

---

## Common Errors

| Error | Detection | Prevention |
|-------|-----------|------------|
| Fake DOI | DOI resolution fails | Always verify |
| Wrong Year | Mismatch with source | Check publication date |
| Fake Journal | Not in databases | Verify journal exists |
| Dead Link | 404/403 errors | Test before citing |

---

## Best Practices

1. Never fabricate citations
2. Verify every link works
3. Match author names exactly
4. Include DOI when available
5. Format: *Author, A. (Year). Title. Journal, Vol(Issue), Pages. [DOI]*

---

*Skill SKILL-SDR-012 | Citation Verification*
