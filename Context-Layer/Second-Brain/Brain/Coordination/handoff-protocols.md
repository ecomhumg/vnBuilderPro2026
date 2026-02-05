# Handoff Protocols

> **Inter-Worker Data Exchange Contracts**

---

## Handoff Types

| Type | Data Flow | Trigger |
|------|-----------|---------|
| **Sequential** | Worker A → Worker B | Stage completion |
| **Broadcast** | Worker A → All listeners | Event publish |
| **Request-Response** | Worker A ↔ Worker B | Query/result |
| **Aggregate** | Workers A,B,C → Worker D | Parallel completion |

---

## Standard Handoff Contract

```yaml
handoff:
  source_worker: "06-SwarmArchitectWorker"
  target_worker: "07-AgentTopologyWorker"
  handoff_type: "sequential"
  
  payload:
    required:
      - swarm_type           # Selected swarm pattern
      - worker_count         # Number of workers
      - tier_structure       # Tier definitions
    optional:
      - constraints          # Special requirements
      - preferences          # Optimization hints
      
  validation:
    schema: "swarm_output_v1"
    required_fields: true
    quality_threshold: 0.80
    
  on_failure:
    retry: 2
    fallback: "escalate_to_orchestrator"
```

---

## Tier-to-Tier Handoffs

| From Tier | To Tier | Key Data | Memory Bus Key |
|-----------|---------|----------|----------------|
| Research | Requirements | Domain KB, patterns | `research.domain_kb` |
| Requirements | Architecture | Worker specs, deps | `requirements.worker_specs` |
| Architecture | Knowledge | Swarm config, topology | `architecture.swarm_config` |
| Knowledge | Agent Eng. | Playbooks, skills | `knowledge.playbooks` |
| Agent Eng. | Integration | Agent specs, prompts | `agents.specifications` |
| Integration | Quality | Orchestration config | `integration.orchestration` |
| Quality | Deploy | Validated bundle | `quality.approved_bundle` |

---

## Handoff Validation

```python
def validate_handoff(payload, contract):
    errors = []
    
    # Check required fields
    for field in contract.required:
        if field not in payload:
            errors.append(f"Missing required: {field}")
    
    # Validate schema
    if not schema_valid(payload, contract.schema):
        errors.append("Schema validation failed")
    
    # Check quality threshold
    if payload.quality_score < contract.quality_threshold:
        errors.append(f"Quality {payload.quality_score} < {contract.quality_threshold}")
    
    return {'valid': len(errors) == 0, 'errors': errors}
```

---

*Handoff Protocols v1.0 | MASDesign-Workforce*
