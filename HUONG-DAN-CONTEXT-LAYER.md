# Hướng Dẫn Tích Hợp Context-Layer

> **vnBuilderProMax v2.3.4** | Kiến trúc 6-Tier HierarchicalSwarm
>
> Tài liệu hướng dẫn liên kết Context-Layer với Workforce

---

## Tổng Quan

Context-Layer là trung tâm tri thức cho Workforce, cung cấp ngữ cảnh, kỹ năng, và bộ nhớ cho workers.

| Thành Phần | Mục Đích |
|------------|----------|
| **Knowledge-Base/** | 3 tầng kiến thức domain (PLAYBOOKS, SKILLS, EXPERIENCE) |
| **Second-Brain/** | Hub thông minh (Brain, Memory, Command, bootstrap) |
| **CoreModules/** | Đặc tả module kiểu Nanobot |
| **context-injection-config.json** | Cấu hình liên kết worker-context |

---

## Các Files Chính

### 1. context-injection-config-TEMPLATE.json

File mẫu để tạo workforce mới:

```
Context-Layer/context-injection-config-TEMPLATE.json
```

**Nội dung chính:**

- `tier_bindings`: Liên kết 6 tier với playbooks, skills, commands
- `worker_context_map`: Liên kết chi tiết W01-W22
- `execution_hooks`: Hooks cho on_session_start, on_tier_enter, on_worker_activate

### 2. context-loader.md

Tài liệu giải thích quy trình context injection:

```
Context-Layer/context-loader.md
```

---

## Kiến Trúc 6-Tier

| Tier | Tên | Workers | Chế Độ |
|------|-----|---------|--------|
| 1 | Strategy | W01-W04 | Sequential |
| 2 | Intelligence | W05-W08 | Parallel |
| 3 | Content | W09-W14 | Partial Parallel (W14: aggregator) |
| 4 | Analysis | W15-W18 | Barrier Sync |
| 5 | Validation | W19-W20 | Sequential |
| 6 | Synthesis | W21-W22 | Sequential |

---

## Quy Trình Context Injection

### Phase 0: Bootstrap (Tự động)

1. Load `context-injection-config.json`
2. `ContextBuilder.load_bootstrap()` - Load AGENTS.md, SOUL.md
3. `SkillsLoader.load_skills()` - Index skills
4. `MemoryStore.get_memory_context()` - Load MEMORY.md

### Khi Worker Được Kích Hoạt

```yaml
on_worker_activate:
  - ContextBuilder.inject_context(worker_id)
  - SkillsLoader.filter_by_worker(worker_id)
  - AgentLoop.initialize(worker_context)
```

---

## Hướng Dẫn Tạo Workforce Mới

### Bước 1: Copy Template

```powershell
Copy-Item "Context-Layer/context-injection-config-TEMPLATE.json" `
          "Team Orchestration/context-injection-config.json"
```

### Bước 2: Thay Thế Placeholders

- `{WorkforceName}` → Tên workforce
- `{PB01}`, `{PB02}` → Tên playbook thực tế
- `{SK01}`, `{SK02}` → Tên skill thực tế

### Bước 3: Tùy Chỉnh Worker Bindings

Trong `worker_context_map`, điều chỉnh:

- `primary_playbook`: Playbook chính
- `skills`: Mảng skills
- `commands`: CLAWDBOT commands được phép
- `bootstrap`: Bootstrap files cho worker

---

## CoreModules

| Module | Methods Chính |
|--------|---------------|
| MemoryStore | `read_today()`, `append_today()`, `get_memory_context()` |
| ContextBuilder | `load_bootstrap()`, `get_tier_context()`, `inject_context()` |
| SkillsLoader | `load_skills()`, `get_tier_skills()`, `filter_by_worker()` |
| AgentLoop | `initialize()`, `run(max_iterations=20)` |
| SubagentManager | `spawn_parallel()`, `coordinate_tier()`, `aggregate_results()` |

---

## Files Đã Được Cập Nhật

| File | Thay Đổi |
|------|----------|
| `Context-Layer/README.md` | v2.3.2, CoreModules integration |
| `Context-Layer/context-builder.md` | 6-tier, injection methods |
| `Team Orchestration/swarm-router-config.json` | 8-tier → 6-tier |
| `Team Orchestration/WORKFLOW.md` | Phase 0: Bootstrap |
| `Workers/_WORKER_TEMPLATE.md` | C - Context Binding section |

---

## Tham Khảo

- Template: [context-injection-config-TEMPLATE.json](Context-Layer/context-injection-config-TEMPLATE.json)
- Docs: [context-loader.md](Context-Layer/context-loader.md)
- Reference: [SEO-AEO-GEO-EEAT-BlogWriter](WorkForce_Example/SEO-AEO-GEO-EEAT-BlogWriter/) (Chỉ tham khảo CẤU TRÚC, không sao chép nội dung)

---

*Hướng dẫn v1.1 | vnBuilderProMax v2.3.4 | 6-Tier HierarchicalSwarm*
