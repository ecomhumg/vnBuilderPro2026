# MemoryStore - Persistent Memory System

> **Module Documentation**: vnBuilderPro-MAS2026 CoreModules
>
> Dual-layer persistent memory: Daily Logs + Long-term Memory (CLAWDBOT v2.2.0 Enhanced)

---

## 📋 Overview

| Attribute | Value |
|-----------|-------|
| **Source** | nanobot `agent/memory.py` pattern |
| **Architecture** | Two-Layer CLAWDBOT v2.2.0 |
| **Storage** | Markdown files in Memory/ |
| **Integration** | 528-agent HierarchicalSwarm |

---

## 🏗️ Memory Architecture

```
Context-Layer/Second-Brain/Memory/
├── MEMORY.md              # Layer 2: Curated Knowledge (Long-term)
├── DailyLogs/
│   ├── 2026-02-03.md      # Today's notes
│   ├── 2026-02-02.md      # Yesterday's notes
│   └── ...                # Historical daily notes
├── Sessions/              # Session state
├── State/                 # Persistent state
└── memory-config.json     # Configuration
```

---

## 📚 Class Structure (Conceptual)

```python
class MemoryStore:
    """
    Memory system for vnBuilderPro-MAS2026 workforces.
    
    Supports daily logs (DailyLogs/YYYY-MM-DD.md) and long-term 
    memory (MEMORY.md) following CLAWDBOT v2.2.0 standard.
    """
    
    def __init__(self, workspace: Path):
        self.workspace = workspace
        self.memory_dir = workspace / "Context-Layer" / "Second-Brain" / "Memory"
        self.daily_logs_dir = self.memory_dir / "DailyLogs"
        self.memory_file = self.memory_dir / "MEMORY.md"
```

---

## 🔧 Core Methods

### `get_today_file() -> Path`

Get path to today's memory file.

```python
def get_today_file(self) -> Path:
    """Get path to today's memory file."""
    return self.daily_logs_dir / f"{today_date()}.md"
```

### `read_today() -> str`

Read today's memory notes.

```python
def read_today(self) -> str:
    """Read today's memory notes."""
    today_file = self.get_today_file()
    if today_file.exists():
        return today_file.read_text(encoding="utf-8")
    return ""
```

### `append_today(content: str) -> None`

Append content to today's memory notes.

```python
def append_today(self, content: str) -> None:
    """Append content to today's memory notes."""
    today_file = self.get_today_file()
    
    if today_file.exists():
        existing = today_file.read_text(encoding="utf-8")
        content = existing + "\n" + content
    else:
        # Add header for new day
        header = f"# {today_date()}\n\n"
        content = header + content
    
    today_file.write_text(content, encoding="utf-8")
```

### `read_long_term() -> str`

Read long-term memory (MEMORY.md).

```python
def read_long_term(self) -> str:
    """Read long-term memory (MEMORY.md)."""
    if self.memory_file.exists():
        return self.memory_file.read_text(encoding="utf-8")
    return ""
```

### `write_long_term(content: str) -> None`

Write to long-term memory (MEMORY.md).

```python
def write_long_term(self, content: str) -> None:
    """Write to long-term memory (MEMORY.md)."""
    self.memory_file.write_text(content, encoding="utf-8")
```

### `get_recent_memories(days: int = 7) -> str`

Get memories from the last N days.

```python
def get_recent_memories(self, days: int = 7) -> str:
    """
    Get memories from the last N days.
    
    Args:
        days: Number of days to look back.
    
    Returns:
        Combined memory content.
    """
    memories = []
    today = datetime.now().date()
    
    for i in range(days):
        date = today - timedelta(days=i)
        date_str = date.strftime("%Y-%m-%d")
        file_path = self.daily_logs_dir / f"{date_str}.md"
        
        if file_path.exists():
            content = file_path.read_text(encoding="utf-8")
            memories.append(content)
    
    return "\n\n---\n\n".join(memories)
```

### `get_memory_context() -> str`

Get memory context for the agent.

