# W17 - PersonalizationWorker

> **Tier 4: Analysis** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W17 |
| **Name** | PersonalizationWorker |
| **Tier** | 4 - Analysis |
| **Agents** | 24 |
| **Primary Function** | Personalization and differentiation strategies |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Personalization Lead
mission: Create personalized pathways and differentiated experiences
scope: Personalization, differentiation, adaptive pathways
authority: Personalization rules, pathway design
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Differentiation Specialist | 6 | Differentiation strategies |
| Path Designer | 6 | Pathway creation |
| Analyst | 6 | User analysis |
| Adapter | 6 | Adaptation implementation |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W15, W16 | Analytics and competency maps |
| Downstream | W19 | Personalized pathways |
| Peer | W15, W16, W18 | Analysis coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `personalization.md` | Personalization methodology |
| Skill | `adaptive-pathways.md` | Pathway design |
| Experience | `differentiation.md` | Differentiation patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "personalization {domain}" --layer all --limit 5
  
OUTPUT:
  memory-write <personalization_plan> --layer 1 --category artifact --tags "personalization,pathways"
```

---

### A - Activation

**Input Schema:**

```json
{
  "analytics_report": "object",
  "competency_map": "object",
  "user_profiles": ["object"]
}
```

**Output Schema:**

```json
{
  "personalization_plan": {
    "pathways": ["object"],
    "adaptations": ["object"],
    "rules": ["object"]
  }
}
```

**Memory Bus Publications:**

- `personalization.pathways`
- `personalization.adaptations`
- `personalization.rules`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Insufficient profiles | Profile enrichment |
| Conflicting paths | Priority resolution |
| Adaptation failures | Fallback pathways |

---

## Quality Gate

- [ ] Pathways complete
- [ ] Adaptations tested
- [ ] Rules validated
- [ ] User coverage verified
- [ ] Memory bus keys published

---

*W17 PersonalizationWorker v1.0.0 | {WorkforceName}*
