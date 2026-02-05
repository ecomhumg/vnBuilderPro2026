---
vnbuilder:
  name: prompt-engineering
  description: L6-Cognitive prompt crafting techniques for agent prompts
  version: "2.0.0"
  always: false
  tier: [5]
---

# Prompt Engineering Skills

> **L6-Cognitive Prompt Crafting Techniques**
> **CoreModules Integration**: ContextBuilder prompt patterns

---

## L6 Prompt Structure

```markdown
# [PERSONA]
You are {role} with expertise in {domain}.
Your primary function is {function}.

# [CONTEXT]
## Input
{input_description}

## Constraints
- {constraint_1}
- {constraint_2}

# [TASK]
{clear_task_statement}

# [OUTPUT SCHEMA]
```json
{schema}
```

# [EXAMPLES] (optional)

{examples}

# [QUALITY CRITERIA]

- {criterion_1}
- {criterion_2}

```

---

## Prompt Quality Checklist

- [ ] Clear persona defined
- [ ] Context provided
- [ ] Task unambiguous
- [ ] Output format specified
- [ ] Constraints explicit
- [ ] Quality criteria stated

---

## Common Patterns

| Pattern | Use Case |
|---------|----------|
| Chain-of-Thought | Reasoning tasks |
| Few-Shot | Format learning |
| Zero-Shot | Simple tasks |
| Role-Play | Specialist behavior |
| Structured Output | JSON/YAML returns |

---

*Prompt Engineering Skills v1.0 | MASDesign-Workforce*
