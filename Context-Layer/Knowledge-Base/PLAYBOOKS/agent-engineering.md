# Agent Engineering Playbook

> **Best Practices for Agent Specification & Design**

---

## Agent Anatomy

```yaml
agent:
  name: "PatternAnalyzer"
  worker: "01-PatternResearchWorker"
  stage: "ANALYZE"
  
  role: "Analyze and rank patterns by problem fit"
  
  triggers:
    on_event: "pattern_search_complete"
    from_agent: "PatternSearcher"
  
  reads:
    - "patterns.search_results"
    - "requirements.parsed_prd"
  
  writes:
    - "patterns.ranked_list"
    - "patterns.match_scores"
  
  delegates_to: "PatternSynthesizer"
  
  quality_threshold: 0.80
```

---

## Agent Design Principles

### 1. Single Responsibility
Each agent does one thing well. Avoid multi-task agents.

### 2. Clear Triggers
Define explicit trigger conditions:
- `on_event`: Event-based activation
- `on_schedule`: Time-based activation
- `on_condition`: State-based activation

### 3. Typed Memory Access
Always use typed memory keys:
```
{domain}.{subdomain}  →  patterns.search_results
```

### 4. Chain of Delegation
Each agent knows its successor:
```
Analyzer → Synthesizer → Validator → Output
```

---

## L6-Cognitive Prompt Structure

```markdown
# Persona Block
You are {role} in {worker}. Your expertise is {domain}.

# Context
Given:
- {input_context}
- {constraints}

# Task
{primary_task}

# Output Schema
```json
{
  "result": "...",
  "confidence": 0.0-1.0,
  "rationale": "..."
}
```

# Constraints
- {constraint_1}
- {constraint_2}
```

---

## 6-Stage ROMA Agent Distribution

| Stage | Agent Count | Roles |
|-------|-------------|-------|
| INTAKE | 4 | Parser, Validator, Classifier, Router |
| ANALYZE | 4 | Analyzer, Matcher, Scorer, Synthesizer |
| DESIGN | 4 | Designer, Architect, Planner, Validator |
| IMPLEMENT | 4 | Generator, Writer, Formatter, Linker |
| VALIDATE | 4 | Checker, Tester, Scorer, Approver |
| DELIVER | 4 | Packager, Documenter, Handoff, Logger |

---

## Error Handling

Each agent must handle:
1. **Input validation failures** → Return error + reason
2. **Processing errors** → Retry with backoff
3. **Quality threshold misses** → Escalate or re-process
4. **Timeout** → Partial result + status

---

*Agent Engineering Playbook v1.0 | MASDesign-Workforce*
