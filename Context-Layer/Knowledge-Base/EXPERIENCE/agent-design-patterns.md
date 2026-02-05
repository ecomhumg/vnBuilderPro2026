# Agent Design Patterns

> **Best Practices & Anti-Patterns**

---

## Best Practices

### DO: Single Responsibility
```yaml
# GOOD: One focused agent
name: PatternMatcher
role: Match requirements to patterns
```

### DO: Clear Triggers
```yaml
# GOOD: Explicit trigger
triggers:
  on_event: pattern_search_complete
```

### DO: Typed Outputs
```yaml
# GOOD: Schema defined
writes:
  - key: patterns.ranked
    type: array
    schema: PatternRank[]
```

---

## Anti-Patterns

### DON'T: God Agent
```yaml
# BAD: Does too much
name: DoEverythingAgent
role: Parse, analyze, design, implement, validate
```

### DON'T: Implicit Dependencies
```yaml
# BAD: Assumes data exists
reads:
  - some.random.key  # Who writes this??
```

### DON'T: Magic Numbers
```yaml
# BAD: Hardcoded values
quality_threshold: 0.73  # Why 0.73?
```

---

*Agent Design Patterns v1.0 | MASDesign-Workforce*
