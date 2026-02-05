# memory-get - Retrieve Memory Entry

> **CLAWDBOT v2.3.2** | Command | Memory Operations

---

## Usage

```
/memory-get <key>
```

## Parameters

| Parameter | Required | Description |
|-----------|----------|-------------|
| key | Yes | Memory key to retrieve |

## Purpose

Retrieve a specific memory entry by key.

## Key Format

```
{category}.{topic}.{identifier}
```

### Examples

```
seo.meta.title_optimization
aeo.voice.answer_format
eeat.author.bio_template
geo.entity.nap_format
```

## Output

```
Memory: [key]
---
[Content of the memory entry]
---
Last updated: [timestamp]
```

---

*memory-get.md | CLAWDBOT v2.3.2*
