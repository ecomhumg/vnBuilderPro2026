# Swarm Configuration Playbook

> **Guide to Selecting and Configuring Swarm Types**

---

## Available Swarm Types

| Swarm Type | Best For | Workers | Complexity |
|------------|----------|---------|------------|
| **SequentialWorkflow** | Simple pipelines | 1-3 | Low |
| **ConcurrentWorkflow** | Parallel tasks | 4-8 | Medium |
| **HierarchicalSwarm** | Multi-level | 9-15 | High |
| **SwarmRouter** | Dynamic routing | Any | Medium |
| **HeavySwarm** | Research-intensive | 16+ | Very High |

---

## Selection Criteria

### SequentialWorkflow
```
✓ Tasks must run in order
✓ Each step depends on previous
✓ Simple error handling
✓ Easy to debug
```

### ConcurrentWorkflow
```
✓ Independent parallel tasks
✓ Need speed optimization
✓ Aggregation at end
✓ Moderate complexity
```

### HierarchicalSwarm
```
✓ Clear management hierarchy
✓ Sub-task delegation
✓ Multiple capability tiers
✓ Complex coordination
```

### SwarmRouter
```
✓ Dynamic task routing
✓ Content-based decisions
✓ Flexible paths
✓ Universal fallback
```

### HeavySwarm
```
✓ Many workers (16+)
✓ Research-intensive
✓ Long-running operations
✓ Complex state management
```

---

## Configuration Templates

### SwarmRouter Config
```json
{
  "swarm_type": "SwarmRouter",
  "routing_rules": [
    {
      "condition": "request.type == 'pattern_search'",
      "route_to": "01-PatternResearchWorker"
    },
    {
      "condition": "request.type == 'architecture'",
      "route_to": "06-SwarmArchitectWorker"
    }
  ],
  "default_route": "04-RequirementsAnalysisWorker",
  "timeout_ms": 30000
}
```

---

## Tier Configuration

| Tier Level | Workers | Parallel | Sequential |
|------------|---------|----------|------------|
| Tier 1 | 3 | Yes | No |
| Tier 2 | 2 | Yes | No |
| Tier 3 | 3 | Yes | No |
| Tier 4 | 2 | Yes | No |
| Tier 5 | 3 | Yes | No |
| Tier 6 | 3 | Yes | No |
| Tier 7 | 2 | Yes | No |
| Tier 8 | 2 | Yes | No |

**Note**: Tiers execute sequentially, workers within tiers execute in parallel.

---

*Swarm Configuration Playbook v1.0 | MASDesign-Workforce*
