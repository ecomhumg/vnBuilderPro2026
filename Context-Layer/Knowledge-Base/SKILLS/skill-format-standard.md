# Skill Format Standard

> **vnBuilderPro-MAS2026 Knowledge-Base** | SKILL Format Template
>
> Standard format for all SKILL files following Nanobot pattern

---

## Overview

All skills in the Knowledge-Base must follow this format to enable:

- Progressive loading by SkillsLoader
- Requirements checking
- Tier-based filtering
- Always-loaded designation

---

## YAML Frontmatter Specification

```yaml
---
vnbuilder:
  name: skill-name              # Required: Unique identifier (lowercase, hyphenated)
  description: Brief description # Required: Shown in skill summary (max 100 chars)
  version: "1.0.0"              # Optional: Skill version
  always: false                 # Optional: Always include in context (default: false)
  tier: [1,2,3,4,5,6,7,8]       # Optional: Applicable worker tiers (empty = all)
  requires:                     # Optional: Dependencies
    bins: [tool1, tool2]        # Required CLI tools
    env: [API_KEY, SECRET]      # Required environment variables
---
```

---

## Frontmatter Fields

| Field | Required | Type | Default | Description |
|-------|----------|------|---------|-------------|
| `name` | ✅ | string | - | Unique skill identifier |
| `description` | ✅ | string | - | Brief description for summary |
| `version` | ❌ | string | "1.0.0" | Semantic version |
| `always` | ❌ | boolean | false | Always load in context |
| `tier` | ❌ | array[int] | [] | Applicable tiers (empty = all) |
| `requires.bins` | ❌ | array[string] | [] | Required CLI tools |
| `requires.env` | ❌ | array[string] | [] | Required env vars |

---

## Content Structure

```markdown
---
[YAML Frontmatter]
---

# Skill Name

## Overview
Brief description of what this skill does and when to use it.

## Usage
Step-by-step instructions for using this skill.

## Methods/Patterns
Detailed documentation of methods, patterns, or techniques.

## Examples
Concrete examples demonstrating skill application.

## References
Links to related skills, documentation, or external resources.

---

*vnBuilderPro-MAS2026 Skill | {Skill Name} v{version}*
```

---

## Complete Example

```markdown
---
vnbuilder:
  name: roma-pipeline
  description: 6-stage ROMA worker execution pipeline pattern
  version: "2.0.0"
  always: true
  tier: [1,2,3,4,5,6,7,8]
---

# ROMA Pipeline

## Overview

ROMA (Role-Orchestration-Methods-Activation) defines the standardized
6-stage execution pipeline for all 22 workers in vnBuilderPro-MAS2026.

## Usage

1. **Role Definition**: Define worker identity and capabilities
2. **Orchestration**: Specify coordination and handoff protocols
3. **Methods**: Document core methods and algorithms
4. **Activation**: Define triggers and activation conditions
5. **Quality Gates**: Specify validation criteria
6. **Output**: Define expected deliverables

## Stages

### Stage 1: Role Definition

```yaml
role:
  id: W06
  name: Architecture Designer
  tier: 3
  capabilities:
    - Swarm topology design
    - Pattern application
    - Memory bus design
```

### Stage 2: Orchestration

```yaml
orchestration:
  receives_from: [W04, W05]
  sends_to: [W10, W11]
  parallel_peers: [W07, W08, W09]
```

### Stage 3: Methods

```python
def design_topology(requirements: Requirements) -> Topology:
    pattern = select_pattern(requirements.scale)
    topology = apply_pattern(pattern, requirements)
    return validate_topology(topology)
```

### Stage 4: Activation

| Trigger | Action |
|---------|--------|
| Requirements received | Start design |
| Pattern selected | Apply to topology |
| Topology validated | Send to Knowledge tier |

### Stage 5: Quality Gates

| Gate | Threshold |
|------|-----------|
| Pattern compliance | 100% |
| Memory bus coverage | ≥ 200 keys |
| Swarm efficiency | ≥ 0.85 E-O |

### Stage 6: Output

- `swarm-topology.md`
- `memory-bus-contract.md`
- `efficiency-report.md`

## Examples

### Example: Healthcare Workforce

```
Input: 8 workers, healthcare domain
Output: HierarchicalSwarm topology with HIPAA compliance
```

## References

- [AgentLoop](../../CoreModules/agent-loop.md)
- [Pattern Library](../../Research/patterns/)

---

*vnBuilderPro-MAS2026 Skill | ROMA Pipeline v2.0.0*

```

---

## Progressive Loading Behavior

### Always-Loaded Skills (always: true)

- Full content included in every system prompt
- Use sparingly - consumes tokens
- Best for: Core skills used in every task

### On-Demand Skills (always: false)

- Only summary shown in system prompt
- Worker reads full content when needed
- Best for: Domain-specific or occasional skills

---

## Requirements Checking

### Binary Requirements

```yaml
requires:
  bins: [docker, kubectl]
```

SkillsLoader checks: `shutil.which(bin_name)`

### Environment Variables

```yaml
requires:
  env: [OPENAI_API_KEY, AWS_ACCESS_KEY]
```

SkillsLoader checks: `os.environ.get(env_var)`

### Unavailable Skills

Skills with unmet requirements show in summary with missing info:

```xml
<skill name="kubernetes-deploy" available="false" missing="kubectl not found">
Kubernetes deployment patterns
</skill>
```

---

## Migration Guide

### Converting Existing Skills

1. Add YAML frontmatter
2. Use `name` from filename (without .md)
3. Extract first paragraph for `description`
4. Set `tier` based on content
5. Add `requires` if dependencies exist

### Example Migration

**Before:**

```markdown
# Memory Contracts

This skill defines the Memory Bus contract specifications...
```

**After:**

```markdown
---
vnbuilder:
  name: memory-contracts
  description: Memory Bus contract specifications for cross-worker state
  tier: [3,6]
---

# Memory Contracts

This skill defines the Memory Bus contract specifications...
```

---

*vnBuilderPro-MAS2026 | Skill Format Standard v2.3.0 | Nanobot Pattern*
