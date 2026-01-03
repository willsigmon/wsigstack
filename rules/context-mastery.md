# Context Mastery - Quick Reference

> **Added:** 2025-12-28 | **Source:** Sankalp's Claude Code 2.0 article

## The Core Insight

Model performance degrades with **LENGTH**, not difficulty. Treat context as a limited attention budget.

## Thresholds

| % | Status | Action |
|---|--------|--------|
| 0-40 | 🟢 | Full power |
| 40-60 | 🟡 | Plan handoff |
| 60-80 | 🟠 | Wrap up → `/compact` |
| 80+ | 🔴 | `/compact` NOW |

## Essential Commands

```
/context     - Check usage
/compact     - Compress history
/clear       - Full reset
/rewind      - Checkpoint restore
Esc+Esc      - Quick rewind
Ctrl+R       - Search prompt history
/ultrathink  - Force deep reasoning
```

## Token Economy

- Tool results persist (LLMs are stateless)
- One task = 6K+ tokens easily
- MCP tool definitions load upfront
- Agent contexts are isolated (fresh)

## Optimization Tactics

**Front-load critical info** - Important stuff FIRST

**Minimize bloat:**
- `head_limit` on Grep
- `offset/limit` on large file reads
- Background agents for research

**Agent summaries are lossy:**
- Use them to find WHERE to look
- Read critical files yourself (2-3 max)
- Direct reads enable attention mechanisms

**Checkpoint strategy:**
- `/rewind` before risky pivots
- Think of it as git commits for conversation
- Cheap to create, valuable when needed

## When to Spawn Agents

| Agent | Use For |
|-------|---------|
| Explore | File search, codebase navigation |
| Plan | Architecture, strategy |
| General | Multi-step research |
| claude-code-guide | CC feature questions |

Fresh context = advantage for complex searches.

## Handoff Protocol

At 60% context, create handoff:
1. Current task + status
2. Key decisions made
3. Files modified
4. Next steps
5. Resume instructions

Save to: `~/.claude/handoffs/[project]-[date].md`

---
**Mantra:** Context is attention. Spend it wisely.
