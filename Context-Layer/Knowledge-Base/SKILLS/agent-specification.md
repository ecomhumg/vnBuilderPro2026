---
vnbuilder:
  name: agent-specification
  description: Technical guide for writing agent definitions with YAML specs
  version: "2.0.0"
  always: false
  tier: [5]
---

# Agent Specification Skills

> **Technical Guide for Writing Agent Definitions**
> **CoreModules Integration**: AgentLoop specification patterns

---

## Specification Template

```yaml
agent:
  id: "{worker_num}-{stage_abbrev}-{seq}"
  name: "{DescriptiveName}"
  worker: "{##-WorkerName}"
  stage: "{STAGE}"
  
  role: "{One-line role description}"
  
  cognitive_level: "L6"
  
  triggers:
    primary:
      type: "event|schedule|condition"
      source: "{source}"
    fallback:
      type: "timeout"
      after_ms: 30000
  
  reads:
    required:
      - "{key.path}"
    optional:
      - "{key.path}"
  
  writes:
    - "{key.path}"
  
  delegates_to: "{next_agent_id}"
  
  error_handling:
    on_failure: "retry|escalate|skip"
    max_retries: 3
    
  quality:
    threshold: 0.80
    validation: "{validation_type}"
```

---

## Naming Conventions

| Component | Pattern | Example |
|-----------|---------|---------|
| Agent ID | `{WW}-{SS}-{NN}` | `01-AN-02` |
| Agent Name | PascalCase | `PatternAnalyzer` |
| Memory Key | dot.notation | `patterns.ranked_list` |

---

## ROMA Stage Mapping

| Stage | Abbrev | Agents |
|-------|--------|--------|
| INTAKE | IN | Parser, Validator, Classifier, Router |
| ANALYZE | AN | Analyzer, Matcher, Scorer, Synthesizer |
| DESIGN | DE | Designer, Architect, Planner, Validator |
| IMPLEMENT | IM | Generator, Writer, Formatter, Linker |
| VALIDATE | VA | Checker, Tester, Scorer, Approver |
| DELIVER | DL | Packager, Documenter, Handoff, Logger |

---

*Agent Specification Skills v1.0 | MASDesign-Workforce*
