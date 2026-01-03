# BRAIN Network AI Rules

> **Auto-synced** 3x daily (9 AM, 2 PM, 6 PM)
> **Last update:** 2025-12-28 - Context Engineering added

## Files

- evergreen-vibe-rules.md - Universal + LSP-first + Context Engineering
- ios-vibe.md - iOS/Swift + LSP + Sosumi
- lsp-mastery.md - LSP quick reference
- context-mastery.md - Context engineering guide (NEW)
- README.md - This file

## Sync Flow

~/dotfiles-hub/claude/rules/*.md → rsync via Tailscale → All devices → symlinks to ~/.claude/rules/

## What's New (2025-12-28)

**Context Engineering** - From Sankalp's Claude Code 2.0 article:
- Attention budget concept (60% threshold)
- Three-phase workflow (Explore → Execute → Review)
- Agent file-reading rule (summaries are lossy)
- First-draft iteration pattern
- Design intentionality (anti-slop)

**New Skills**: session-handoff, first-draft-iteration, context-engineering, cross-model-review, design-intentionality

**New Commands**: /handoff, /checkpoint

## Operations

Force sync: ~/.claude/scripts/sync-to-brain-network.sh
Logs: tail -f ~/.claude/logs/brain-sync.log

## Devices

mba (Primary), tower (Unraid), office-pc (Desktop), deck (Steam Deck)

---
**Philosophy:** One BRAIN, distributed knowledge. Context is attention—spend wisely.
