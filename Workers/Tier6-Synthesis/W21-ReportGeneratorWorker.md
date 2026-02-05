# W21 - ReportGeneratorWorker

> **Tier 6: Synthesis** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W21 |
| **Name** | ReportGeneratorWorker |
| **Tier** | 6 - Synthesis |
| **Agents** | 24 |
| **Primary Function** | Report generation and deliverable packaging |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Report Generator Lead
mission: Generate comprehensive reports and package final deliverables
scope: Report generation, deliverable packaging, documentation
authority: Report format decisions, deliverable structure
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Report Designer | 6 | Report structure design |
| Data Compiler | 6 | Data aggregation |
| Visualizer | 6 | Report visualization |
| Publisher | 6 | Report publishing |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W19, W20 | Validated outputs |
| Downstream | W22 | Final reports |
| Peer | W22 | Synthesis coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `report-generation.md` | Report methodology |
| Skill | `data-visualization.md` | Visualization techniques |
| Experience | `deliverable-patterns.md` | Delivery patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "reports {domain}" --layer all --limit 5
  
OUTPUT:
  memory-write <final_report> --layer 1 --category artifact --tags "reports,deliverables"
```

---

### A - Activation

**Input Schema:**

```json
{
  "validated_outputs": ["object"],
  "report_template": "string",
  "audience": "string"
}
```

**Output Schema:**

```json
{
  "final_report": {
    "executive_summary": "string",
    "detailed_report": "object",
    "visualizations": ["object"],
    "deliverables": ["object"]
  }
}
```

**Memory Bus Publications:**

- `reports.final`
- `reports.summary`
- `deliverables.package`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Missing data | Request from source |
| Format issues | Template revision |
| Publish failures | Retry with fallback |

---

## Quality Gate

- [ ] All data compiled
- [ ] Reports complete
- [ ] Visualizations rendered
- [ ] Deliverables packaged
- [ ] Memory bus keys published

---

*W21 ReportGeneratorWorker v1.0.0 | {WorkforceName}*
