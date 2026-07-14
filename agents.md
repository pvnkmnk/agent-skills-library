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
- `git-safe-ops` — safe git operation rules
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

### Media Acquisition Session (Soulseek / slskd)
```
Invoke soulseek-network-orienter
Invoke slskd-media-acquisition
Invoke slsk-mcp-client
Invoke music-library-organizer
Invoke subsonic-media-server
Invoke obsidian-music-journal
```

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
| Proxmox MCP | `mcp/proxmox-mcp.json` | `homelab-topology-mapper`, `homelab-sre-agent` |
| Slsk MCP | `mcp/slsk-mcp.json` | `slsk-mcp-client`, `soulseek-network-orienter` |
| slskd-mcp | `mcp/slskd-mcp.json` | `slskd-media-acquisition` |
| Subsonic MCP | `mcp/subsonic-mcp.json` | `subsonic-media-server`, `subsonic-api-client` |

---

## Skill Path Reference

All canonical skills follow the pattern `skills/<skill-id>/SKILL.md`. Examples:

```
skills/homelab-safe-ops/SKILL.md
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
