# agent-skills-library

> A comprehensive, opinionated agent skills library for **OpenCode**, **Freebuff**, **Antigravity CLI**, and **Codex** — covering homelab, media, music, DJ, Obsidian, coding, and social domains.

**Owner:** pvnkmnk  
**Last updated:** July 14, 2026  
**Stack:** Windows 11 + WSL2, MCP, Obsidian, Cipher/Mem0, slskd, Subsonic/OpenSubsonic, Proxmox

---

## Overview

This repo is the single source of truth for all agent skills used across the pvnkmnk agent ecosystem. It follows a two-layer model:

- **Behavior layer** — SKILL.md files that encode opinionated workflows, decision trees, safety rules, and domain knowledge for each agent.
- **Action layer** — MCP server configs and API wrappers (Proxmox MCP, Slsk MCP, slskd-mcp, Subsonic/OpenSubsonic HTTP APIs) that do the actual work.

Agents (OpenCode, Freebuff, Antigravity CLI, Codex) load skills by referencing this repo in their config (`agents.md`, `opencode.json`, or equivalent skill directories).

---

## Repo Structure

```
agent-skills-library/
  README.md                        <- this file
  GUIDE.md                         <- full agent skills deep-dive guide
  REFERENCE.md                     <- companion skill reference table
  agents.md                        <- OpenCode/Freebuff agent skill index
  skills/
    meta/
      grill-me.SKILL.md
      prompt-auditor.SKILL.md
      write-prd-from-conversation.SKILL.md
      prd-to-kanban-issues.SKILL.md
      orchestrator.SKILL.md
      eval-loop.SKILL.md
    coding/
      tdd-loop.SKILL.md
      refactor-with-tests.SKILL.md
      architecture-improvement.SKILL.md
      security-audit.SKILL.md
      authz-and-audit-log.SKILL.md
    obsidian/
      obsidian-markdown.SKILL.md
      obsidian-bases.SKILL.md
      json-canvas.SKILL.md
      obsidian-cli.SKILL.md
      defuddle.SKILL.md
      obsidian-vault-architect.SKILL.md
      obsidian-homelab-logbook.SKILL.md
      obsidian-music-journal.SKILL.md
    homelab/
      homelab-topology-mapper.SKILL.md
      homelab-change-planner.SKILL.md
      homelab-safe-ops.SKILL.md
      homelab-monitoring-analyst.SKILL.md
      homelab-logbook.SKILL.md
      homelab-research-librarian.SKILL.md
      media-stack-builder.SKILL.md
      reverse-proxy-and-tunnel.SKILL.md
      docker-app-deployer.SKILL.md
      homelab-sre-agent.SKILL.md
    media/
      soulseek-network-orienter.SKILL.md
      slskd-media-acquisition.SKILL.md
      slsk-mcp-client.SKILL.md
      subsonic-media-server.SKILL.md
      subsonic-api-client.SKILL.md
      netrunner-media-orchestrator.SKILL.md
      music-library-organizer.SKILL.md
      music-listening-journal.SKILL.md
      dj-library-curator.SKILL.md
      dj-set-architect.SKILL.md
      dj-mix-documentarian.SKILL.md
      music-project-planner.SKILL.md
      lyrics-and-theory-bridge.SKILL.md
    social/
      social-impact-lens.SKILL.md
      case-note-structurer.SKILL.md
    mcp/
      memory-layer-bridge.SKILL.md
      filesystem-refactor-planner.SKILL.md
      git-safe-ops.SKILL.md
  mcp/
      proxmox-mcp.json
      slsk-mcp.json
      slskd-mcp.json
      subsonic-mcp.json
```

---

## Skill Categories

| Category | Skills | Description |
|---|---|---|
| **Meta / Reasoning** | 6 | Planning, auditing, PRD, orchestration, eval |
| **Coding** | 5 | TDD, refactoring, architecture, security, authZ |
| **Obsidian** | 8 | Official Obsidian Skills + bespoke vault skills |
| **Homelab** | 10 | Proxmox, media stack, networking, SRE, research |
| **Media / Music** | 13 | Soulseek, slskd, Subsonic, DJ, listening, netrunner |
| **Social** | 2 | Social impact lens, case notes |
| **MCP / Tools** | 3 | Memory bridge, filesystem, git safety |

---

## Quick Start

### OpenCode

1. Clone this repo to `~/.config/opencode/skills/` or your project root.
2. Add to your `agents.md`:

```markdown
## Skills
This agent has access to the skills in ./skills/. Use "Invoke <skill-name>" to activate a skill.
```

3. Reference in `opencode.json`:

```json
{
  "skills": "./skills"
}
```

### Freebuff

1. Clone or symlink `skills/` into Freebuff's skill directory.
2. Invoke skills via `/skill <skill-name>` or as configured.

### Antigravity CLI / Codex

1. Point your agent config at this repo's `skills/` directory.
2. Use your skill manager (aix/OpenPackage or equivalent) to index skills from this repo.

---

## MCP Action Layers

The following community-backed MCP servers provide the action layer underneath behavioral skills:

| MCP Server | Purpose | Config |
|---|---|---|
| Proxmox MCP | Proxmox VM/LXC/monitoring | `mcp/proxmox-mcp.json` |
| Slsk MCP | Soulseek P2P search & download | `mcp/slsk-mcp.json` |
| slskd-mcp | slskd OpenAPI → MCP (70 paths) | `mcp/slskd-mcp.json` |
| Subsonic MCP | Subsonic/OpenSubsonic library ops | `mcp/subsonic-mcp.json` |

---

## Upstream Sources

- [Official Obsidian Skills](https://github.com/kepano/obsidian-skills) by kepano
- [claude-homelab](https://github.com/jmagar/claude-homelab) by jmagar (SKILL.md structure reference)
- [Slsk MCP](https://mcpmarket.com) — Soulseek MCP server
- [slskd-mcp](https://github.com/abl030/slskd-mcp) by abl030
- [Subsonic API](https://subsonic.org/pages/api.jsp) / [OpenSubsonic API](https://opensubsonic.netlify.app)
- [slskd](https://github.com/slskd/slskd) — headless Soulseek client

---

## Philosophy

- **Behavior on top, action underneath.** Skills encode *how to think and decide*; MCP servers encode *how to act*.
- **Safety by default.** Every homelab and media skill has explicit safety rules and read-first constraints.
- **Domain-true.** Skills reflect actual workflows: Soulseek culture, Subsonic/OpenSubsonic auth, Proxmox VE, Obsidian vault semantics, DJ set architecture, social work ethics.
- **Composable.** Skills are designed to call each other (e.g., `netrunner-media-orchestrator` chains `slskd-media-acquisition` → `music-library-organizer` → `subsonic-media-server` → `obsidian-music-journal`).
