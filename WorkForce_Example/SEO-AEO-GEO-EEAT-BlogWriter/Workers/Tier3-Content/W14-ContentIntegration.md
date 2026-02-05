# W14-ContentIntegration

> **Tier 3** | Content | Aggregator | SEO-AEO-GEO-EEAT-BlogWriter

---

## A. Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W14 |
| **Name** | ContentIntegration |
| **Role** | Content Aggregator (Tier 3 Sync Point) |
| **Tier** | 3 - Content |
| **Mode** | Sequential (after W09-W13 complete) |
| **Function** | **AGGREGATOR** |

---

## B. Responsibilities

1. **Wait** for W09-W13 outputs
2. **Merge** all content components
3. **Resolve** conflicts and gaps
4. **Package** integrated content for T4

---

## C. Context Injection

### Playbooks

- `PB-001-ContentBriefProtocol`

### Skills

- All SK-001 through SK-008 (reference)

---

## D. Inputs

| Key | Source |
|-----|--------|
| `content.outline.*` | W09 |
| `content.body.*` | W10 |
| `content.meta.*` | W11 |
| `content.aeo.*` | W12 |
| `content.geo.*` | W12 |
| `content.schema.*` | W13 |
| `content.images.*` | W13 |
| `content.faqs.*` | W10, W13 |
| `content.links.*` | W11 |

---

## E. Outputs

| Key | Consumer |
|-----|----------|
| `content.integrated.article` | T4, T5, T6 |
| `content.integrated.meta` | T5, T6 |
| `content.integrated.schema` | T5, T6 |
| `content.integrated.links` | T5, T6 |
| `content.integrated.images` | T6 |

---

## F. Quality Gates

- [ ] All T3 worker outputs received
- [ ] No conflicting content
- [ ] Complete deliverable set assembled
- [ ] Ready for T4 analysis

---

## G. Execution

### Mode: Barrier-Sync (waits for W09-W13)

### Timeout: 15 min

### Next: Tier 4 (Parallel)

---

*W14-ContentIntegration.md | ROMA v2.3.3*
