# W20-ComplianceValidation

> **Tier 5** | Validation | Sequential | SEO-AEO-GEO-EEAT-BlogWriter

---

## A. Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W20 |
| **Name** | ComplianceValidation |
| **Role** | Compliance Certification Officer |
| **Tier** | 5 - Validation |
| **Mode** | Sequential |

---

## B. Responsibilities

1. Verify all E-E-A-T requirements met
2. Validate schema correctness
3. Confirm legal disclaimer presence (YMYL)
4. Issue compliance certification

---

## C. Context Injection

### Playbooks

- `PB-002-EEATComplianceChecklist`

---

## D. Inputs

| Key | Source |
|-----|--------|
| `validation.quality.*` | W19 |
| `strategy.eeat.*` | W03 |
| `content.schema.*` | W13 |

---

## E. Outputs

| Key | Consumer |
|-----|----------|
| `validation.compliance.certified` | W21, W22 |
| `validation.compliance.issues` | W21 |
| `validation.compliance.timestamp` | W22 |
| `validation.compliance.version` | W22 |

---

## F. Quality Gates

- [ ] E-E-A-T threshold met (85 YMYL / 70 general)
- [ ] All required signals present
- [ ] Schema validates in Rich Results Test
- [ ] Disclaimers present if required

---

## G. Execution

### Certification Status

- CERTIFIED: Full compliance
- CONDITIONAL: Minor gaps noted
- REJECTED: Critical gaps, block publication

---

*W20-ComplianceValidation.md | ROMA v2.3.3*