```python
def get_memory_context(self) -> str:
    """
    Get memory context for the agent.
    
    Returns:
        Formatted memory context including long-term and recent memories.
    """
    parts = []
    
    # Long-term memory (Layer 2)
    long_term = self.read_long_term()
    if long_term:
        parts.append("## Long-term Memory\n" + long_term)
    
    # Today's notes (Layer 1)
    today = self.read_today()
    if today:
        parts.append("## Today's Notes\n" + today)
    
    return "\n\n".join(parts) if parts else ""
```

---

## 🔄 Memory Flow

```mermaid
graph TD
    W1[Worker: Task Complete] --> W2[append_today content]
    W2 --> W3[DailyLogs/YYYY-MM-DD.md]
    W3 --> C1[/compact command]
    C1 --> C2[Summarize DailyLogs]
    C2 --> C3[Promote to MEMORY.md]
    R1[ContextBuilder.build_system_prompt] --> R2[MemoryStore.get_memory_context]
    R2 --> R3[Read MEMORY.md]
    R2 --> R4[Read today notes]
    R3 --> R5[Include in system prompt]
    R4 --> R5
```

---

## 💡 Memory Types

### Long-term Memory (MEMORY.md) - Layer 2

**Purpose**: Persistent facts, preferences, important context, curated knowledge

**Content Categories**:

| Category | Description | Example |
|----------|-------------|---------|
| **Decisions** | Architectural decisions with rationale | DEC-001: HierarchicalSwarm for 22+ workers |
| **Facts** | Verified domain facts | FACT-001: 528 agents = 22 × 24 |
| **Patterns** | Quality patterns with success rate | QP-001: ROMA Pipeline 94% |
| **Optimizations** | Learned optimizations | OPT-001: Chunk size 400 +23% accuracy |

### Daily Notes (DailyLogs/YYYY-MM-DD.md) - Layer 1

**Purpose**: Session-specific notes, temporary context, execution logs

**Example Content**:

```markdown
# 2026-02-03

## Session: SpecGapNiche-Rebuild
- Started workforce rebuild at 09:48
- Completed structural reorganization
- [CURATE] Key insight: L5 autonomy requires 6 modules

## Execution Log
- Phase 1 complete: Knowledge-Base verified
- Phase 2 complete: CLAWDBOT upgraded
```

---

## 📊 Memory Integration Points

| Component | Integration |
|-----------|-------------|
| ContextBuilder | Calls `get_memory_context()` in `build_system_prompt()` |
| AgentLoop | Memory included in every worker request |
| Skills | Can access memory via MemoryStore |
| Workers | `append_today()` on task completion |
| Autonomous-Core | `get_recent_memories(7)` for decision context |

---

## 🔧 CLAWDBOT v2.2.0 Integration

This MemoryStore integrates with the existing CLAWDBOT command registry:

| Command | MemoryStore Method |
|---------|-------------------|
| `/memory-search` | Search across `get_memory_context()` |
| `/memory-get` | `read_long_term()` or `read_today()` |
| `/memory-write` | `append_today()` or `write_long_term()` |
| `/compact` | Trigger curation from Layer 1 → Layer 2 |
| `/save-all` | Flush all pending to DailyLogs |

---

## 💡 Best Practices

### 1. **Structured Long-term Memory**

Use markdown headers to organize:

```markdown
# Workforce Decisions
| ID | Date | Decision | Rationale |
...

# Domain Facts
| ID | Fact | Confidence |
...
```

### 2. **Daily Note Headers**

Each daily note gets automatic date header:

```markdown
# 2026-02-03

[Content appended throughout the day]
```

### 3. **Curation Tags**

Mark entries for promotion to Layer 2:

```markdown
[CURATE] Important insight: ...
[CURATE] Decision: ...
```

### 4. **Memory Retrieval**

Agent automatically sees:

- All long-term memory (MEMORY.md)
- Today's notes only (not historical by default)

To access historical notes, use `get_recent_memories(days=N)`.

---

## 🔗 Related Modules

| Module | Relationship |
|--------|--------------|
| [ContextBuilder](context-builder.md) | Consumes memory context |
| [AgentLoop](agent-loop.md) | Memory included in processing |
| [SkillsLoader](skills-loader.md) | Skills can read memory |
| [SubagentManager](subagent-manager.md) | Subagents share memory context |

---

*vnBuilderPro-MAS2026 CoreModules | MemoryStore v2.3.0 | Nanobot Pattern*
