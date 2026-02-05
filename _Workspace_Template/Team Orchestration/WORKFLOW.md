# WORKFLOW - Content Generation Pipeline

> **SEO-AEO-GEO-EEAT-BlogWriter** | vnBuilderProMax v2.3.3 | 9-Phase Execution

---

## Pipeline Overview

```
Phase 0 → Phase 1 → Phase 2 → Phase 3 → Phase 4 → Phase 5 → Phase 6 → Phase 7 → Phase 8
Bootstrap  Strategy  Intel    Content  Analysis  Valid    Synth+Save Memory+Ctx Learning
```

---

## Phase 0: Bootstrap Context Injection

**Trigger**: Session start
**Mode**: Auto

### Steps

1. Load Context-Layer bootstrap files
2. Initialize MemoryStore + SkillsLoader
3. Inject tier-specific context per worker
4. Load previous session context (if resuming)
5. Validate configurations loaded

---

## Phase 1: Strategic Planning

**Tier**: T1 (W01-W04)
**Mode**: Sequential
**Duration**: ~10 min

### Workers

| Worker | Task |
|--------|------|
| W01-ContentStrategyResearch | Analyze topic, audience, intent |
| W02-SEOAEOGEOPlanning | Define keyword/entity strategy |
| W03-EEATStandardsAlignment | Establish E-E-A-T framework |
| W04-IntegrationStrategy | Plan content integration flow |

### Outputs

- `strategy.brief` - Resolved content brief
- `strategy.keywords` - Keyword/entity plan
- `strategy.eeat` - E-E-A-T requirements
- `strategy.outline` - Initial content structure

### Auto-Save

- Context snapshot: `ContextSnapshots/[session]/phase-1.json`

---

## Phase 2: Intelligence Gathering

**Tier**: T2 (W05-W08)
**Mode**: ⚡ Parallel
**Duration**: ~15 min

### Workers

| Worker | Task |
|--------|------|
| W05-KeywordEntityIntelligence | Deep keyword research |
| W06-CompetitorAnalysis | Analyze competitor content |
| W07-SearchIntentClassification | Classify and map intent |
| W08-TrendForecasting | Identify trends, PAA questions |

### Outputs

- `intel.keywords` - Validated keyword data
- `intel.competitors` - Gap analysis
- `intel.intent` - Intent classification
- `intel.trends` - Trending topics, PAA

### Auto-Save

- Context snapshot: `ContextSnapshots/[session]/phase-2.json`

---

## Phase 3: Content Development

**Tier**: T3 (W09-W14)
**Mode**: ⚡ Parallel (W09-W13) + Sequential (W14)
**Duration**: ~30 min

### Workers

| Worker | Task |
|--------|------|
| W09-ContentOutline | Create H1/H2/H3 structure |
| W10-HumanFirstCopywriter | Write human-first content |
| W11-SEOOptimization | Apply on-page SEO |
| W12-AEOGEOEnhancement | Format for AI extraction |
| W13-VisualStructuredData | Generate JSON-LD, images |
| W14-ContentIntegration | Integrate all components |

### Outputs

- `content.outline` - Structure with headings
- `content.body` - Article content
- `content.meta` - SEO meta elements
- `content.schema` - JSON-LD structured data
- `content.integrated` - Final merged content

### Auto-Save

- Context snapshot: `ContextSnapshots/[session]/phase-3.json`

---

## Phase 4: Analysis & Personalization

**Tier**: T4 (W15-W18)
**Mode**: ⚡ Parallel
**Duration**: ~15 min

### Workers

| Worker | Task |
|--------|------|
| W15-ReadabilityVoiceAnalyzer | Check readability, tone |
| W16-EEATComplianceMapper | Audit E-E-A-T signals |
| W17-Personalization | Adapt for audience |
| W18-ProgressTracking | Track generation progress |

### Outputs

- `analysis.readability` - Readability scores
- `analysis.eeat` - Compliance report  
- `analysis.personalization` - Audience fit
- `analysis.progress` - Status tracking

### Auto-Save

- Context snapshot: `ContextSnapshots/[session]/phase-4.json`

---

## Phase 5: Quality Validation

