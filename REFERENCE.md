# Agent Skills Reference

> Companion reference for all skills in the pvnkmnk agent-skills-library.
> Use this as the single index for OpenCode, Freebuff, Antigravity CLI, and Codex.
> **Invoke a skill:** `Invoke <skill-id>` (OpenCode/Codex) | `/skill <skill-id>` (Freebuff)

Last updated: July 14, 2026

---

## Meta / Reasoning Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `grill-me` | Meta | Interrogates a plan or idea with pointed questions to expose gaps before execution | `skills/meta/grill-me.SKILL.md` |
| `prompt-auditor` | Meta | Reviews and rewrites prompts for clarity, specificity, and safety | `skills/meta/prompt-auditor.SKILL.md` |
| `write-prd-from-conversation` | Meta | Turns a freeform conversation into a structured PRD | `skills/meta/write-prd-from-conversation.SKILL.md` |
| `prd-to-kanban-issues` | Meta | Decomposes a PRD into Kanban-ready issues with acceptance criteria | `skills/meta/prd-to-kanban-issues.SKILL.md` |
| `orchestrator` | Meta | Plans and delegates multi-step tasks across agents and tools | `skills/meta/orchestrator.SKILL.md` |
| `eval-loop` | Meta | Runs evaluation loops on agent outputs against defined criteria | `skills/meta/eval-loop.SKILL.md` |

---

## Coding Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `tdd-loop` | Coding | Drives a red-green-refactor TDD loop for any feature or fix | `skills/coding/tdd-loop.SKILL.md` |
| `refactor-with-tests` | Coding | Safely refactors existing code with test coverage as the safety net | `skills/coding/refactor-with-tests.SKILL.md` |
| `architecture-improvement` | Coding | Reviews and proposes improvements to system architecture and module boundaries | `skills/coding/architecture-improvement.SKILL.md` |
| `security-audit` | Coding | Audits code for common vulnerabilities (OWASP Top 10, injection, auth flaws) | `skills/coding/security-audit.SKILL.md` |
| `authz-and-audit-log` | Coding | Implements RBAC authorization and audit logging patterns (FastAPI/PostgreSQL focused) | `skills/coding/authz-and-audit-log.SKILL.md` |

---

## Obsidian Skills

