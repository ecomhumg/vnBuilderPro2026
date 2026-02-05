# W12 - ContentCreator4Worker

> **Tier 3: Content** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W12 |
| **Name** | ContentCreator4Worker |
| **Tier** | 3 - Content |
| **Agents** | 24 |
| **Primary Function** | Assessment and evaluation content creation |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Assessment Content Creator
mission: Create comprehensive assessment and evaluation materials
scope: Assessment design, rubric creation, evaluation criteria
authority: Assessment format decisions, evaluation standards
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Assessment Specialist | 6 | Assessment design expertise |
| Content Author | 6 | Assessment writing |
| Rubric Designer | 6 | Criteria development |
| Reviewer | 6 | Validity review |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W09-W11 | Content to assess |
| Downstream | W14 | Assessment content |
| Peer | W09-W13 | Coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `assessment-design.md` | Assessment methodology |
| Skill | `rubric-creation.md` | Rubric techniques |
| Experience | `evaluation-patterns.md` | Assessment patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "assessment {domain}" --layer all --limit 5
  
OUTPUT:
  memory-write <assessment_content> --layer 1 --category artifact --tags "content,assessment"
```

---

### A - Activation

**Input Schema:**

```json
{
  "content_assets": ["object"],
  "assessment_type": "string",
  "evaluation_levels": ["string"]
}
```

**Output Schema:**

```json
{
  "assessment_content": {
    "assessments": ["object"],
    "rubrics": ["object"],
    "criteria": ["string"]
  }
}
```

**Memory Bus Publications:**

- `content.assessment.items`
- `content.rubrics`
- `content.criteria`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Validity concerns | Expert review |
| Misalignment | Content re-mapping |
| Bias detection | Remediation |

---

## Quality Gate

- [ ] Assessment validity verified
- [ ] Rubrics complete
- [ ] Alignment confirmed
- [ ] Bias check passed
- [ ] Memory bus keys published

---

*W12 ContentCreator4Worker v1.0.0 | {WorkforceName}*
