# W07 - TechnologyIntelligenceWorker

> **Tier 2: Intelligence** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W07 |
| **Name** | TechnologyIntelligenceWorker |
| **Tier** | 2 - Intelligence |
| **Agents** | 24 |
| **Primary Function** | Technology evaluation and integration intelligence |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Technology Intelligence Lead
mission: Evaluate and recommend technology stack and integrations
scope: Technology scanning, tool evaluation, integration assessment
authority: Technology recommendations, integration decisions
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Tech Specialist | 6 | Technology research, scanning |
| Evaluator | 6 | Tool evaluation, comparison |
| Researcher | 6 | Trend analysis, benchmarking |
| Integrator | 6 | Integration assessment |

---

### O - Orchestration

```mermaid
graph LR
    A[Input: Integration Blueprint] --> B[Technology Scan]
    B --> C[Evaluation Phase]
    C --> D[Integration Assessment]
    D --> E[Recommendations]
    E --> F[Output: Technology Intelligence Report]
```

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W04 | Integration blueprint |
| Downstream | Tools layer | Technology requirements |
| Peer | W05, W06, W08 | Intelligence sync |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `technology-evaluation.md` | Evaluation framework |
| Skill | `tech-integration.md` | Integration techniques |
| Experience | `tech-stack.md` | Stack patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "technology {domain} stack" --layer all --limit 5
  
OUTPUT:
  memory-write <tech_intelligence> --layer 1 --category artifact --tags "technology,intelligence"
```

---

### A - Activation

**Trigger Conditions:**

- Integration blueprint received
- Technology evaluation requested
- Tool comparison needed

**Input Schema:**

```json
{
  "integration_blueprint": "object",
  "domain": "string",
  "tech_requirements": ["string"]
}
```

**Output Schema:**

```json
{
  "tech_intelligence": {
    "technology_scan": ["object"],
    "evaluations": ["object"],
    "recommendations": ["string"],
    "integration_plan": "object"
  }
}
```

**Memory Bus Publications:**

- `technology.intelligence.report`
- `technology.scan.results`
- `technology.recommendations`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Deprecated technology | Flag and suggest alternatives |
| Integration incompatibility | Assess middleware options |
| Missing evaluations | Expand technology scan |

---

## Quality Gate

- [ ] Technology landscape scanned
- [ ] All tools evaluated
- [ ] Integration compatibility verified
- [ ] Recommendations prioritized
- [ ] Risk assessment complete
- [ ] Memory bus keys published

---

*W07 TechnologyIntelligenceWorker v1.0.0 | {WorkforceName}*
