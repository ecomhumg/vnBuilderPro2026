# Memory Methods API

> **vnBuilderPro-MAS2026 Memory System** | Unified Methods Specification
>
> Following Nanobot MemoryStore Pattern with CLAWDBOT v2.2.0 Integration

---

## Overview

This document specifies the unified memory methods API for vnBuilderPro-MAS2026 workforces. All workers and components MUST use these methods for memory operations.

---

## Architecture

```
Memory/
├── MEMORY.md              # Layer 2: Curated Knowledge
├── DailyLogs/             # Layer 1: Daily Session Logs
│   └── YYYY-MM-DD.md
├── Sessions/              # Session state
├── State/                 # Persistent state
└── memory-methods.md      # This file
```

---

## Core Methods

### 1. `get_today_file() -> Path`

**Purpose**: Get path to today's daily log file

**Returns**: `Path` to `DailyLogs/YYYY-MM-DD.md`

**Example**:

```python
path = memory.get_today_file()
# Returns: DailyLogs/2026-02-03.md
```

---

### 2. `read_today() -> str`

**Purpose**: Read today's memory notes

**Returns**: Content of today's daily log, empty string if not exists

**Example**:

```python
content = memory.read_today()
# Returns: "# 2026-02-03\n\n## Session: SpecGapNiche..."
```

---

### 3. `append_today(content: str) -> None`

**Purpose**: Append content to today's memory notes

**Parameters**:

- `content`: Text to append

**Behavior**:

- Creates file with date header if not exists
- Appends content with newline separator

**Example**:

```python
memory.append_today("""
## [W06] Task: Design Topology
- **Time**: 2026-02-03T10:30:00
- **Status**: Completed
- **Output**: HierarchicalSwarm selected
""")
```

---

### 4. `read_long_term() -> str`

**Purpose**: Read long-term curated memory (MEMORY.md)

**Returns**: Content of MEMORY.md, empty string if not exists

**Example**:

```python
curated = memory.read_long_term()
# Returns: "# MEMORY.md - Layer 2: Long-term Curated Knowledge..."
```

---

### 5. `write_long_term(content: str) -> None`

**Purpose**: Write to long-term memory (MEMORY.md)

**Parameters**:

- `content`: Complete content to write

**⚠️ Warning**: Overwrites entire MEMORY.md. Use curation workflow for partial updates.

**Example**:

```python
memory.write_long_term(new_curated_content)
```

---

### 6. `get_recent_memories(days: int = 7) -> str`

**Purpose**: Get memories from the last N days

**Parameters**:

- `days`: Number of days to look back (default: 7)

**Returns**: Combined content from recent daily logs, separated by `---`

**Example**:

```python
recent = memory.get_recent_memories(days=3)
# Returns: "# 2026-02-03\n...\n---\n# 2026-02-02\n..."
```

---

### 7. `get_memory_context() -> str`

**Purpose**: Get complete memory context for LLM prompt

**Returns**: Formatted string with both Layer 2 and today's notes

**Structure**:

```markdown
## Long-term Memory
[Content of MEMORY.md]

## Today's Notes
[Content of DailyLogs/YYYY-MM-DD.md]
```

**Example**:

```python
context = memory.get_memory_context()
# Used by ContextBuilder.build_system_prompt()
```

---

## CLAWDBOT Command Mapping

| CLAWDBOT Command | Memory Method |
|------------------|---------------|
| `/memory-search` | Search across `get_memory_context()` |
| `/memory-get` | `read_long_term()` or `read_today()` |
| `/memory-write` | `append_today()` |
| `/compact` | Curation workflow |
| `/save-all` | Flush pending to `append_today()` |
| `/recall` | `get_recent_memories(days)` |

---

## Usage Patterns

### Worker Task Completion

```python
async def complete_task(self, task, result):
    # Log completion to DailyLogs
    log_entry = f"""
## [{self.worker_id}] Task: {task.name}
- **Time**: {datetime.now().isoformat()}
- **Status**: Completed
- **Quality**: {result.quality_score}
- **Output**: {result.summary}
"""
    self.memory.append_today(log_entry)
```

### Context Building

```python
def build_system_prompt(self):
    parts = []
    
    # Get memory context
    memory_context = self.memory.get_memory_context()
    if memory_context:
        parts.append(f"# Memory\n\n{memory_context}")
    
    return "\n\n---\n\n".join(parts)
```

### Curation Workflow

```python
async def compact_memory(self):
    # Read recent memories
    recent = self.memory.get_recent_memories(days=7)
    
    # Extract entries marked [CURATE]
    curated_entries = extract_curated(recent)
    
    # Read existing long-term
    existing = self.memory.read_long_term()
    
    # Merge curated entries
    updated = merge_curated(existing, curated_entries)
    
    # Write updated long-term
    self.memory.write_long_term(updated)
```

---

## Curation Tags

Use these tags in DailyLogs to mark entries for promotion:

| Tag | Purpose |
|-----|---------|
| `[CURATE]` | Promote to MEMORY.md on compact |
| `[DECISION]` | Record architectural decision |
| `[FACT]` | Record verified fact |
| `[PATTERN]` | Record quality pattern |
| `[OPTIMIZE]` | Record optimization learned |

**Example**:

```markdown
## [W06] Architecture Decision
[CURATE] [DECISION] Selected HierarchicalSwarm for 22-worker topology
- Rationale: Best for tiered coordination with clear hierarchy
- Alternatives considered: LinearParallel, AgentRearrange
- Confidence: 0.95
```

---

## Best Practices

### 1. **Always Log Task Completion**

```python
# ✅ Good
memory.append_today(f"## Task Complete: {task.name}\n...")

# ❌ Bad
# Completing task without logging
```

### 2. **Use Structured Logging**

```python
# ✅ Good
log = f"""
## [{worker_id}] {action}
- **Time**: {timestamp}
- **Status**: {status}
"""

# ❌ Bad
log = f"{worker_id} did {action}"
```

### 3. **Mark Important Entries**

```python
# ✅ Good
memory.append_today("[CURATE] Key insight: L5 requires 6 modules")

# ❌ Bad
memory.append_today("L5 requires 6 modules")  # Won't be curated
```

### 4. **Check Existence Before Read**

```python
# ✅ Good
content = memory.read_today()
if content:
    process(content)

# Context is already handled
context = memory.get_memory_context()  # Returns "" if empty
```

---

## Integration Points

| Component | Usage |
|-----------|-------|
| ContextBuilder | `get_memory_context()` in `build_system_prompt()` |
| AgentLoop | `append_today()` on task completion |
| Workers | All methods for task-specific operations |
| Autonomous-Core | `get_recent_memories()` for decision context |
| SubagentManager | Read-only access via parent worker |

---

*vnBuilderPro-MAS2026 | Memory Methods API v2.3.0 | Nanobot Pattern*
