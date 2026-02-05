# memory-write - Write to Memory

> **CLAWDBOT v2.3.2** | Command | Memory Operations

---

## Usage

```
/memory-write <key> <content>
```

## Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| key | Yes | Namespaced key |
| content | Yes | Content to store |

## Purpose

Write or update a memory entry.

## Key Naming Convention

```
{domain}.{category}.{identifier}
```

### Domain Prefixes

- `seo.` - SEO-related memories
- `aeo.` - AEO-related memories
- `geo.` - GEO-related memories
- `eeat.` - E-E-A-T-related memories
- `content.` - Content patterns
- `client.` - Client-specific preferences

## Output

```
Written: [key]
Size: [X] bytes
Updated: [timestamp]
```

---

*memory-write.md | CLAWDBOT v2.3.2*
