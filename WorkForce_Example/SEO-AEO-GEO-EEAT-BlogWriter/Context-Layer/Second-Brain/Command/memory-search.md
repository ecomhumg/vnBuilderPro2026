# memory-search - Search Memory

> **CLAWDBOT v2.3.2** | Command | Memory Operations

---

## Usage

```
/memory-search <query> [--category <cat>] [--limit <n>]
```

## Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| query | Yes | Search term or phrase |
| --category | Optional | Filter by category |
| --limit | Optional | Max results (default: 10) |

## Purpose

Semantic search across MEMORY.md and daily logs.

## Search Modes

| Mode | Trigger | Behavior |
|------|---------|----------|
| Keyword | Default | Exact match on terms |
| Semantic | Phrase query | Meaning-based matching |
| Pattern | Regex prefix | Regular expression |

## Output

```
Search: "[query]"
Results: [X] matches

1. [Key] - [Snippet...] (Score: 0.95)
2. [Key] - [Snippet...] (Score: 0.88)
...
```

---

*memory-search.md | CLAWDBOT v2.3.2*
