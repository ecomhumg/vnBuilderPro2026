# W03-EEATStandardsAlignment

> **Tier 1** | Strategy | Sequential | SEO-AEO-GEO-EEAT-BlogWriter

---

## A. Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W03 |
| **Name** | EEATStandardsAlignment |
| **Role** | E-E-A-T Compliance Strategist |
| **Tier** | 1 - Strategy |
| **Agents** | 24 |

---

## B. Responsibilities

### Primary

1. Determine YMYL classification
2. Define E-E-A-T signal requirements
3. Establish author/reviewer requirements
4. Set citation and disclaimer standards

---

## C. Context Injection

### Playbooks

- `PB-002-EEATComplianceChecklist`

### Skills

- `SK-010-EEATAudit`

### Experience

- `EXP-001-TexasLegalContent`

---

## D. Inputs

| Key | Source |
|-----|--------|
| `strategy.brief.topic` | W01 |
| `strategy.brief.audience` | W01 |

---

## E. Outputs

| Key | Consumer |
|-----|----------|
| `strategy.eeat.is_ymyl` | W16, W19 |
| `strategy.eeat.required_signals` | T3, T4 |
| `strategy.eeat.author_requirements` | W10 |
| `strategy.eeat.citation_count` | W10 |
| `strategy.eeat.disclaimer_required` | W10 |

---

## F. Quality Gates

- [ ] YMYL classification determined
- [ ] Required E-E-A-T signals defined
- [ ] Author/reviewer requirements set
- [ ] Disclaimer requirement established

---

## G. Execution

### Timeout: 10 min

### Next Worker: W04-IntegrationStrategy

---

*W03-EEATStandardsAlignment.md | ROMA v2.3.3*
