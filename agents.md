# Agent Skills Index

This file is the runtime skill index for OpenCode, Freebuff, Antigravity CLI, and Codex agents operating in the pvnkmnk ecosystem.

## How to Use Skills

- **OpenCode / Codex:** `Invoke <skill-id>` at the start of any session where the skill is relevant.
- **Freebuff:** `/skill <skill-id>`
- **Antigravity CLI:** Load via your skill manager (aix/OpenPackage) pointing at this repo.

All canonical skills live in `skills/<skill-id>/SKILL.md`. The full reference is in `REFERENCE.md`.

---

## Always-On Skills (load by default)

These skills are active in every session:

- `homelab-safe-ops` — safety constraints for all homelab operations
- `git-safe-ops` — safe git operation rules (no force-push to main, always branch)
- `memory-layer-bridge` — when to use Cipher/Mem0 vs Obsidian vs inline context

---

## Skill Groups by Session Type

### Coding / Development Session
```
Invoke grill-me
Invoke tdd-loop
Invoke refactor-with-tests
Invoke security-audit
Invoke authz-and-audit-log
Invoke git-safe-ops
```

### Homelab / Infrastructure Session
```
Invoke homelab-safe-ops
Invoke homelab-topology-mapper
Invoke homelab-change-planner
Invoke homelab-research-librarian
Invoke homelab-logbook
Invoke obsidian-homelab-logbook
```

### Homelab Security / Network Audit Session
```
Invoke homelab-safe-ops
Invoke homelab-network-auditor
Invoke homelab-change-planner
Invoke homelab-logbook
```

### Proxmox / VM Provisioning Session
```
Invoke homelab-safe-ops
Invoke homelab-topology-mapper
Invoke homelab-change-planner
Invoke docker-app-deployer
Invoke homelab-logbook
Invoke obsidian-homelab-logbook
```
> Requires: `mcp/proxmox-mcp.json` configured and Proxmox MCP server running.

### WSL / Dotfiles Session
```
Invoke git-safe-ops
Invoke homelab-safe-ops
Invoke memory-layer-bridge
```
> Use for dotfiles repo management, WSL distro config, shell environment changes (Zsh/Bash/PowerShell).
> git-safe-ops enforces branch discipline; homelab-safe-ops prevents destructive system file edits.

### Local LLM Inference Session (RTX 3060 / Ollama / LM Studio)
```
Invoke homelab-safe-ops
Invoke homelab-monitoring-analyst
Invoke homelab-logbook
```
> Use when loading, benchmarking, or switching local LLM models on the RTX 3060 inference node.
> homelab-monitoring-analyst: watch VRAM usage and thermal headroom before loading large quants.
> homelab-logbook: record which model, quantization level, and context size was used in each session.

### Media Acquisition Session (Soulseek / slskd)
```
Invoke soulseek-network-orienter
Invoke slskd-media-acquisition
Invoke slsk-mcp-client
Invoke music-library-organizer
Invoke subsonic-media-server
Invoke obsidian-music-journal
```

### Beets Library Run Session
```
Invoke music-library-organizer
Invoke homelab-logbook
```
> Use when running a beets import pass on downloaded files.
> music-library-organizer: drives the beet import, tag, deduplicate, and move pipeline.
> homelab-logbook: records the import summary (files processed, ambiguous matches, errors).
> After beets completes, invoke `subsonic-media-server` to trigger a Navidrome library rescan.

### netrunner Development Session
```
Invoke netrunner-media-orchestrator
Invoke subsonic-api-client
Invoke slskd-media-acquisition
Invoke tdd-loop
Invoke security-audit
Invoke architecture-improvement
```

### DJ / Mix Planning Session
```
Invoke dj-library-curator
Invoke dj-set-architect
Invoke dj-mix-documentarian
Invoke obsidian-music-journal
Invoke music-listening-journal
```

### Music Production / Project Session
```
Invoke music-project-planner
Invoke music-listening-journal
Invoke dj-mix-documentarian
Invoke obsidian-music-journal
Invoke lyrics-and-theory-bridge
```

### Knowledge Base (KB) Maintenance Session
```
Invoke obsidian-vault-architect
Invoke obsidian-vault-manager
Invoke memory-layer-bridge
Invoke homelab-logbook
```
> Use for vault restructuring, MOC updates, tag taxonomy changes, and note migrations.
> obsidian-vault-architect: enforces structure before making bulk changes.
> memory-layer-bridge: routes what should be in Mem0 vs. Obsidian.
> homelab-logbook: records significant vault structure changes as infrastructure events.

### Obsidian Vault Session
```
Invoke obsidian-vault-architect
Invoke obsidian-vault-manager
Invoke obsidian-markdown
Invoke obsidian-bases
Invoke defuddle
Invoke memory-layer-bridge
```

### Planning / PRD Session
```
Invoke grill-me
Invoke prompt-auditor
Invoke write-prd-from-conversation
Invoke prd-to-kanban-issues
Invoke orchestrator
```

### Social / Community Work Session
```
Invoke social-impact-lens
Invoke case-note-structurer
Invoke obsidian-vault-architect
```

---

## MCP Servers (action layer)

Ensure these MCP servers are configured and running before invoking related skills:

| MCP | Config | Required For |
|---|---|---|
| Proxmox MCP | `mcp/proxmox-mcp.json` | `homelab-topology-mapper`, `homelab-sre-agent`, Proxmox/VM Session |
| Slsk MCP | `mcp/slsk-mcp.json` | `slsk-mcp-client`, `soulseek-network-orienter` |
| slskd-mcp | `mcp/slskd-mcp.json` | `slskd-media-acquisition` |
| Subsonic MCP | `mcp/subsonic-mcp.json` | `subsonic-media-server`, `subsonic-api-client` |
| Obsidian MCP | `mcp/obsidian-mcp.json` | `obsidian-vault-manager`, `obsidian-music-journal`, `obsidian-homelab-logbook`, KB Maintenance Session |

---

## Skill Path Reference

All canonical skills follow the pattern `skills/<skill-id>/SKILL.md`. Examples:

```
skills/homelab-safe-ops/SKILL.md
skills/git-safe-ops/SKILL.md
skills/memory-layer-bridge/SKILL.md
skills/lyrics-and-theory-bridge/SKILL.md
skills/soulseek-network-orienter/SKILL.md
skills/obsidian-vault-architect/SKILL.md
skills/netrunner-media-orchestrator/SKILL.md
skills/dj-set-architect/SKILL.md
```

Domain meta-aggregator indexes (discovery only, not skill specs):

```
skills/homelab/README.md
skills/media/README.md
skills/obsidian/README.md
```

See `REFERENCE.md` for the complete skill table with descriptions and paths.
