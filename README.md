<div align="center">

# wsigstack

**My personal Claude Code stack for shipping software with AI**

[![Skills](https://img.shields.io/badge/skills-84-blue?style=for-the-badge)](./skills)
[![Commands](https://img.shields.io/badge/commands-24-green?style=for-the-badge)](./commands)
[![License](https://img.shields.io/badge/license-MIT-orange?style=for-the-badge)](./LICENSE)

*84 skills • 24 commands • BRAIN network config • Ready to clone*

---

</div>

## The Story

I've been using AI every single day since **November 30, 2022**—the day ChatGPT launched.

In **March 2025**, I discovered vibe coding, and everything changed. I had an idea I felt convicted to build, and that sent me down a rabbit hole of figuring out how to actually ship software with AI as my copilot.

After **~5,000 hours** across Codex, Claude, Lovable, Replit, Cursor, and more, this repo is the distillation of everything that actually stuck.

Now I want to share it with friends and anyone else who's curious about this way of building.

---

## What's Inside

```
wsigstack/
├── 🧠 skills/      84 specialized skills for Claude Code
├── ⚡ commands/    24 slash commands (/test, /deploy, /build, etc.)
├── 📏 rules/       LSP mastery, context engineering, iOS patterns
├── 🔮 brain/       CLAUDE.md + BRAIN network multi-device sync
└── 📚 examples/    Setup examples and templates
```

---

## ⚡ Quick Install

```bash
# Clone the repo
git clone https://github.com/willsigmon/wsigstack.git
cd wsigstack

# Copy skills to Claude Code
cp -r skills/* ~/.claude/skills/

# Copy commands
cp -r commands/* ~/.claude/commands/

# Copy rules (auto-loaded by Claude Code)
mkdir -p ~/.claude/rules
cp -r rules/* ~/.claude/rules/

# Optional: Use my CLAUDE.md as a starting point
cp brain/CLAUDE.md ~/.claude/CLAUDE.md
```

---

## 🛠 The Stack

### 🧠 The Brain

| Tool | What It Does | |
|:-----|:-------------|:-:|
| **Claude Code + Opus 4.5** | The brain. CLI-first AI coding. This is where the magic happens. | [↗](https://claude.ai/code) |
| **Omi** | AI wearable + MCP server. Captures context, syncs memories across sessions. | [↗](https://www.omi.me/?ref=WILLSIGMON) |

### 🎤 Voice Input

> *Pick your favorite—I use both and love them equally.*

| Tool | What It Does | |
|:-----|:-------------|:-:|
| **Typeless** | Dictation that actually works. I talk, it types. | [↗](https://www.typeless.com/?via=wsig) |
| **Wispr Flow** | Voice-to-code. Speak your intentions, get code. | [↗](https://wisprflow.ai/r?WILL48) |

### 💻 Terminal

| Tool | What It Does | |
|:-----|:-------------|:-:|
| **Ghostty** | Fast, minimal, GPU-accelerated. Replaced Terminal.app for me entirely. | [↗](https://ghostty.org) |

### 🖥 IDE *(Optional—I rarely need one)*

> *Claude Code in terminal handles 95% of my work. IDEs are for when I need to see things visually.*

| Tool | What It Does | |
|:-----|:-------------|:-:|
| **Cursor Max** | AI-native IDE. $200/mo for unlimited. Great for visual work. | [↗](https://cursor.com) |
| **VS Code Insiders** | Free. Claude extension available. Solid fallback. | [↗](https://code.visualstudio.com/insiders/) |

### ☁️ Infrastructure

| Tool | What It Does | |
|:-----|:-------------|:-:|
| **GitHub** | Code lives here. PRs, issues, Actions. | [↗](https://github.com) |
| **Vercel** | Deploy frontend, serverless functions. Pro plan. | [↗](https://vercel.com) |
| **Supabase** | Postgres + Auth + Realtime + Storage. Pro plan. | [↗](https://supabase.com) |

### 🔌 MCP Servers

| Server | Purpose |
|:-------|:--------|
| **Omi** | Memory persistence across sessions |
| **Sosumi** | Apple documentation (essential for iOS dev) |
| **GitHub** | PR reviews, issues, repo management |
| **SQLite** | Local database queries |
| **Puppeteer** | Browser automation |

---

## 🔮 The BRAIN Network

My setup syncs Claude context across multiple machines via Tailscale.

<details>
<summary><strong>📁 Key Files</strong></summary>

| File | Purpose |
|:-----|:--------|
| `CLAUDE.md` | Master instructions that load on every session |
| `BRAIN-NETWORK-SYNC.md` | How the multi-device sync works |
| `yolo-yolox-config.md` | My "nanobot healing swarm" autonomous mode |

</details>

---

## 🧠 Adding Your Own Skills

Skills are just markdown files:

```markdown
# Skill Name

## Purpose
What this skill does

## When to Use
- Scenario 1
- Scenario 2

## Instructions
Step by step what Claude should do
```

Save to `~/.claude/skills/` — available immediately, no restart needed.

---

## 🔗 Integrating Omi

Omi is the secret weapon—it captures conversations and creates memories that persist across Claude sessions.

<details>
<summary><strong>📦 Setup Instructions</strong></summary>

```bash
# Clone the Omi MCP server
git clone https://github.com/BasedHardware/omi
cd omi/plugins/mcp
pnpm install && pnpm build
```

Add to your Claude Code MCP config:

```json
{
  "mcpServers": {
    "omi": {
      "command": "node",
      "args": ["/path/to/omi/plugins/mcp/dist/index.js"],
      "env": {
        "OMI_API_KEY": "your-api-key"
      }
    }
  }
}
```

</details>

<details>
<summary><strong>🛠 Available Tools</strong></summary>

| Tool | What It Does |
|:-----|:-------------|
| `mcp__omi__get_memories` | Retrieve facts Claude knows about you |
| `mcp__omi__create_memory` | Save important context for later |
| `mcp__omi__get_conversations` | Access past conversation transcripts |
| `mcp__omi__get_conversation_by_id` | Deep dive into specific conversations |

</details>

I start every session checking memories. Claude picks up exactly where we left off.

---

## 🔌 Adding More MCP Servers

<details>
<summary><strong>How to add MCP servers</strong></summary>

### 1. Find or Build a Server

Check the [MCP Server Registry](https://github.com/modelcontextprotocol/servers) or build your own.

### 2. Add to Config

```json
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

New tools appear automatically.

</details>

---

## 🤖 Philosophy: Nanobot Healing Swarm

My `CLAUDE.md` instructs Claude to act as a "healing swarm of nanobots"—find every bug, scrub every infection, optimize every inefficiency.

| Principle | What It Means |
|:----------|:--------------|
| **Tools first** | Check if MCP/skill can handle it before writing code |
| **Parallel agents** | Spawn 20+ agents for complex tasks |
| **Context is attention** | Manage the 60% threshold, use `/compact` |
| **Memory graph** | Use Omi to maintain continuity across sessions |

---

## 💖 Support the Stack

If this setup helps you ship faster, consider using my affiliate links:

<div align="center">

| | Tool | Link |
|:-:|:-----|:-----|
| 🧠 | **Omi** | [omi.me/?ref=WILLSIGMON](https://www.omi.me/?ref=WILLSIGMON) |
| 🎤 | **Typeless** | [typeless.com/?via=wsig](https://www.typeless.com/?via=wsig) |
| 🗣 | **Wispr Flow** | [wisprflow.ai/r?WILL48](https://wisprflow.ai/r?WILL48) |

</div>

---

## 📬 Questions?

Reach out: **[wjsigmon@me.com](mailto:wjsigmon@me.com)**

---

<div align="center">

**MIT License** — Use it, modify it, make it yours.

---

*Built with Claude Code Opus 4.5 and ~5,000 hours of figuring out what actually works.*

</div>
