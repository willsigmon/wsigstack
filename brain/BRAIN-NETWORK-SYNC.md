# BRAIN Network Synchronization - Setup Complete ✅

## Overview

Auto-discovered AI coding tips now sync across ALL your BRAIN network devices via Tailscale.

## BRAIN Network Devices

Your Tailscale mesh network:
- **mba** (MacBook Air) - Primary discovery device
- **tower** - Unraid server
- **office-pc** - Desktop workstation
- **deck** - Steam Deck (when online)

## How It Works

### Discovery Flow
1. **mba** runs AI Tips Monitor 3x daily
2. Monitors Reddit, YouTube, X, blogs
3. Claude Opus 4.5 extracts valuable tips
4. Updates `~/dotfiles-hub/claude/rules/*.md` on mba
5. **Triggers BRAIN network sync**

### Sync Flow
1. After tips are discovered, sync script runs
2. Uses Tailscale mesh to reach all devices
3. `rsync` pushes updated rules to each online device
4. Remote script recreates symlinks on each device
5. Pushover notification confirms sync

### Schedule

**Discovery:** 3x during waking hours
- 🌅 9:00 AM
- 🌞 2:00 PM
- 🌆 6:00 PM

**Sync:** 15 minutes after each discovery
- 9:15 AM
- 2:15 PM
- 6:15 PM

## Synced Content

What gets pushed to all devices:
- `~/dotfiles-hub/claude/rules/evergreen-vibe-rules.md`
- `~/dotfiles-hub/claude/rules/ios-vibe.md`
- `~/dotfiles-hub/claude/rules/README.md`
- Any auto-discovered tips sections

## Per-Device Setup

On each device, rules are symlinked to:
```
~/.claude/rules/*.md → Claude Code
~/.cursor/rules/*.md → Cursor IDE
~/.codex/rules/*.md → Codex CLI
```

This means **all AI tools on all devices** see the same latest rules!

## SSH/Tailscale Requirements

**On mba (primary):**
- ✅ Tailscale installed and authenticated
- ✅ SSH keys for passwordless auth to other devices
- ✅ Sync script: `~/.claude/scripts/sync-to-brain-network.sh`

**On other devices (tower, office-pc, deck):**
- ✅ Tailscale installed and authenticated
- ✅ SSH server running
- ✅ User 'wsig' exists
- ✅ Directory structure: `~/dotfiles-hub/claude/rules/`
- ✅ Directories exist: `~/.claude/rules/`, `~/.cursor/rules/`, `~/.codex/rules/`

## Offline Handling

If a device is offline:
- Sync script pings via Tailscale first
- Skips offline devices with warning in logs
- Syncs to that device on next run when online
- No errors, graceful degradation

## Manual Sync

Force sync to all devices:
```bash
~/.claude/scripts/sync-to-brain-network.sh
```

Sync to specific device:
```bash
rsync -avz ~/dotfiles-hub/claude/rules/ wsig@tower:~/dotfiles-hub/claude/rules/
ssh wsig@tower "cd ~/dotfiles-hub/claude/rules && for f in *.md; do ln -sf \$(pwd)/\$f ~/.claude/rules/\$f; done"
```

## Logs

**Discovery log:**
- `~/.claude/logs/tips-monitor.log`

**Sync log:**
- `~/.claude/logs/brain-sync.log`

**Check sync status:**
```bash
tail -f ~/.claude/logs/brain-sync.log
```

## Notifications

You'll get Pushover alerts for:
- 🚀 New tips discovered (from monitor)
- 🧠 BRAIN network sync complete (after sync)
- ❌ Sync errors (if devices unreachable)

## Network Topology

```
                    ┌─────────────┐
                    │  Tailscale  │
                    │    Mesh     │
                    └──────┬──────┘
                           │
            ┌──────────────┼──────────────┐
            │              │              │
       ┌────▼────┐    ┌────▼────┐   ┌────▼────┐
       │   mba   │    │  tower  │   │office-pc│
       │(primary)│    │ (Unraid)│   │  (PC)   │
       └────┬────┘    └─────────┘   └─────────┘
            │
       ┌────▼────┐
       │  deck   │
       │(SteamOS)│
       └─────────┘

mba: Discovers tips → Syncs to all
All: Receive updates → Recreate symlinks
```

## Verification

**Check if Tailscale is connected:**
```bash
tailscale status
```

**Test ping to a device:**
```bash
tailscale ping tower
```

**Check if rules are in sync:**
```bash
# On mba
md5 ~/dotfiles-hub/claude/rules/evergreen-vibe-rules.md

# On tower (via SSH)
ssh wsig@tower "md5sum ~/dotfiles-hub/claude/rules/evergreen-vibe-rules.md"
```

They should match!

## What This Means

🎯 **Unified BRAIN:**
- All your devices share the same AI coding knowledge
- Tips discovered on mba instantly available everywhere
- Work on any device, same vibe coding rules apply
- One source of truth across your entire network

🔄 **Always Current:**
- No manual syncing needed
- No git commits required
- Automatic 3x daily updates
- 15-minute propagation delay

🧠 **True BRAIN Network:**
- Your dotfiles ARE your distributed knowledge base
- Tailscale mesh = neural pathways
- Auto-discovery = continuous learning
- All nodes stay synchronized

---

Last updated: 2025-12-24
