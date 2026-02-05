# W01-ContentStrategyResearch

> **Tier 1** | Strategy | Sequential | SEO-AEO-GEO-EEAT-BlogWriter

---

## A. Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W01 |
| **Name** | ContentStrategyResearch |
| **Role** | Strategic Research Lead |
| **Tier** | 1 - Strategy |
| **Agents** | 24 |
| **Mode** | Sequential |

---

## B. Responsibilities

### Primary

1. Analyze incoming content request
2. Resolve audience, intent, stage parameters
3. Research topic depth requirements
4. Define content strategy framework

### Secondary

- Validate brief completeness
- Identify topic complexity
- Set quality targets

---

## C. Context Injection

### Bootstrap (load first)

- `AGENTS.md` - Swarm architecture
- `SOUL.md` - Voice/persona
- `IDENTITY.md` - Capabilities
- `USER.md` - Default preferences

### Playbooks

- `PB-001-ContentBriefProtocol` - Parameter resolution
- `PB-002-EEATComplianceChecklist` - E-E-A-T requirements
- `PB-008-HumanFirstVoiceProtocol` - Voice calibration

### Skills

- `SK-001-KeywordEntityResearch` - Entity extraction
- `SK-003-SearchIntentClassification` - Intent mapping

### Commands

- `/memory-search` - Find relevant patterns
- `/memory-write` - Store decisions
- `/recall` - Quick retrieval

---

## D. Inputs

| Key | Type | Source | Required |
|-----|------|--------|----------|
| `request.topic` | string | User | ✅ |
| `request.keyword` | string | User | Optional |
| `request.audience` | string | User/Default | Optional |
| `request.intent` | string | User/Auto | Optional |
| `request.competitors` | array | User | Optional |

---

## E. Outputs

| Key | Type | Consumer |
|-----|------|----------|
| `strategy.brief.topic` | string | T2-T6 |
| `strategy.brief.keyword_primary` | string | W02, W05 |
| `strategy.brief.audience` | string | T3-T4 |
| `strategy.brief.intent` | string | W07 |
| `strategy.brief.stage` | string | T3 |
| `strategy.outline.initial` | object | W09 |

---

## F. Quality Gates

- [ ] Topic clearly defined
- [ ] Primary keyword identified or research flagged
- [ ] Audience segment resolved
- [ ] Intent classified
- [ ] Complexity assessment complete

---

## G. Execution

### Timeout

15 minutes

### Error Handling

Escalate missing critical inputs to orchestrator

### Next Worker

W02-SEOAEOGEOPlanning

---

*W01-ContentStrategyResearch.md | ROMA v2.3.3*
