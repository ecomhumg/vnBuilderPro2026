---
vnbuilder:
  name: memory-contracts
  description: Typed key schema design and Memory Bus management patterns
  version: "2.0.0"
  always: false
  tier: [3,6]
---

# Memory Contracts Skills

> **Typed Key Schema Design & Management**
> **CoreModules Integration**: MemoryStore, Memory Bus patterns

---

## Key Types

| Type | Format | Example |
|------|--------|---------|
| String | `"value"` | `"HierarchicalSwarm"` |
| Integer | `123` | `20` |
| Float | `0.85` | Quality score |
| Boolean | `true/false` | `true` |
| Array | `[...]` | Worker list |
| Object | `{...}` | Complex data |

---

## Key Categories

```
input.*          # User inputs
output.*         # Final outputs
control.*        # Flow control signals
research.*       # Research tier data
requirements.*   # Requirements data
architecture.*   # Architecture data
knowledge.*      # Knowledge base data
agents.*         # Agent specifications
quality.*        # Quality metrics
```

---

## Contract Template

```yaml
keys:
  - name: "architecture.swarm.config"
    type: object
    schema:
      swarm_type: {type: string, required: true}
      worker_count: {type: integer, required: true}
      tier_structure: {type: array, required: true}
    writer: "06-SwarmArchitectWorker"
    readers: ["07-AgentTopologyWorker", "08-MemoryBusDesignWorker"]
    persistence: session
    ttl: null
```

---

*Memory Contracts Skills v1.0 | MASDesign-Workforce*
