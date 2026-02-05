# Memory Bus Design Playbook

> **Typed Key Schema Design for Agent Communication**

---

## Memory Bus Principles

1. **Typed Keys**: All keys follow `domain.subdomain` pattern
2. **Clear Ownership**: Each key has one writer
3. **Explicit Reads**: Agents declare what they read
4. **State Immutability**: Write-once, read-many

---

## Key Naming Convention

```
{tier}.{worker_short}.{data_type}

Examples:
- research.patterns.search_results
- architecture.swarm.selected_type
- agents.specs.worker_01
```

---

## Standard Key Categories

| Category | Pattern | Example |
|----------|---------|---------|
| Input | `input.{source}` | `input.user_request` |
| Output | `output.{target}` | `output.final_bundle` |
| Research | `research.{type}` | `research.patterns.matched` |
| Requirements | `requirements.{field}` | `requirements.worker_count` |
| Architecture | `architecture.{component}` | `architecture.topology` |
| Agents | `agents.{property}` | `agents.specifications` |
| Quality | `quality.{metric}` | `quality.eo_score` |
| Control | `control.{signal}` | `control.stage_complete` |

---

## Key Schema Template

```yaml
key: "architecture.swarm.config"
type: "object"
schema:
  swarm_type: string
  worker_count: integer
  tier_structure: array
writer: "06-SwarmArchitectWorker"
readers:
  - "07-AgentTopologyWorker"
  - "08-MemoryBusDesignWorker"
ttl: "session"
```

---

## Memory Bus Size Targets

| Workforce Size | Recommended Keys |
|---------------|-----------------|
| Small (1-5 workers) | 50-80 |
| Medium (6-15 workers) | 80-120 |
| Large (16+ workers) | 120-180 |

**MASDesign-Workforce Target**: 150+ keys

---

*Memory Bus Design Playbook v1.0 | MASDesign-Workforce*
