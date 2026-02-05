# search - General Search Command

> **CLAWDBOT v2.3.2** | Command | Search Operations

---

## Usage

```
/search <query> [--scope <scope>] [--type <type>]
```

## Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| query | Yes | Search term |
| --scope | Optional | memory, playbooks, skills, all |
| --type | Optional | keyword, semantic, exact |

## Purpose

Unified search across all workforce knowledge.

## Scopes

| Scope | Searches |
|-------|----------|
| memory | MEMORY.md + DailyLogs |
| playbooks | PLAYBOOKS/ directory |
| skills | SKILLS/ directory |
| experience | EXPERIENCE/ directory |
| all | All above (default) |

## Output

```
Search: "[query]"
Scope: [scope]
---
[Results organized by source]
---
Total: [X] results
```

---

*search.md | CLAWDBOT v2.3.2*
