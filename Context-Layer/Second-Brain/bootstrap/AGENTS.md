# AGENTS.md - Multi-Agent Coordination Configuration

> **{WorkforceName}-Workforce** | Bootstrap
> **Standard**: vnBuilderProMax v2.3.3

---

## Agent Architecture

| Attribute | Value |
|-----------|-------|
| **Topology** | 6-Tier HierarchicalSwarm |
| **Total Workers** | 22 |
| **Agents Per Worker** | 24 |
| **Total Agents** | 528 |
| **Autonomy Level** | L5 Full Auto |

---

## Tier-Agent Distribution

| Tier | Workers | Agents | Mode |
|------|---------|--------|------|
| 1 - Strategy | 4 | 96 | Sequential |
| 2 - Intelligence | 4 | 96 | Full Parallel |
| 3 - Content | 6 | 144 | Partial Parallel |
| 4 - Analysis | 4 | 96 | Barrier Sync |
| 5 - Validation | 2 | 48 | Sequential |
| 6 - Synthesis | 2 | 48 | Sequential |

---

## Agent Roles Per Worker

Each worker contains 24 agents distributed across 4 specialized roles:

```yaml
role_distribution:
  orchestrator: 2     # Coordinate worker execution
  specialist: 10      # Domain-specific tasks
  validator: 6        # Quality assurance
  synthesizer: 6      # Output aggregation
```

---

## Inter-Agent Communication

| Pattern | Use Case |
|---------|----------|
| **Memory Bus** | Persistent state sharing |
| **Direct Message** | Point-to-point coordination |
| **Broadcast** | Tier-wide announcements |
| **Barrier Sync** | Phase completion gates |

---

## Agent Capabilities

### Domain Capabilities

| Capability | Description |
|------------|-------------|
| **{Capability1}** | {Description1} |
| **{Capability2}** | {Description2} |
| **{Capability3}** | {Description3} |
| **{Capability4}** | {Description4} |
| **{Capability5}** | {Description5} |
| **{Capability6}** | {Description6} |
| **{Capability7}** | {Description7} |
| **{Capability8}** | {Description8} |

---

## Coordination Protocols

### Parallel Execution

```yaml
tier_2:
  mode: full_parallel
  workers: [W05, W06, W07, W08]
  barrier: all_complete
  timeout: 30min

tier_3:
  mode: partial_parallel
  workers: [W09, W10, W11, W12, W13]
  aggregator: W14
  timeout: 60min

tier_4:
  mode: barrier_sync
  workers: [W15, W16, W17, W18]
  barrier: atomic_phase
  timeout: 30min
```

---

## Agent Lifecycle

```yaml
lifecycle:
  initialization:
    - Load bootstrap context
    - Index available skills
    - Restore memory context
  
  execution:
    - Receive task assignment
    - Execute domain operations
    - Report progress to memory bus
  
  termination:
    - Persist execution logs
    - Update memory index
    - Release resources
```

---

*AGENTS.md v2.3.3 | {WorkforceName}-Workforce | 528 Agents*
