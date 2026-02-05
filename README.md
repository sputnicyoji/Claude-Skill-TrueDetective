# True Detective Universal

[中文](README_zh-CN.md) | [日本語](README_ja.md) | English

> **"Don't guess, trace. Don't fix, understand."**

**True Detective Universal** is an AI coding assistant skill for systematic root cause analysis. It uses hypothesis-driven investigation with parallel exploration to find the true source of bugs - without making any fixes.

## Key Capabilities

The tool enforces a strict "analysis only" discipline, preventing premature fixes that might mask deeper issues. It generates multiple hypotheses before reading any code, then validates them in parallel using Task subagents. All conclusions require code evidence with file paths and line numbers.

Core principles:
- **Hypothesis-First**: Generate 3-5 hypotheses before diving into code
- **Parallel Exploration**: Validate multiple theories concurrently
- **Evidence-Based**: Every conclusion needs code proof
- **No Fixing**: Pure analysis, outputs root cause report only

## When to Use

True Detective Universal excels at:
- Debugging intermittent/flaky bugs
- Investigating race conditions and async issues
- Analyzing state management problems
- Finding root causes in unfamiliar codebases

Not suited for: Simple typo fixes, known issues with obvious solutions, or when you need immediate fixes.

## Problem Categories

| Category | Typical Keywords |
|----------|------------------|
| P1: Async/Concurrency | "sometimes", "race condition", "intermittent" |
| P2: State Management | "after restart", "inconsistent", "cache" |
| P3: UI/Rendering | "not showing", "flicker", "stale" |
| P4: Config/Data | "config", "parameter", "not found" |
| P5: Resource/Dependency | "load failed", "null", "missing" |
| P6: Lifecycle | "on startup", "first time", "after close" |

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

## Installation

### Claude Code

```bash
# Clone and copy to your project
git clone https://github.com/sputnicyoji/Claude-Skill-TrueDetective.git
cp -r Claude-Skill-TrueDetective/* .claude/skills/true-detective-universal/
```

Or copy `SKILL.md` and `references/` directory to `.claude/skills/true-detective-universal/`.

### Cursor

Copy `SKILL.md` content to `.cursorrules` or `.cursor/rules/true-detective.md`.

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

## License

MIT

## Author

**Yoji** - The fear of the Lord is the beginning of wisdom. — Proverbs 9:10

---

*Part of the Claude Code skill ecosystem*
