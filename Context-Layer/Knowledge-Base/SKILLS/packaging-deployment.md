---
vnbuilder:
  name: packaging-deployment
  description: Bundle creation and release management for workforce deployment
  version: "2.0.0"
  always: false
  tier: [8]
---

# Packaging & Deployment Skills

> **Bundle Creation & Release Management**

---

## Bundle Structure

```
{WorkforceName}/
├── README.md
├── Second-Brain/
├── Knowledge-Base/
├── Workers/
└── Team Orchestration/
```

---

## Packaging Steps

1. **Verify completeness** - All files present
2. **Validate cross-refs** - No broken links
3. **Check quality** - E-O ≥ 0.85
4. **Generate manifest** - team-manifest.json
5. **Create archive** - Optional zip

---

## Deployment Targets

| Target | Path |
|--------|------|
| Production | `D:\AGENTS\_Workforce\` |
| Development | `D:\AGENTS\_Workforce-Dev\` |
| Archive | `D:\AGENTS\_Workforce-Archive\` |

---

## Release Notes Template

```markdown
# {WorkforceName} v{version}

## Summary
{brief_description}

## Workers
- {count} workers, {agent_count} agents

## Changes
- {change_1}
- {change_2}

## Known Issues
- {issue_1}
```

---

*Packaging & Deployment Skills v1.0 | MASDesign-Workforce*
