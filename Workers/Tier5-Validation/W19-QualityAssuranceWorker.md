# W19 - QualityAssuranceWorker

> **Tier 5: Validation** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W19 |
| **Name** | QualityAssuranceWorker |
| **Tier** | 5 - Validation |
| **Agents** | 24 |
| **Primary Function** | Quality assurance and validation |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Quality Assurance Lead
mission: Ensure all outputs meet quality standards and requirements
scope: Quality auditing, validation, compliance verification
authority: Quality decisions, validation approvals
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| QA Specialist | 6 | Quality testing |
| Auditor | 6 | Compliance auditing |
| Validator | 6 | Validation execution |
| Reporter | 6 | QA reporting |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W15-W18 | Analysis outputs |
| Downstream | W21 | Validated outputs |
| Peer | W20 | Validation coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `quality-assurance.md` | QA methodology |
| Skill | `validation-testing.md` | Testing techniques |
| Experience | `qa-patterns.md` | QA patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "quality {domain} validation" --layer all --limit 5
  
OUTPUT:
  memory-write <qa_report> --layer 1 --category artifact --tags "quality,validation"
```

---

### A - Activation

**Input Schema:**

```json
{
  "analysis_outputs": ["object"],
  "quality_criteria": "object",
  "validation_scope": "string"
}
```

**Output Schema:**

```json
{
  "qa_report": {
    "test_results": ["object"],
    "issues": ["object"],
    "approval_status": "string",
    "recommendations": ["string"]
  }
}
```

**Memory Bus Publications:**

- `quality.report`
- `quality.issues`
- `quality.approval`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Validation failure | Issue tracking and remediation |
| Critical defects | Block and escalate |
| Missing criteria | Criteria extension |

---

## Quality Gate

- [ ] All tests executed
- [ ] Issues documented
- [ ] Remediation tracked
- [ ] Approval obtained
- [ ] Memory bus keys published

---

*W19 QualityAssuranceWorker v1.0.0 | {WorkforceName}*
