# W02-SEOAEOGEOPlanning

> **Tier 1** | Strategy | Sequential | SEO-AEO-GEO-EEAT-BlogWriter

---

## A. Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W02 |
| **Name** | SEOAEOGEOPlanning |
| **Role** | SEO/AEO/GEO Strategy Planner |
| **Tier** | 1 - Strategy |
| **Agents** | 24 |
| **Mode** | Sequential |

---

## B. Responsibilities

### Primary

1. Define keyword strategy (primary + secondary)
2. Plan AEO extraction opportunities
3. Establish GEO entity requirements
4. Set Featured Snippet targets

### Secondary

- Identify PAA opportunities
- Define voice search optimization goals
- Plan schema requirements

---

## C. Context Injection

### Bootstrap

- `AGENTS.md`, `SOUL.md`, `TOOLS.md`

### Playbooks

- `PB-003-FeaturedSnippetProtocol`
- `PB-004-PAAResearchProtocol`
- `PB-005-AEOEnhancementProtocol`
- `PB-006-GEOEntityProtocol`

### Skills

- `SK-001-KeywordEntityResearch`
- `SK-003-SearchIntentClassification`

---

## D. Inputs

| Key | Source |
|-----|--------|
| `strategy.brief.*` | W01 |

---

## E. Outputs

| Key | Consumer |
|-----|----------|
| `strategy.keywords.primary` | T2, T3 |
| `strategy.keywords.secondary` | T2, T3 |
| `strategy.aeo.targets` | W12 |
| `strategy.geo.entities` | W12 |
| `strategy.snippets.opportunities` | W11 |

---

## F. Quality Gates

- [ ] Primary keyword validated
- [ ] 5-12 secondary keywords listed
- [ ] AEO extraction points identified
- [ ] Entity list complete

---

## G. Execution

### Timeout: 15 min

### Next Worker: W03-EEATStandardsAlignment

---

*W02-SEOAEOGEOPlanning.md | ROMA v2.3.3*
