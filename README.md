# True Detective Universal

> Universal root cause analysis for any codebase. Hypothesis-driven, parallel exploration, no fixing.

**"Don't guess, trace. Don't fix, understand."**

---

## Features

- **Hypothesis-First** - Generate 3-5 hypotheses before reading any code
- **Parallel Exploration** - Validate multiple hypotheses concurrently using Task agents
- **Evidence-Based** - Every conclusion must have code evidence
- **No Fixing** - Pure analysis, outputs root cause report only
- **Language Agnostic** - Works with any programming language or framework

## 4-Phase Workflow

```
Phase 1: PARSE
  Keywords → Classification → Code Structure Exploration → Hypotheses

Phase 2: EXPLORE (Parallel)
  ┌──────────┐  ┌──────────┐  ┌──────────┐
  │ Hypo A   │  │ Hypo B   │  │ Hypo C   │  ← Parallel Task agents
  └────┬─────┘  └────┬─────┘  └────┬─────┘
       ↓             ↓             ↓
    Evidence A    Evidence B    Evidence C

Phase 3: CONVERGE
  Evidence merge → Deep reasoning (ultrathink) → Root cause lock

Phase 4: REPORT
  Structured report → Evidence chain → Timeline (optional)
```

## Problem Categories

| Category | Keywords |
|----------|----------|
| P1: Async/Concurrency | "sometimes", "race condition", "intermittent" |
| P2: State Management | "after restart", "inconsistent", "cache" |
| P3: UI/Rendering | "not showing", "flicker", "stale" |
| P4: Config/Data | "config", "parameter", "not found" |
| P5: Resource/Dependency | "load failed", "null", "missing" |
| P6: Lifecycle | "on startup", "first time", "after close" |

## Usage

```
/true-detective-universal [problem description]
/tdu [problem description]
```

## Output

- Code structure exploration results
- Hypothesis list with verification status
- Evidence collection with code snippets
- Root cause analysis report

**Does NOT output**: Fix code, PR, or file modifications

---

# True Detective Universal (中文)

> 通用根因分析工具，适用于任意代码库。假设驱动，并行探索，只分析不修复。

**"不要猜测，要追踪。不要修复，要理解。"**

---

## 特性

- **假设先行** - 读代码前先生成 3-5 个假设
- **并行探索** - 使用 Task 子代理并发验证多个假设
- **证据为王** - 每个结论必须有代码证据支撑
- **禁止修复** - 纯分析，只输出根因报告
- **语言无关** - 适用于任何编程语言和框架

## 四阶段工作流

```
Phase 1: 解析
  关键词提取 → 问题分类 → 代码结构探索 → 假设生成

Phase 2: 探索 (并行)
  ┌──────────┐  ┌──────────┐  ┌──────────┐
  │ 假设 A   │  │ 假设 B   │  │ 假设 C   │  ← 并行 Task 子代理
  └────┬─────┘  └────┬─────┘  └────┬─────┘
       ↓             ↓             ↓
    证据集 A      证据集 B      证据集 C

Phase 3: 汇聚
  证据合并 → 深度推理 (ultrathink) → 根因锁定

Phase 4: 报告
  结构化报告 → 证据链 → 时序图 (可选)
```

## 问题分类

| 分类 | 典型关键词 |
|------|------------|
| P1: 异步/并发 | "有时候"、"偶发"、"竞态" |
| P2: 状态管理 | "重启后"、"不一致"、"缓存" |
| P3: UI/渲染 | "不显示"、"闪烁"、"不刷新" |
| P4: 配置/数据 | "配置"、"参数"、"找不到" |
| P5: 资源/依赖 | "加载失败"、"空引用"、"缺失" |
| P6: 生命周期 | "启动时"、"第一次"、"关闭后" |

## 使用方法

```
/true-detective-universal [问题描述]
/tdu [问题描述]
```

## 输出物

- 代码结构探索结果
- 假设列表及验证状态
- 证据集合 (含代码片段)
- 根因分析报告

**不输出**: 修复代码、PR、文件修改

---

## License

MIT

## Author

**Yoji** - The fear of the Lord is beginning of wisdom. -- Proverbs 9:10

---

*Created for Claude Code skill ecosystem*
