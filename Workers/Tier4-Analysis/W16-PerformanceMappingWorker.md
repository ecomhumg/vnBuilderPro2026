# W16 - PerformanceMappingWorker

> **Tier 4: Analysis** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W16 |
| **Name** | PerformanceMappingWorker |
| **Tier** | 4 - Analysis |
| **Agents** | 24 |
| **Primary Function** | Performance tracking and competency mapping |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Performance Mapping Lead
mission: Map performance metrics to competencies and outcomes
scope: Competency mapping, performance tracking, outcome alignment
authority: Competency definitions, mapping standards
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Competency Specialist | 6 | Competency framework management |
| Mapper | 6 | Performance-to-competency mapping |
| Tracker | 6 | Progress tracking |
| Reporter | 6 | Performance reporting |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W15 | Analytics insights |
| Downstream | W17, W19 | Performance maps |
| Peer | W15, W17, W18 | Analysis coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `competency-mapping.md` | Mapping methodology |
| Skill | `performance-tracking.md` | Tracking techniques |
| Experience | `outcome-alignment.md` | Alignment patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "competency {domain} mapping" --layer all --limit 5
  
OUTPUT:
  memory-write <competency_map> --layer 1 --category artifact --tags "competency,mapping"
```

---

### A - Activation

**Input Schema:**

```json
{
  "analytics_report": "object",
  "competency_framework": "object",
  "tracking_scope": "string"
}
```

**Output Schema:**

```json
{
  "competency_map": {
    "mappings": ["object"],
    "progress_data": "object",
    "gaps": ["string"]
  }
}
```

**Memory Bus Publications:**

- `competency.map`
- `competency.progress`
- `competency.gaps`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Misalignment | Re-mapping review |
| Missing competencies | Framework update |
| Tracking gaps | Manual data entry |

---

## Quality Gate

- [ ] All competencies mapped
- [ ] Progress tracked
- [ ] Gaps identified
- [ ] Alignment verified
- [ ] Memory bus keys published

---

*W16 PerformanceMappingWorker v1.0.0 | {WorkforceName}*
