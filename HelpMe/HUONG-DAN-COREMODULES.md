# Hướng Dẫn Sử Dụng CoreModules

> **vnBuilderPro-MAS2026 v2.3.0** | Tích Hợp Nanobot Pattern
>
> Hướng dẫn chi tiết sử dụng hệ thống CoreModules với 10 ví dụ thực tế

---

## 📋 Tổng Quan

CoreModules cung cấp kiến trúc nhẹ và hiệu quả cho việc quản lý trạng thái, ngữ cảnh và thực thi agent. Dựa trên framework [nanobot](https://github.com/HKUDS/nanobot), tối ưu cho hệ thống 528-agent HierarchicalSwarm.

| Module | Mục Đích | File |
|--------|----------|------|
| **MemoryStore** | Bộ nhớ hai lớp | `CoreModules/memory-store.md` |
| **ContextBuilder** | Lắp ráp prompt | `CoreModules/context-builder.md` |
| **SkillsLoader** | Tải kỹ năng | `CoreModules/skills-loader.md` |
| **AgentLoop** | Vòng lặp xử lý | `CoreModules/agent-loop.md` |
| **SubagentManager** | Thực thi song song | `CoreModules/subagent-manager.md` |

---

## 🚀 Bắt Đầu Nhanh

### Cấu Trúc Thư Mục

```
Context-Layer/
├── CoreModules/              # 5 module specs (MỚI)
│   ├── memory-store.md
│   ├── context-builder.md
│   ├── skills-loader.md
│   ├── agent-loop.md
│   └── subagent-manager.md
├── Knowledge-Base/
│   └── SKILLS/               # Skills với YAML frontmatter
└── Second-Brain/
    ├── bootstrap/            # 5 bootstrap files (MỚI)
    │   ├── AGENTS.md
    │   ├── SOUL.md
    │   ├── USER.md
    │   ├── TOOLS.md
    │   └── IDENTITY.md
    └── Memory/
        ├── MEMORY.md         # Layer 2: Kiến thức curated
        ├── DailyLogs/        # Layer 1: Log hàng ngày
        └── memory-methods.md # API specification
```

---

## 📚 10 Ví Dụ Thực Tế

### Ví Dụ 1: Đọc/Ghi Memory

**Mục tiêu**: Ghi nhật ký hoàn thành task và đọc ngữ cảnh memory

```python
# Ghi vào DailyLogs
memory.append_today("""
## [W06] Task: Thiết kế Topology
- **Thời gian**: 2026-02-03T10:30:00
- **Trạng thái**: Hoàn thành
- **Kết quả**: HierarchicalSwarm được chọn
""")

# Đọc ngữ cảnh đầy đủ
context = memory.get_memory_context()
# Trả về: Layer 2 (MEMORY.md) + Today's notes

# Đọc lịch sử 7 ngày
recent = memory.get_recent_memories(days=7)
```

---

### Ví Dụ 2: Tạo Skill Mới

**Mục tiêu**: Tạo skill theo chuẩn format mới

```markdown
---
vnbuilder:
  name: healthcare-compliance
  description: HIPAA và quy định y tế cho workforce
  version: "1.0.0"
  always: false
  tier: [1,4,7]
  requires:
    env: [MEDICAL_API_KEY]
---

# Healthcare Compliance

## Tổng Quan
Skill này cung cấp hướng dẫn tuân thủ HIPAA...

## Sử Dụng
1. Kiểm tra yêu cầu bảo mật
2. Áp dụng mã hóa PHI
3. Ghi nhật ký audit trail

## Ví Dụ
...
```

Lưu tại: `Knowledge-Base/SKILLS/healthcare-compliance.md`

---

### Ví Dụ 3: Cấu Hình Progressive Loading

**Mục tiêu**: Thiết lập skill always-loaded

```yaml
# Skill được tải vào mọi prompt
---
vnbuilder:
  name: roma-pipeline
  description: 6-stage ROMA pipeline pattern
  always: true  # Luôn tải
  tier: []      # Tất cả tiers
---
```

```yaml
# Skill chỉ hiện summary, đọc khi cần
---
vnbuilder:
  name: kubernetes-deploy
  description: Kubernetes deployment patterns
  always: false  # Tải theo yêu cầu
  tier: [8]
  requires:
    bins: [kubectl]
---
```

---

### Ví Dụ 4: Tùy Chỉnh Bootstrap Files

**Mục tiêu**: Thay đổi hành vi worker

Chỉnh sửa `bootstrap/AGENTS.md`:

```markdown
## Core Principles

### 1. Quality First
- Tất cả outputs phải đạt quality gates
- Validate với 107 MAS patterns
- Tuân theo ROMA pipeline

### 2. Memory Discipline (TÙY CHỈNH)
- Log TẤT CẢ sự kiện (không chỉ significant)
- Sử dụng tag [CURATE] cho thông tin quan trọng
- Flush memory mỗi 30 phút
```

---

### Ví Dụ 5: Spawn Subagent

**Mục tiêu**: Thực thi task song song

```python
# Worker W06 spawn subagents cho research
results = []

# Spawn 3 subagents song song
await manager.spawn(
    task="Research HierarchicalSwarm patterns cho enterprise",
    label="Research-1"
)
await manager.spawn(
    task="Research LinearParallel patterns cho streaming", 
    label="Research-2"
)
await manager.spawn(
    task="Research AgentRearrange patterns cho flexibility",
    label="Research-3"
)

# Tiếp tục công việc khác...
await process_other_tasks()

# Thu thập kết quả
results = await manager.get_pending_results()
for r in results:
    if r["status"] == "completed":
        incorporate_finding(r["result"])
```

---

### Ví Dụ 6: Context Building với Skills

**Mục tiêu**: Build system prompt với tier-specific skills

```python
# ContextBuilder tự động load skills theo tier
builder = ContextBuilder(workspace)

# Tier 3 worker - tự động load architecture skills
prompt = builder.build_system_prompt(skill_names=["swarm-topology", "memory-bus"])

# Kết quả prompt structure:
# 1. Core identity (vnBuilderPro-MAS2026 Worker)
# 2. Bootstrap files (AGENTS, SOUL, USER, TOOLS)
# 3. Memory context (MEMORY.md + Today's notes)
# 4. Active skills (always: true)
# 5. Skills summary (for progressive loading)
```

---

### Ví Dụ 7: Curation Workflow

**Mục tiêu**: Chuyển thông tin từ DailyLogs sang MEMORY.md

**Bước 1**: Đánh dấu entries trong DailyLogs

```markdown
## [W06] Architecture Decision
[CURATE] [DECISION] Chọn HierarchicalSwarm cho 22-worker topology
- Lý do: Tốt nhất cho coordination với hierarchy rõ ràng
- Alternatives: LinearParallel, AgentRearrange
- Confidence: 0.95
```

**Bước 2**: Chạy compact

```bash
/compact
```

**Bước 3**: Entries được promote lên MEMORY.md

```markdown
# Workforce Decisions

| Decision ID | Date | Decision | Rationale |
|-------------|------|----------|-----------|
| DEC-003 | 2026-02-03 | HierarchicalSwarm cho 22-worker | Best for tiered coordination |
```

---

### Ví Dụ 8: Requirements Checking

**Mục tiêu**: Kiểm tra dependencies trước khi load skill

```yaml
# Skill với requirements
---
vnbuilder:
  name: docker-deploy
  description: Docker deployment automation
  requires:
    bins: [docker, docker-compose]
    env: [DOCKER_HOST]
---
```

Khi requirements không đạt, skill hiển thị:

```xml
<skill name="docker-deploy" available="false" missing="docker-compose not found">
Docker deployment automation
</skill>
```

Worker có thể cài đặt missing requirements hoặc bỏ qua skill.

---

### Ví Dụ 9: Custom Identity Override

**Mục tiêu**: Tùy chỉnh identity cho domain cụ thể

Chỉnh sửa `bootstrap/IDENTITY.md`:

```yaml
## Domain-Specific Overrides

### Fintech (Mới thêm)

domain_override:
  compliance: [PCI-DSS, SOX, GDPR]
  terminology: Financial Technology
  quality_threshold: 0.99
  validation: 
    - Encryption required
    - Audit trail mandatory
    - Real-time monitoring
  special_instructions: |
    Tất cả transactions phải được log.
    KYC/AML checks bắt buộc.
    Data residency theo quy định local.
```

---

### Ví Dụ 10: Full AgentLoop Execution

**Mục tiêu**: Chạy worker với đầy đủ CoreModules

```python
from vnbuilder.core import AgentLoop
from pathlib import Path

# Khởi tạo worker
workspace = Path("D:/BuilderPro/_vnBuilderPro-MAS2026")
worker = AgentLoop(
    worker_id="W06",
    tier=3,
    workspace=workspace,
    model="claude-sonnet-4-20250514",
    max_iterations=20
)

# Chạy loop
await worker.run()

# Hoặc xử lý trực tiếp
response = await worker.process_direct(
    content="Thiết kế HierarchicalSwarm topology cho 8 workers healthcare domain",
    session_key="healthcare-2026-02-03"
)

# Kết quả:
# - Task được xử lý qua ContextBuilder
# - Memory context được include
# - Skills tier 3 được load
# - Kết quả log vào DailyLogs
# - Response trả về
```

---

## 🔧 Cấu Hình Nâng Cao

### Memory Configuration

Chỉnh sửa `memory-config.json`:

```json
{
  "architecture": {
    "layers": {
      "layer2": {
        "file": "MEMORY.md",
        "type": "curated"
      },
      "layer1": {
        "directory": "DailyLogs",
        "format": "YYYY-MM-DD.md"
      }
    }
  },
  "indexing": {
    "chunking": {
      "chunkSize": 400,
      "overlapPercentage": 80
    }
  }
}
```

### Bootstrap Customization

Thứ tự áp dụng overrides:

1. AGENTS.md (base)
2. SOUL.md (personality)
3. USER.md (preferences)
4. TOOLS.md (tool guidelines)
5. IDENTITY.md (custom overrides)

---

## 💡 Best Practices

### 1. Sử Dụng Curation Tags

```markdown
[CURATE] - Promote to MEMORY.md
[DECISION] - Quyết định kiến trúc
[FACT] - Sự thật đã xác minh
[PATTERN] - Pattern chất lượng
[OPTIMIZE] - Học được optimization
```

### 2. Structured Logging

```markdown
## [{worker_id}] {action}
- **Time**: {timestamp}
- **Status**: {status}
- **Quality**: {score}
- **Notes**: {observations}
```

### 3. Progressive Skill Usage

```python
# Đọc full skill khi cần
skill_content = skills.load_skill("advanced-pattern")

# Không load tất cả skills
# Chỉ load skills cần thiết cho task
```

### 4. Subagent Limits

```python
# Max 10 subagents per worker
# Reduced iterations (10 vs 20)
# Use for parallel, independent tasks only
```

---

## 🔗 Tham Khảo

| Tài Liệu | Vị Trí |
|----------|--------|
| CoreModules README | `CoreModules/README.md` |
| Memory Store | `CoreModules/memory-store.md` |
| Context Builder | `CoreModules/context-builder.md` |
| Skills Loader | `CoreModules/skills-loader.md` |
| Agent Loop | `CoreModules/agent-loop.md` |
| Subagent Manager | `CoreModules/subagent-manager.md` |
| Nanobot Knowledge-Base | `E:\AGENTS\GithubClone\Repos2026\nanobot\_Knowledge-Base\` |

---

*vnBuilderPro-MAS2026 | Hướng Dẫn CoreModules v2.3.0 | Nanobot Pattern*
