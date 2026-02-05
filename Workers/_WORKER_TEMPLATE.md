# W{XX} - {WorkerName}

> **{WorkforceName}-Workforce** | Worker | Tier {N} {TierName}
> **Standard**: vnBuilderProMax v2.3.3 | ROMA C Compliant

---

## Section A: Identity

| Attribute | Value |
|-----------|-------|
| **Worker ID** | W{XX} |
| **Name** | {WorkerName} |
| **Tier** | {N} - {TierName} |
| **Role** | {Role} |
| **Agents** | 24 (2 orchestrator, 10 specialist, 6 validator, 6 synthesizer) |

---

## Section B: Responsibilities

### Primary Mission

{Mission statement describing the worker's core function}

### Key Tasks

1. {Task1}
2. {Task2}
3. {Task3}
4. {Task4}
5. {Task5}

---

## Section C: Context Injection

### Playbooks

- **{PB-XXX}**: {Description} (primary)
- **{PB-XXX}**: {Description}

### Skills

- **{SK-XXX}**: {Description}
- **{SK-XXX}**: {Description}

### Commands

- `memory-search`: Search patterns
- `memory-write`: Log decisions
- `recall`: Retrieve prior decisions

### Bootstrap

- AGENTS.md, SOUL.md, USER.md

---

## Section D: Inputs

| Source | Type | Key |
|--------|------|-----|
| User Request | Task | Input params |
| Bootstrap | Context | Bootstrap files |
| Memory | Prior | {Patterns} |

---

## Section E: Outputs

| Key | Type | Consumer |
|-----|------|----------|
| `{namespace}.{key1}` | {Type} | {Consumer} |
| `{namespace}.{key2}` | {Type} | {Consumer} |
| `{namespace}.{key3}` | Flag | {Consumer} |

---

## Section F: Quality Gates

- [ ] {QualityCheck1} (≥95%)
- [ ] {QualityCheck2}
- [ ] {QualityCheck3}
- [ ] {QualityCheck4}

---

## Section G: Execution

```yaml
mode: {sequential/parallel/barrier_sync}
timeout: {XX} min
priority: P{X} {Priority}
dependencies: {Dependencies}
```

---

*W{XX}-{WorkerName}.md | ROMA C Compliant | v2.3.3*
