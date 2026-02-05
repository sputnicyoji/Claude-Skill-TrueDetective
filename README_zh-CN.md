# True Detective Universal

[English](README.md) | [日本語](README_ja.md) | 中文

> **"不要猜测，要追踪。不要修复，要理解。"**

**True Detective Universal** 是一个用于系统化根因分析的 AI 编程助手技能。它采用假设驱动的调查方法，通过并行探索找到 Bug 的真正根源——且不做任何修复。

## 核心能力

该工具强制执行严格的"只分析"原则，防止过早修复可能掩盖深层问题。它在读取任何代码之前先生成多个假设，然后使用 Task 子代理并行验证。所有结论都需要代码证据（文件路径和行号）支撑。

核心原则：
- **假设先行**：读代码前先生成 3-5 个假设
- **并行探索**：同时验证多个理论
- **证据为王**：每个结论都需要代码证明
- **禁止修复**：纯分析，只输出根因报告

## 适用场景

True Detective Universal 擅长：
- 调试间歇性/不稳定的 Bug
- 排查竞态条件和异步问题
- 分析状态管理问题
- 在不熟悉的代码库中寻找根因

不适用于：简单的拼写错误修复、已知问题的明显解决方案、或需要立即修复的场景。

## 问题分类

| 分类 | 典型关键词 |
|------|------------|
| P1: 异步/并发 | "有时候"、"竞态"、"偶发" |
| P2: 状态管理 | "重启后"、"不一致"、"缓存" |
| P3: UI/渲染 | "不显示"、"闪烁"、"不刷新" |
| P4: 配置/数据 | "配置"、"参数"、"找不到" |
| P5: 资源/依赖 | "加载失败"、"空引用"、"缺失" |
| P6: 生命周期 | "启动时"、"第一次"、"关闭后" |

## 四阶段工作流

```
阶段 1: 解析 (PARSE)
  关键词提取 → 问题分类 → 代码结构探索 → 假设生成

阶段 2: 探索 (EXPLORE) - 并行
  ┌──────────┐  ┌──────────┐  ┌──────────┐
  │ 假设 A   │  │ 假设 B   │  │ 假设 C   │  ← 并行 Task 子代理
  └────┬─────┘  └────┬─────┘  └────┬─────┘
       ↓             ↓             ↓
    证据集 A      证据集 B      证据集 C

阶段 3: 汇聚 (CONVERGE)
  证据合并 → 深度推理 (ultrathink) → 根因锁定

阶段 4: 报告 (REPORT)
  结构化报告 → 证据链 → 时序图 (可选)
```

## 安装

### Claude Code

```bash
# 克隆并复制到你的项目
git clone https://github.com/sputnicyoji/Claude-Skill-TrueDetective.git
cp -r Claude-Skill-TrueDetective/* .claude/skills/true-detective-universal/
```

或者将 `SKILL.md` 和 `references/` 目录复制到 `.claude/skills/true-detective-universal/`。

### Cursor

将 `SKILL.md` 内容复制到 `.cursorrules` 或 `.cursor/rules/true-detective.md`。

## 使用方法

```
/true-detective-universal [问题描述]
/tdu [问题描述]
```

## 输出物

- 代码结构探索结果
- 假设列表及验证状态
- 证据集合（含代码片段）
- 根因分析报告

**不输出**：修复代码、PR、文件修改

## 许可证

MIT

## 作者

**Yoji** - 敬畏耶和华是智慧的开端。—— 箴言 9:10

---

*Claude Code 技能生态系统的一部分*
