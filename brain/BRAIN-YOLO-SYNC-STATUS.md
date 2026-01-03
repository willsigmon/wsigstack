# YOLO/YOLOX BRAIN Network Sync Status

> **Last Sync:** 2025-12-30 03:04 UTC | **Status:** ACTIVE

## Device Status

### MBA (Primary) ✅ COMPLETE
- `/usr/local/bin/yolo` - Claude Opus 4.5 + 32K ultrathink
- `/usr/local/bin/yolox` - GPT-5 Codex + xhigh reasoning
- `~/.claude/BRAIN_BACKUP_DEC2025.md` - Context file
- `~/dotfiles-hub/claude/yolo-yolox-config.md` - Master config
- Omi memory persisted (2 entries)

### Tower (100.119.19.61) ✅ SYNCED
- `/usr/local/bin/yolo` ✓
- `/usr/local/bin/yolox` ✓
- `~/dotfiles-hub/claude/yolo-yolox-config.md` ✓
- `~/.claude/BRAIN_BACKUP_DEC2025.md` ✓

### Office-PC / vt-pc (100.124.63.99) ⚠️ PARTIAL
- Windows machine - different path structure
- Codex CLI available
- Manual config needed: copy scripts to PATH-accessible location
- Or use native codex with xhigh reasoning

### Deck (100.68.94.31) 🔄 PENDING
- Currently offline (last seen 1d ago)
- Will sync automatically when online via cron job

## Sync Commands

```bash
# Manual sync to tower
scp -P 2222 /usr/local/bin/yolo /usr/local/bin/yolox root@tower:/usr/local/bin/

# Full dotfiles sync
~/.claude/scripts/sync-to-brain-network.sh

# Check Tailscale status
tailscale status
```

## Verification

```bash
# On any device
yolo --version  # Should launch Claude Opus 4.5
yolox --help    # Should show GPT-5 Codex options
```

---
*Auto-updated by nanobot healing swarm*
