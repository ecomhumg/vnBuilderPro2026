# W22 - CertificationWorker

> **Tier 6: Synthesis** | {WorkforceName}  
> **ROMA Pipeline** | vnBuilderProMax v2.1.0

---

## Role Definition

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W22 |
| **Name** | CertificationWorker |
| **Tier** | 6 - Synthesis |
| **Agents** | 24 |
| **Primary Function** | Certification, credentialing, and final delivery |

---

## ROMA Pipeline

### R - Role

```yaml
identity: Certification Lead
mission: Issue certifications and manage final credential delivery
scope: Certification, credential issuance, completion verification
authority: Certification decisions, credential standards
```

**Agent Roles (4 × 6 agents):**

| Role | Count | Responsibilities |
|------|-------|------------------|
| Certification Specialist | 6 | Certification processing |
| Credential Designer | 6 | Credential design |
| Validator | 6 | Completion validation |
| Issuer | 6 | Credential issuance |

**Dependencies:**

| Direction | Worker | Data |
|-----------|--------|------|
| Upstream | W21 | Final reports |
| Downstream | Output delivery | Certified outputs |
| Peer | W21 | Synthesis coordination |

---

### M - Methods

**KB Integration:**

| Type | Reference | Usage |
|------|-----------|-------|
| Playbook | `certification.md` | Certification methodology |
| Skill | `credentialing.md` | Credential techniques |
| Experience | `delivery-patterns.md` | Delivery patterns |

**Memory Operations:**

```
INTAKE:
  memory-search "certification {domain}" --layer all --limit 5
  
OUTPUT:
  memory-write <certification_record> --layer 2 --category certification --tags "certification,credentials"
```

---

### A - Activation

**Input Schema:**

```json
{
  "final_report": "object",
  "certification_criteria": "object",
  "recipients": ["object"]
}
```

**Output Schema:**

```json
{
  "certification_record": {
    "certifications": ["object"],
    "credentials": ["object"],
    "completion_status": "object",
    "registry": "object"
  }
}
```

**Memory Bus Publications:**

- `certification.records`
- `credentials.issued`
- `completion.registry`

---

## Error Handling

| Error | Resolution |
|-------|------------|
| Incomplete requirements | Hold certification |
| Issuance failure | Manual override |
| Registry errors | Backup sync |

---

## Quality Gate

- [ ] All requirements verified
- [ ] Certifications valid
- [ ] Credentials issued
- [ ] Registry updated
- [ ] Memory bus keys published

---

*W22 CertificationWorker v1.0.0 | {WorkforceName}*
