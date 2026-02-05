# Handoff Protocols

> Cross-worker communication and data transfer specifications.

## Handoff Types

### Type 1: Sequential Handoff

```yaml
pattern: "tier_to_tier"
description: "Standard tier progression"
protocol:
  1. Source worker completes output
  2. Validate output schema
  3. Write to Memory Bus
  4. Signal downstream workers
  5. Target workers read from Memory Bus
```

### Type 2: Parallel Merge

```yaml
pattern: "multi_to_one"
description: "Multiple sources to single consumer"
protocol:
  1. All source workers write outputs
  2. Aggregator detects completion
  3. Merge results with deduplication
  4. Pass merged output downstream
```

### Type 3: Broadcast

```yaml
pattern: "one_to_multi"
description: "Single source to multiple consumers"
protocol:
  1. Source worker writes output
  2. All subscribers notified
  3. Each subscriber processes independently
```

## Memory Bus Integration

| Handoff Point | Key Pattern | Producers | Consumers |
|---------------|-------------|-----------|-----------|
| Query → Search | `query.*` | W01-W03 | W04-W05 |
| Strategy → Acquisition | `search.*` | W04-W05 | W06-W08, W21 |
| Acquisition → Extraction | `results.*` | W06-W08, W21 | W09-W10 |
| Extraction → Reading | `content.*` | W09-W10 | W11-W14 |
| Reading → Analysis | `reading.*` | W11-W14 | W15-W17 |
| Analysis → Validation | `analysis.*` | W15-W17 | W18-W19 |
| Validation → Delivery | `validation.*` | W18-W19 | W20 |

---

*Handoff Protocols v1.0.0 | ScholarDeepResearch-Workforce*
