# Evergreen Vibe Rules - BRAIN Network

> **Last Updated:** 2025-12-28 | **Synced:** All BRAIN devices

## LSP-First Development (Dec 2025)

**Claude Code shipped native LSP Dec 20, 2025. USE IT.**

Before Refactoring: LSP findReferences → Map ALL usages → Get approval → Make changes → LSP verify

Core LSP Operations: goToDefinition, findReferences, hover, workspaceSymbol, incomingCalls, outgoingCalls

Never Guess: ❌ "~5 places" ✅ "47 refs in 12 files (LSP)"

## Tool Hierarchy

0. LSP for navigation/refactoring
1. Plugins (30+)
2. MCP tools
3. Skills (89+)
4. Agents (parallel)
5. Manual code

## 🧠 Context Engineering (Dec 2025)

**Attention Budget**: Performance degrades with LENGTH, not difficulty.

| Context % | Status | Action |
|-----------|--------|--------|
| 0-40% | 🟢 Optimal | Full capability |
| 40-60% | 🟡 Caution | Plan handoff |
| 60%+ | 🔴 Degraded | `/compact` or fresh |

**Rules:**
- Front-load critical info in prompts
- Use `head_limit` on Grep
- Spawn agents for research (isolated context)
- Checkpoint before pivots (`/rewind`)

**Commands:** `/context`, `/compact`, `/clear`, `/rewind`, `Esc+Esc`

## 📋 Three-Phase Workflow

**Explore → Execute → Review**

1. **Explore**: Ask questions, read files, map dependencies
2. **Execute**: `/ultrathink` for hard decisions, checkpoint before pivots
3. **Review**: Cross-validate, check requirements, document

## 🔍 Agent File-Reading Rule

> "Summaries are lossy. Read critical files yourself after agents locate them."

- Agent summaries guide WHERE to look
- Direct reads enable attention to extract pair-wise relationships
- 2-3 most critical files → read in main context

## 🔄 Iteration Patterns

**First-Draft Iteration** (for fuzzy requirements):
1. Throwaway branch → let model write freely
2. Observe divergences from mental model
3. Fresh branch with sharpened prompts
4. Synthesize best of both

## 🎨 Design Intentionality

**Anti-slop rules:**
- Exact fonts, not "modern"
- Hex codes, not "nice colors"
- Reference apps/sites
- "Bold maximalism or refined minimalism—never generic middle"

**Test:** Can someone describe the aesthetic in one sentence?

## Code Quality

- Simplicity > cleverness
- Delete unused (LSP confirms safety)
- No premature abstraction

## Architecture

- LSP maps real dependencies
- Red flags: God objects, circular deps
- Use LSP, don't guess

---

## New Skills (2025-12-28)
- `session-handoff` - Document state for context reset
- `first-draft-iteration` - Throw-away draft workflow
- `context-engineering` - Attention budget management
- `cross-model-review` - Multi-model QA patterns
- `design-intentionality` - Anti-slop design rules

## New Commands
- `/handoff` - Auto-document session state
- `/checkpoint` - Mark decision points for rewind

---
**Rule:** LSP before refactoring. Context at 60% = handoff time. Read files yourself.
