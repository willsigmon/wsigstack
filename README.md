# wsigstack

> My complete Claude Code stack: 84 skills, 24 commands, BRAIN network config, and the tools I use daily.

This is my actual working setup for Claude Code. No fluff, just what I use every day to build iOS apps, manage servers, and ship code faster than I ever thought possible.

## What's Inside

```
wsigstack/
├── skills/      # 84 specialized skills for Claude Code
├── commands/    # 24 slash commands (/test, /deploy, /build, etc.)
├── rules/       # LSP mastery, context engineering, iOS patterns
├── brain/       # CLAUDE.md + BRAIN network multi-device sync
└── examples/    # Setup examples and templates
```

## Quick Install

```bash
# Clone
git clone https://github.com/willsigmon/wsigstack.git

# Copy skills to Claude Code
cp -r wsigstack/skills/* ~/.claude/skills/

# Copy commands
cp -r wsigstack/commands/* ~/.claude/commands/

# Copy rules (auto-loaded by Claude Code)
mkdir -p ~/.claude/rules
cp -r wsigstack/rules/* ~/.claude/rules/

# Optional: Use my CLAUDE.md as a starting point
cp wsigstack/brain/CLAUDE.md ~/.claude/CLAUDE.md
```

## My Stack

### The Core (What I Actually Use)

| Tool | What It Does | Link |
|------|--------------|------|
| **Claude Code + Opus 4.5** | The brain. CLI-first, no IDE needed. | [claude.ai/code](https://claude.ai/code) |
| **Omi** | AI wearable + memory MCP. Captures conversations, syncs context across sessions. | [omi.me](https://www.omi.me/?ref=WILLSIGMON) |
| **Typeless** | Dictation that actually works. I talk, it types. | [typeless.com](https://www.typeless.com/?via=wsig) |
| **Wispr Flow** | Voice-to-code. Speak your intentions, get code. | [wisprflow.ai](https://wisprflow.ai/r?WILL48) |
| **Ghostty** | Fast terminal. That's it. | [ghostty.org](https://ghostty.org) |

### Infrastructure

| Tool | What For |
|------|----------|
| **GitHub** | Code lives here |
| **Vercel** | Deploy frontend, serverless functions |
| **Supabase** | Postgres + auth + realtime |

### Occasional Use

- **Cursor** / **VS Code Insiders** - Only when I need the Claude extension for visual stuff
- But honestly? Claude Code in terminal handles 95% of my work

## The BRAIN Network

My setup syncs Claude context across multiple machines (MacBook, tower server, desktop, Steam Deck) via Tailscale. The `brain/` folder has the configs.

**Key files:**
- `CLAUDE.md` - Master instructions that load on every session
- `BRAIN-NETWORK-SYNC.md` - How the multi-device sync works
- `yolo-yolox-config.md` - My "nanobot healing swarm" autonomous mode

## Adding More Skills

Skills are just markdown files. Create one:

```markdown
# my-skill.md

# Skill Name

## Purpose
What this skill does

## When to Use
- Scenario 1
- Scenario 2

## Instructions
Step by step what Claude should do
```

Save to `~/.claude/skills/` and it's available immediately.

## Integrating Omi with Your Stack

Omi is the secret weapon. It captures your conversations and creates memories that persist across Claude sessions.

### Setup Omi MCP

```bash
# Install the Omi MCP server
git clone https://github.com/BasedHardware/omi-mcp
cd omi-mcp
pnpm install && pnpm build

# Add to Claude Code MCP config (~/.claude/mcp.json or settings)
{
  "mcpServers": {
    "omi": {
      "command": "node",
      "args": ["/path/to/omi-mcp/dist/index.js"],
      "env": {
        "OMI_API_KEY": "your-api-key"
      }
    }
  }
}
```

### What Omi Gives You

- `mcp__omi__get_memories` - Retrieve facts Claude knows about you
- `mcp__omi__create_memory` - Save important context
- `mcp__omi__get_conversations` - Access past conversation transcripts
- `mcp__omi__get_conversation_by_id` - Deep dive into specific conversations

I start every session checking memories. Claude picks up exactly where we left off.

## Adding More MCP Servers

MCP servers extend Claude's capabilities. Here's how to add them:

### 1. Find or Build an MCP Server

- [MCP Server Registry](https://github.com/modelcontextprotocol/servers)
- Or build your own with the MCP SDK

### 2. Add to Your Config

```json
// ~/.claude/mcp.json
{
  "mcpServers": {
    "your-server": {
      "command": "node",
      "args": ["/path/to/server/index.js"],
      "env": {
        "API_KEY": "xxx"
      }
    }
  }
}
```

### 3. Restart Claude Code

The new tools appear automatically.

### MCP Servers I Use

| Server | Purpose |
|--------|---------|
| **Omi** | Memory persistence across sessions |
| **Sosumi** | Apple documentation (essential for iOS dev) |
| **GitHub** | PR reviews, issues, repo management |
| **Brave Search** | Web search from CLI |
| **SQLite** | Database queries |

## Philosophy: Nanobot Healing Swarm

My CLAUDE.md instructs Claude to act as a "healing swarm of nanobots" - find every bug, scrub every infection, optimize every inefficiency. It's aggressive but it works.

Key principles:
- **Tools first** - Check if MCP/skill can do it before writing code
- **Parallel agents** - Spawn 20+ agents for complex tasks
- **Context is attention** - Manage the 60% threshold, use `/compact`
- **Memory graph** - Use Omi to maintain continuity across sessions

## Support the Stack

If this setup helps you ship faster, consider using my affiliate links:

- **[Omi](https://www.omi.me/?ref=WILLSIGMON)** - The AI wearable that changed how I work
- **[Typeless](https://www.typeless.com/?via=wsig)** - Dictation that just works
- **[Wispr Flow](https://wisprflow.ai/r?WILL48)** - Voice-to-code magic

Questions? [wjsigmon@me.com](mailto:wjsigmon@me.com)

## License

MIT - Use it, modify it, make it yours.

---

*Built with Claude Code Opus 4.5 and way too much coffee.*