**Tier**: T5 (W19-W20)
**Mode**: Sequential
**Duration**: ~10 min

### Workers

| Worker | Task |
|--------|------|
| W19-QualityAssurance | Full quality audit |
| W20-ComplianceValidation | Compliance verification |

### Outputs

- `validation.quality` - QA report
- `validation.compliance` - Compliance certification

### Auto-Save

- Context snapshot: `ContextSnapshots/[session]/phase-5.json`

---

## Phase 6: Reporting, Synthesis & Output Saving

**Tier**: T6 (W21-W22) + Autonomous-Core
**Mode**: Sequential
**Duration**: ~10 min

### Workers

| Worker | Task |
|--------|------|
| W21-FinalDeliverablesGenerator | Generate all deliverables |
| W22-Certification | Final certification |

### Final Deliverables

1. Content Brief
2. Article Body (H1/H2/H3, TL;DR, PAA)
3. FAQs (3-5)
4. Meta Pack (Title, Desc, Slug, Canonical, OG)
5. Internal/External Link Map
6. Image Plan (2-4 + alt text)
7. JSON-LD Schema

### Auto-Save Outputs (NEW)

**Trigger**: After W22 certification
**Handler**: `Autonomous-Core/output-saver.md`

1. Generate topic slug from `strategy.brief.topic`
2. Create directory: `Outputs/[topic-slug]/[YYYY-MM-DD-HHMMSS]/`
3. Write all 7 deliverables to directory
4. Generate `manifest.json` with checksums and quality scores
5. Commit output path to memory bus

---

## Phase 7: Memory Logging & Context Persistence

**Trigger**: Phase 6 complete
**Mode**: Auto
**Handler**: `Autonomous-Core/context-persistence.md`

### Steps

1. Generate full execution log
2. Write to `Memory/ExecutionLogs/[session-id].json`
3. Update `Memory/ExecutionLogs/index.json`
4. Update MEMORY.md with curated patterns
5. Commit to daily log (`DailyLogs/YYYY-MM-DD.md`)
6. Index new entries for search

### Context Saved

- Full memory bus state
- Phase-level snapshots
- Quality scores
- Output paths

---

## Phase 8: Learning & Evolution (NEW)

**Trigger**: Phase 7 complete (if quality ≥ 85)
**Mode**: Auto
**Handler**: `Autonomous-Core/self-improvement-loop.md`

### Steps

1. **Pattern Extraction**: Extract successful patterns from content
   - H1/H2/H3 structure patterns
   - E-E-A-T signal patterns
   - AEO/GEO optimization patterns

2. **Quality Analysis**: Update metrics
   - Add scores to `Memory/Learning/metrics.json`
   - Update 7-day and 30-day trends

3. **Pattern Promotion**: Evaluate existing patterns
   - Promote patterns with ≥80% success rate
   - Deprecate patterns with <50% success rate

4. **Evolution Logging**: Record improvement
   - Log to `Memory/Learning/evolution-log.md`
   - Update focus areas for next generation

### Outputs

- `learning.patterns.extracted` - New patterns
- `learning.metrics.updated` - Current metrics
- `learning.evolution.decision` - Promotion/demotion actions

---

## Phase 9: Task Completion & Full Context Save (NEW)

**Trigger**: Phase 8 complete (or Phase 7 if quality < 85)
**Mode**: Auto
**Handler**: `Autonomous-Core/context-persistence.md`

### Steps

1. Execute `/save-context --full` (ALWAYS)
2. Save complete memory bus state to ExecutionLogs
3. Mark task as COMPLETE in index.json
4. Return all deliverables to user

### Auto-Save Guarantee

> [!IMPORTANT]
> This phase ensures ALL execution context is preserved regardless of quality score.

---

## Commands Reference

| Command | Function | Phase | Auto-Execute |
|---------|----------|-------|--------------|
| `/save-context` | Manual context save | Any | No |
| `/save-context --full` | Full memory bus save | Phase 9 | **YES** |
| `/load-context [id]` | Restore session | Phase 0 | No |
| `/evolution-tracker` | View learning metrics | Any | No |

---

*WORKFLOW.md | SEO-AEO-GEO-EEAT-BlogWriter | v2.3.3 Enhanced*