### Official Obsidian Skills (upstream: github.com/kepano/obsidian-skills)

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `obsidian-markdown` | Obsidian | Teaches Obsidian-flavored Markdown: wikilinks, YAML properties, callouts, embeds, tags | `skills/obsidian/obsidian-markdown.SKILL.md` |
| `obsidian-bases` | Obsidian | Teaches agents to work with Bases (Obsidian's structured data tables) | `skills/obsidian/obsidian-bases.SKILL.md` |
| `json-canvas` | Obsidian | Teaches the JSON Canvas format for visual canvases and whiteboards | `skills/obsidian/json-canvas.SKILL.md` |
| `obsidian-cli` | Obsidian | Teaches agents to use the Obsidian CLI for vault-level terminal workflows | `skills/obsidian/obsidian-cli.SKILL.md` |
| `defuddle` | Obsidian | Extracts clean Markdown from web pages for vault import | `skills/obsidian/defuddle.SKILL.md` |

### Bespoke Obsidian Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `obsidian-vault-architect` | Obsidian | Designs and evolves vault structure: folders, tags, Bases, MOCs across all domains | `skills/obsidian/obsidian-vault-architect.SKILL.md` |
| `obsidian-homelab-logbook` | Obsidian | Standardizes homelab change and incident logs as Obsidian notes | `skills/obsidian/obsidian-homelab-logbook.SKILL.md` |
| `obsidian-music-journal` | Obsidian | Standardizes listening, DJ set, and production journal entries in the vault | `skills/obsidian/obsidian-music-journal.SKILL.md` |
| `obsidian-vault-manager` | Obsidian | Create, organize, and maintain Obsidian vault notes, folders, templates, and links via the Local REST API | `skills/obsidian-vault-manager/SKILL.md` |

---

## Homelab Skills

### Core Homelab Behavior Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `homelab-topology-mapper` | Homelab | Builds and maintains a structured map of hosts, VMs, containers, networks, and services | `skills/homelab/homelab-topology-mapper.SKILL.md` |
| `homelab-change-planner` | Homelab | Plans infrastructure changes with explicit risk assessment and rollback steps | `skills/homelab/homelab-change-planner.SKILL.md` |
| `homelab-safe-ops` | Homelab | Encodes read-first, no-destroy-by-default safety constraints for all homelab automation | `skills/homelab/homelab-safe-ops.SKILL.md` |
| `homelab-monitoring-analyst` | Homelab | Interprets metrics and logs, summarizes incidents, suggests investigations | `skills/homelab/homelab-monitoring-analyst.SKILL.md` |
| `homelab-logbook` | Homelab | Systematizes change and incident logging, linked to topology and issues | `skills/homelab/homelab-logbook.SKILL.md` |
| `homelab-research-librarian` | Homelab | Teaches agents where and how to find reliable homelab/self-hosting information | `skills/homelab/homelab-research-librarian.SKILL.md` |

### Community-Backed Homelab Action Layers (MCP/Tool)

| Skill ID | Category | Description | Path / Source |
|---|---|---|---|
| `proxmox-mcp` | Homelab / MCP | Proxmox VM/LXC/container management and monitoring via MCP | `mcp/proxmox-mcp.json` / MCPMarket |
| `media-stack-builder` | Homelab | Scaffolds Docker Compose media stacks: slskd, Subsonic, Jellyfin, reverse proxy, Watchtower | `skills/homelab/media-stack-builder.SKILL.md` |
| `reverse-proxy-and-tunnel` | Homelab | Secure exposure via Traefik/NPM/Caddy + Cloudflare Tunnel/WireGuard/Tailscale | `skills/homelab/reverse-proxy-and-tunnel.SKILL.md` |
| `docker-app-deployer` | Homelab | Safe Docker Compose deployment, env var management, and update patterns | `skills/homelab/docker-app-deployer.SKILL.md` |
| `homelab-sre-agent` | Homelab | SRE-style agent behavior over monitoring tools and MCP endpoints | `skills/homelab/homelab-sre-agent.SKILL.md` |
| `homelab-network-auditor` | Homelab | Scans homelab for open ports, audits firewall rules, and generates network security reports | `skills/homelab-network-auditor/SKILL.md` |

---

## Media / Music Skills

### Soulseek / slskd / Subsonic

| Skill ID | Category | Description | Path / Source |
|---|---|---|---|
| `soulseek-network-orienter` | Media | Teaches Soulseek culture, etiquette, and search strategies; logs discoveries to Obsidian | `skills/media/soulseek-network-orienter.SKILL.md` |
| `slskd-media-acquisition` | Media | Uses slskd web/API in homelab: token auth, HTTPS, reverse proxy, queue management | `skills/media/slskd-media-acquisition.SKILL.md` |
| `slsk-mcp-client` | Media / MCP | Wraps the Slsk MCP server with safety rules, rate limits, and logging | `skills/media/slsk-mcp-client.SKILL.md` / `mcp/slsk-mcp.json` |
| `slskd-mcp` | Media / MCP | Auto-generated MCP server from slskd OpenAPI 3.0.1 spec (70 paths, 93 ops) | `mcp/slskd-mcp.json` / github.com/abl030/slskd-mcp |
| `subsonic-media-server` | Media | Subsonic/OpenSubsonic auth, browsing, rescans, playlist management, library hygiene | `skills/media/subsonic-media-server.SKILL.md` |
| `subsonic-api-client` | Media | Integration guidance using Subsonic/OpenSubsonic client libraries (TS subsonic-api etc.) | `skills/media/subsonic-api-client.SKILL.md` |
| `netrunner-media-orchestrator` | Media | Orchestrates full acquisition-to-playback pipeline for the netrunner project | `skills/media/netrunner-media-orchestrator.SKILL.md` |

### Music Library, Listening & DJ Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `music-library-organizer` | Music | Structures listening collection: folders, canonical filenames, tags, Obsidian alignment | `skills/media/music-library-organizer.SKILL.md` |
| `music-listening-journal` | Music | Captures reflective listening notes as reusable creative input in Obsidian | `skills/media/music-listening-journal.SKILL.md` |
| `dj-library-curator` | DJ | Curates DJ-friendly library with BPM/key/energy tags and crates per context | `skills/media/dj-library-curator.SKILL.md` |
| `dj-set-architect` | DJ | Plans sets as arcs (opening → build → peak → comedown → close) with transition tracking | `skills/media/dj-set-architect.SKILL.md` |
| `dj-mix-documentarian` | DJ | Logs finished mixes: tracklists, transitions, rights, release metadata | `skills/media/dj-mix-documentarian.SKILL.md` |
| `music-project-planner` | Music | Plans music production projects with milestones, references, and session notes | `skills/media/music-project-planner.SKILL.md` |
| `lyrics-and-theory-bridge` | Music | Bridges lyric writing with music theory concepts for composition and arrangement | `skills/media/lyrics-and-theory-bridge.SKILL.md` |

---

## Social Domain Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `social-impact-lens` | Social | Applies sociological and social-work ethics lens to any feature or system design | `skills/social/social-impact-lens.SKILL.md` |
| `case-note-structurer` | Social | Structures case notes in social work / community support contexts | `skills/social/case-note-structurer.SKILL.md` |

---

## MCP / Tool Bridge Skills

| Skill ID | Category | Description | Path |
|---|---|---|---|
| `memory-layer-bridge` | MCP | Teaches agents when to query Cipher/Mem0, when to consult Obsidian, when to log decisions | `skills/mcp/memory-layer-bridge.SKILL.md` |
| `filesystem-refactor-planner` | MCP | Plans filesystem refactors safely using MCP filesystem tools | `skills/mcp/filesystem-refactor-planner.SKILL.md` |
| `git-safe-ops` | MCP | Encodes safe git operations: no force-push to main, always branch, always review | `skills/mcp/git-safe-ops.SKILL.md` |

---

## MCP Config Files

| Config | Purpose | Upstream |
|---|---|---|
| `mcp/proxmox-mcp.json` | Proxmox VM/LXC/monitoring MCP server | MCPMarket: Homelab Proxmox MCP |
| `mcp/slsk-mcp.json` | Soulseek P2P access MCP server | MCPMarket: Slsk MCP |
| `mcp/slskd-mcp.json` | slskd OpenAPI → MCP auto-generated server | github.com/abl030/slskd-mcp |
| `mcp/subsonic-mcp.json` | Subsonic/OpenSubsonic library ops MCP | subsonic.org / opensubsonic.netlify.app |

---

## Skill Count Summary

| Category | Count |
|---|---|
| Meta / Reasoning | 6 |
| Coding | 5 |
| Obsidian (official + bespoke) | 9  |
| Homelab (behavior + action) | 12 |
| Media / Music / DJ | 13 |
| Social | 2 |
| MCP / Tool Bridge | 3 |
| **Total** | **50** 

---

## Upstream Links

- Official Obsidian Skills: https://github.com/kepano/obsidian-skills
- claude-homelab (SKILL.md structure): https://github.com/jmagar/claude-homelab
- Slsk MCP: https://mcpmarket.com
- slskd-mcp: https://github.com/abl030/slskd-mcp
- slskd: https://github.com/slskd/slskd
- Subsonic API: https://subsonic.org/pages/api.jsp
- OpenSubsonic API: https://opensubsonic.netlify.app
- Proxmox VE: https://www.proxmox.com/en/proxmox-virtual-environment
