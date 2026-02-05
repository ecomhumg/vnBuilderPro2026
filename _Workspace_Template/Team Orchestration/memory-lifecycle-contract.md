# Memory Lifecycle Contract

> **SEO-AEO-GEO-EEAT-BlogWriter** | Key Management | CLAWDBOT v2.3.2

---

## Lifecycle Stages

```
CREATE → ACTIVE → STALE → ARCHIVE/PRUNE
```

---

## Stage Definitions

| Stage | TTL | Behavior |
|-------|-----|----------|
| CREATE | 0 | Key written by producer |
| ACTIVE | 7 days | Available for read/update |
| STALE | 7-30 days | Eligible for compaction |
| ARCHIVE | 30+ days | Elevated or pruned |

---

## Key Categories

### Ephemeral Keys (Auto-prune after 7 days)

- `*.temp.*`
- `*.draft.*`
- `*.progress.*`

### Session Keys (Active current session only)

- `*.current.*`
- `*.session.*`

### Persistent Keys (Always preserve)

- `*.final.*`
- `*.pattern.*`
- `*.certified.*`

---

## Compaction Rules

1. Keys accessed 3+ times → Elevate to MEMORY.md
2. Similar keys (0.85 similarity) → Merge
3. Orphaned keys (no consumer) → Mark stale

---

## Pruning Rules

1. Ephemeral keys > 7 days → Prune
2. Stale keys > 30 days without access → Prune
3. Persistent keys → Never prune

---

*memory-lifecycle-contract.md | v2.3.3*
