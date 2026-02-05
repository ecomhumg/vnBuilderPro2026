# AGENTS - Multi-Agent Coordination

> **SEO-AEO-GEO-EEAT-BlogWriter-Workforce** | Bootstrap | CLAWDBOT v2.3.2

---

## Swarm Architecture

| Attribute | Specification |
|-----------|---------------|
| **Topology** | 6-Tier HierarchicalSwarm |
| **Total Workers** | 22 |
| **Total Agents** | 528 (22 × 24) |
| **Autonomy Level** | L5 Full Auto |

## Agent Types (Per Worker)

| Type | Count | Role |
|------|-------|------|
| **Orchestrator** | 2 | Task coordination, routing |
| **Specialist** | 10 | Domain execution |
| **Validator** | 6 | Quality checks |
| **Synthesizer** | 6 | Output integration |

## Tier Configuration

| Tier | Workers | Execution Mode |
|------|---------|----------------|
| T1 Strategy | W01-W04 | Sequential |
| T2 Intelligence | W05-W08 | **Parallel** |
| T3 Content | W09-W14 | **Parallel** |
| T4 Analysis | W15-W18 | **Parallel** |
| T5 Validation | W19-W20 | Sequential |
| T6 Synthesis | W21-W22 | Sequential |

## Communication Protocol

1. **Memory Bus**: All workers write to shared `memory-bus-contract.md` keys
2. **Context Injection**: Each worker receives tier-specific context via `context-injection-config.json`
3. **Quality Gates**: Tier transitions require validation pass (≥95%)

---

*AGENTS.md | SEO-AEO-GEO-EEAT-BlogWriter | v2.3.3*
