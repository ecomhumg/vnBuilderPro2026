# W15 - DataAnalyticsWorker

> **Tier 4: Analysis** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W15 |
| **Name** | DataAnalyticsWorker |
| **Tier** | 4 - Analysis |
| **Agents** | 24 |
| **Primary Function** | Data collection, analysis, and insights generation |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Data Analytics Lead
mission: Analyze integrated content and generate actionable insights
scope: Data analytics, pattern detection, insights generation
authority: Analytics methodology, insight prioritization
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Data Analyst | 6 | Data processing, analysis |
| Visualizer | 6 | Data visualization, dashboards |
| Interpreter | 6 | Insight interpretation |
| Reporter | 6 | Analytics reporting |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W14 | Integrated content |
| Downstream | W17, W18 | Analytics insights |
| Peer | W16-W18 | Analysis coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `data-analytics.md` | Analytics methodology |
| Skill | `data-visualization.md` | Visualization techniques |
| Experience | `insights-generation.md` | Insight patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "analytics {domain}" --layer all --limit 5
  
OUTPUT:
  memory-write <analytics_report> --layer 1 --category artifact --tags "analytics,insights"
```

---

### A - Activation

**Input Schema:**

```json
{
  "integrated_package": "object",
  "metrics": ["string"],
  "analytics_depth": "string"
}
```

**Output Schema:**

```json
{
  "analytics_report": {
    "data_summary": "object",
    "patterns": ["object"],
    "insights": ["string"],
    "visualizations": ["object"]
  }
}
```

**Memory Bus Publications:**

- `analytics.report`
- `analytics.patterns`
- `analytics.insights`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Insufficient data | Request more data |
| Ambiguous patterns | Multi-scenario analysis |
| Visualization errors | Template fallback |

---

## Quality Gate

- [ ] Data processed completely
- [ ] Patterns identified
- [ ] Insights actionable
- [ ] Visualizations clear
- [ ] Memory bus keys published

---

*W15 DataAnalyticsWorker v1.0.0 | {WorkforceName}*
