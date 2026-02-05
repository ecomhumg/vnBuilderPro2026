# Memory Bus Contract

> **SEO-AEO-GEO-EEAT-BlogWriter** | 250+ Keys | 19 Namespaces | v2.3.3

---

## Namespace Registry

| Namespace | Category | Owner |
|-----------|----------|-------|
| `strategy.*` | Strategic planning | T1 |
| `intel.*` | Intelligence data | T2 |
| `content.*` | Content artifacts | T3 |
| `analysis.*` | Analysis reports | T4 |
| `validation.*` | Validation results | T5 |
| `output.*` | Final deliverables | T6 |
| `seo.*` | SEO patterns | Shared |
| `aeo.*` | AEO patterns | Shared |
| `geo.*` | GEO patterns | Shared |
| `eeat.*` | E-E-A-T signals | Shared |
| `persist.*` | Context persistence (NEW) | Autonomous-Core |
| `learning.*` | Self-learning (NEW) | Autonomous-Core |
| `evolution.*` | Evolution metrics (NEW) | Autonomous-Core |

---

## Key Catalog

### Strategy Keys (T1)

```text
strategy.brief.topic
strategy.brief.keyword_primary
strategy.brief.keywords_secondary
strategy.brief.intent
strategy.brief.audience
strategy.brief.locale
strategy.brief.stage
strategy.brief.cta
strategy.brief.competitors
strategy.outline.h1
strategy.outline.h2_list
strategy.eeat.requirements
```

### Intel Keys (T2)

```text
intel.keywords.primary_validated
intel.keywords.secondary_validated
intel.keywords.volume_data
intel.competitors.gap_analysis
intel.competitors.top_performer
intel.intent.classification
intel.intent.stage
intel.paa.questions
intel.trends.topics
```

### Content Keys (T3)

```text
content.outline.structure
content.body.raw
content.body.optimized
content.body.sections
content.meta.title
content.meta.description
content.meta.slug
content.meta.canonical
content.schema.article
content.schema.faq
content.schema.organization
content.links.internal
content.links.external
content.images.plan
content.faqs.list
content.integrated.final
```

### Analysis Keys (T4)

```text
analysis.readability.grade
analysis.readability.sentence_avg
analysis.readability.active_pct
analysis.voice.score
analysis.eeat.experience_score
analysis.eeat.expertise_score
analysis.eeat.authority_score
analysis.eeat.trust_score
analysis.eeat.total_score
analysis.eeat.gaps
analysis.personalization.fit_score
```

### Validation Keys (T5)

```text
validation.quality.seo_pass
validation.quality.aeo_pass
validation.quality.geo_pass
validation.quality.eeat_pass
validation.quality.issues
validation.compliance.certified
validation.compliance.timestamp
```

### Output Keys (T6)

```text
output.brief.final
output.article.final
output.faqs.final
output.meta.final
output.links.final
output.images.final
output.schema.final
output.package.complete
```

### Persist Keys (Autonomous-Core) - NEW

```text
persist.output.path
persist.output.manifest
persist.output.session_id
persist.output.timestamp
persist.output.quality_scores
persist.context.session_id
persist.context.phase_current
persist.context.phase_snapshots
persist.context.execution_log
persist.context.resumable
```

### Learning Keys (Autonomous-Core) - NEW

```text
learning.patterns.structure
learning.patterns.seo
learning.patterns.eeat
learning.patterns.aeo
learning.patterns.engagement
learning.patterns.promoted
learning.patterns.deprecated
learning.metrics.current
learning.metrics.trends
learning.ab.active_tests
learning.ab.results
```

### Evolution Keys (Autonomous-Core) - NEW

```text
evolution.quality.seo_trend
evolution.quality.aeo_trend
evolution.quality.geo_trend
evolution.quality.eeat_trend
evolution.patterns.promoted_count
evolution.patterns.deprecated_count
evolution.focus.areas
evolution.focus.recommendations
```

---

## Access Rules

| Operation | Producer | Consumer |
|-----------|----------|----------|
| Write | Owner tier only | - |
| Read | - | All tiers |
| Update | Owner tier only | - |

---

*memory-bus-contract.md | v2.3.3 Enhanced*
