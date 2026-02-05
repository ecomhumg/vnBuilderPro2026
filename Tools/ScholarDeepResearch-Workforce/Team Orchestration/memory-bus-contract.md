# Memory Bus Contract

> **ScholarDeepResearch-Workforce v1.0.0**
> Inter-worker communication specification

---

## Query & Intelligence (Tier 1)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `query.original` | String | User | W01 |
| `query.clarified` | Object | W01 | W04, W05 |
| `query.domain` | String | W02 | W05, W06-W08 |
| `query.intent` | String | W01 | W20 |
| `input.multimodal` | Array | W03 | W09, W11 |

---

## Search Strategy (Tier 2)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `search.strategy` | Object | W04 | W06-W08, W21 |
| `search.keywords` | Array | W04 | W06-W08, W21 |
| `sources.priority` | Array | W05 | W06-W08, W21 |
| `sources.quotas` | Object | W05 | W06-W08, W21 |

---

## Search Acquisition (Tier 3)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `results.scholar` | Array | W06 | W09 |
| `results.arxiv` | Array | W07 | W09 |
| `results.pubmed` | Array | W08 | W09 |
| `results.biorxiv` | Array | W08 | W09 |
| `results.patents` | Array | W21 | W09 |
| `results.web` | Array | W21 | W09 |
| `results.merged` | Array | Aggregator | W09, W10 |

---

## Content Extraction (Tier 4)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `content.fulltext` | Array | W09 | W11-W14 |
| `content.failed` | Array | W09 | W20 |
| `datasets.processed` | Array | W10 | W15 |

---

## Critical Reading (Tier 5)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `reading.summaries` | Array | W11 | W17, W20 |
| `reading.questions` | Array | W11, W12 | W20 |
| `reading.inquiry` | Array | W12 | W20 |
| `reading.contrasts` | Array | W13 | W20 |
| `reading.visuals` | Array | W14 | W16, W20 |
| `reading.assumptions` | Array | W12 | W17 |

---

## Analysis & Synthesis (Tier 6)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `analysis.results` | Object | W15 | W16, W20 |
| `visuals.charts` | Array | W16 | W20 |
| `verification.facts` | Array | W17 | W18, W20 |

---

## Quality Validation (Tier 7)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `validation.citations` | Object | W18 | W19, W20 |
| `validation.links` | Array | W18 | W20 |
| `quality.score` | Float | W19 | W20 |
| `quality.passed` | Boolean | W19 | W20 |

---

## Delivery & Evolution (Tier 8)

| Key | Type | Producer | Consumers |
|-----|------|----------|-----------|
| `output.report` | Object | W20 | User |
| `efficiency.metrics` | Object | W22 | System |

---

*Memory Bus Contract | ScholarDeepResearch-Workforce v1.0.0*
