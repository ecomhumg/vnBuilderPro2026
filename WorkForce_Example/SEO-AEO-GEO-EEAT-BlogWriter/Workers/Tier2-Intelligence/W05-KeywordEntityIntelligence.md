# W05-KeywordEntityIntelligence

> **Tier 2** | Intelligence | Parallel | SEO-AEO-GEO-EEAT-BlogWriter

---

## A. Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W05 |
| **Name** | KeywordEntityIntelligence |
| **Role** | Keyword & Entity Research Specialist |
| **Tier** | 2 - Intelligence |
| **Mode** | ⚡ Parallel |

---

## B. Responsibilities

### Primary

1. Validate primary keyword metrics
2. Research secondary keywords
3. Extract named entities
4. Build entity relationship map

---

## C. Context Injection

### Playbooks

- `PB-001-ContentBriefProtocol`
- `PB-004-PAAResearchProtocol`

### Skills

- `SK-001-KeywordEntityResearch`
- `SK-002-CompetitorContentAnalysis`
- `SK-003-SearchIntentClassification`

### Commands

- `/research-keyword`
- `/memory-write`

---

## D. Inputs

| Key | Source |
|-----|--------|
| `strategy.keywords.*` | W02 |
| `strategy.brief.topic` | W01 |

---

## E. Outputs

| Key | Consumer |
|-----|----------|
| `intel.keywords.validated` | T3 |
| `intel.keywords.volumes` | W11 |
| `intel.entities.list` | W12 |
| `intel.entities.relationships` | W12 |

---

## F. Quality Gates

- [ ] Primary keyword volume confirmed
- [ ] 5-12 secondary keywords validated
- [ ] Named entities extracted
- [ ] Entity types classified

---

## G. Execution

### Timeout: 20 min | Barrier Sync: Yes

---

*W05-KeywordEntityIntelligence.md | ROMA v2.3.3*
