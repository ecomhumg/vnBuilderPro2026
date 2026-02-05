# Memory Bus Contract

> **200+ Memory Keys for Deep Research Coordination**

---

## Session Context

| Key | Type | Description |
|-----|------|-------------|
| `session.id` | string | Unique session identifier |
| `session.mode` | enum | quick/standard/deep/enterprise |
| `session.started` | datetime | Session start time |
| `session.status` | enum | active/paused/complete |

## Query Context

| Key | Type | Description |
|-----|------|-------------|
| `query.original` | string | Original user query |
| `query.clarified` | string | Clarified query |
| `query.confidence` | float | Clarity confidence 0-1 |
| `query.focus_areas` | array | Identified focus areas |
| `query.needs_clarification` | bool | Clarification needed |

## Domain Intelligence

| Key | Type | Description |
|-----|------|-------------|
| `domain.primary` | string | Primary domain |
| `domain.secondary` | array | Related domains |
| `domain.experts` | array | Identified experts |
| `domain.technologies` | array | Relevant technologies |

## Research Protocol

| Key | Type | Description |
|-----|------|-------------|
| `protocol.type` | enum | exploratory/systematic/comparative |
| `protocol.approved` | bool | Human approval status |
| `protocol.scope` | object | Research scope definition |

## Source Strategy

| Key | Type | Description |
|-----|------|-------------|
| `sources.strategy` | object | Search strategy |
| `sources.databases` | array | Target databases |
| `sources.parameters` | object | Search parameters |

## Search Results

| Key | Type | Description |
|-----|------|-------------|
| `search.academic.results` | array | Academic findings |
| `search.technical.results` | array | Technical findings |
| `search.web.results` | array | Web findings |
| `search.total_count` | int | Total sources found |

## Verification

| Key | Type | Description |
|-----|------|-------------|
| `verify.claims` | array | Identified claims |
| `verify.status` | object | Verification status per claim |
| `verify.score` | float | Overall verification score |

## Extraction

| Key | Type | Description |
|-----|------|-------------|
| `extract.content` | array | Extracted content |
| `extract.citations` | object | Citation network |
| `extract.evidence` | array | Graded evidence |

## Synthesis

| Key | Type | Description |
|-----|------|-------------|
| `synthesis.themes` | array | Major themes |
| `synthesis.insights` | array | Unique insights |
| `synthesis.contradictions` | array | Conflicting findings |
| `synthesis.gaps` | array | Knowledge gaps |

## Quality

| Key | Type | Description |
|-----|------|-------------|
| `quality.coverage` | float | Source coverage score |
| `quality.verification` | float | Verification score |
| `quality.synthesis` | float | Synthesis quality |
| `quality.eo_score` | float | E-O quality score |

## Efficiency

| Key | Type | Description |
|-----|------|-------------|
| `efficiency.tokens` | int | Token usage |
| `efficiency.cost` | float | API cost |
| `efficiency.pareto` | bool | Pareto optimal |

## Output

| Key | Type | Description |
|-----|------|-------------|
| `output.report` | string | Final report |
| `output.format` | enum | markdown/json/pdf |
| `output.citations` | array | All citations |

---

*Memory Bus Contract v1.0 | DeepResearch-Workforce*
