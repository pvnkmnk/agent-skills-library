# Agent Skills Library — Practitioner Guide

> How to use, extend, and operate the pvnkmnk agent-skills-library.
> Covers all four agents: OpenCode, Freebuff, Antigravity CLI, Codex.

---

## Overview

This library provides structured behavioral skills for AI coding and automation agents. Skills are organized into domain clusters and wired to MCP (Model Context Protocol) action layers that provide live tool access.

### Four-Layer Architecture

```
[Agent]
  └─ [Skills Layer]      <- SKILL.md files in skills/<domain>/
       └─ [MCP Layer]     <- mcp/*.json configs
            └─ [Tools]    <- Proxmox API, slskd REST, Subsonic API, Obsidian vault
                 └─ [Memory Layer]  <- Obsidian vault notes
```

---

## Quickstart

### 1. Clone the repo

```bash
git clone https://github.com/pvnkmnk/agent-skills-library
cd agent-skills-library
```

### 2. Wire an MCP config

Copy the stub from `mcp/` and fill in your credentials:

```bash
cp mcp/proxmox-mcp.json ~/.config/my-agent/mcp/proxmox-mcp.json
# Edit the file to set PROXMOX_HOST, PROXMOX_USER, PROXMOX_TOKEN_NAME, PROXMOX_TOKEN_VALUE
```

### 3. Load a skill

In your agent config, point to the skill file:

```yaml
skills:
  - path: skills/homelab/homelab-safe-ops.SKILL.md
  - path: skills/media/subsonic-api-client.SKILL.md
```

### 4. Invoke a skill

- **OpenCode / Codex:** `Invoke homelab-safe-ops`
- **Freebuff:** `/skill homelab-safe-ops`

---

## Domain Guide

### Homelab

**Skills:** `homelab-safe-ops`, `homelab-change-planner`, `homelab-monitoring-analyst`, `homelab-logbook`, `homelab-research-librarian`, `homelab-sre-agent`, `proxmox-topology-mapper`, `docker-app-deployer`, `reverse-proxy-and-tunnel`, `media-stack-builder`

**MCP:** `mcp/proxmox-mcp.json`

**Workflow pattern:**
1. Run `proxmox-topology-mapper` to understand current state.
2. Use `homelab-change-planner` to draft a change with rollback.
3. Gate execution through `homelab-safe-ops`.
4. Log outcome with `homelab-logbook` + `obsidian-homelab-logbook`.

**Safety:** All destructive operations require `homelab-safe-ops` confirmation gate. Never bypass this step.

---

### Media / Music / DJ

**Skills:** `soulseek-network-orienter`, `slskd-media-acquisition`, `slsk-mcp-client`, `subsonic-media-server`, `subsonic-api-client`, `netrunner-media-orchestrator`, `music-library-organizer`, `dj-library-curator`, `dj-set-architect`, `music-listening-journal`, `dj-mix-documentarian`, `music-project-planner`

**MCP:** `mcp/slsk-mcp.json`, `mcp/slskd-mcp.json`, `mcp/subsonic-mcp.json`

**Pipeline pattern (acquire → organize → serve → document):**
1. `soulseek-network-orienter` → understand network, search etiquette.
2. `slskd-media-acquisition` → search and download via slskd.
3. `music-library-organizer` → tag, structure, deduplicate.
4. `subsonic-media-server` → trigger rescan, verify ingestion.
5. `dj-library-curator` → build playlists for mixing.
6. `dj-set-architect` → plan and sequence the set.
7. `dj-mix-documentarian` + `obsidian-music-journal` → archive the mix.

For end-to-end automation, use `netrunner-media-orchestrator` to coordinate all steps.

---

### Obsidian

**Skills:** `obsidian-vault-architect`, `obsidian-homelab-logbook`, `obsidian-music-journal`

**Role:** Obsidian skills are the memory and journaling layer. All other domains write their outputs here. The vault is the persistent knowledge base for the homelab and music operations.

**Setup:**
1. Run `obsidian-vault-architect` once to set up the vault folder structure.
2. All domain skills will then write to the correct locations automatically.

---

## Adding a New Skill

1. Create `skills/<domain>/<skill-name>.SKILL.md` from the template below.
2. Update `REFERENCE.md` with the new skill row.
3. If a new MCP config is needed, add a stub to `mcp/<mcp-name>.json`.
4. Update this GUIDE.md if a new domain is introduced.

### SKILL.md Template

```markdown
---
name: skill-name
description: One-line description.
category: <domain>
tags: [tag1, tag2]
agents: [opencode, freebuff, antigravity, codex]
---

# skill-name

## Purpose

[What this skill enables. 2-3 sentences.]

## Invocation

**OpenCode / Codex:** `Invoke skill-name`
**Freebuff:** `/skill skill-name`

## Workflow Steps

1. **Step:** Description.
2. **Step:** Description.

## Safety

- [Constraint 1]
- [Constraint 2]

## References

- [Link text](URL)

## Companion Skills

- `companion-skill-a`, `companion-skill-b`
```

---

## MCP Config Setup

Each MCP stub in `mcp/` provides:
- `name` and `description`
- `upstream` (source repo/docs URL)
- `transport` (always `stdio` for local MCP servers)
- `env` (required environment variables with placeholder values)
- `skills` (skills that use this MCP)
- `safety` (constraints to enforce)

Never commit real credentials. Use environment variables or a secrets manager.

---

## Repeatable Iteration Pattern

For each new skill cluster:
1. Create SKILL.md files in `skills/<domain>/`.
2. Create or update MCP JSON stub in `mcp/`.
3. Add rows to `REFERENCE.md`.
4. Update this GUIDE.md domain section.
5. Commit with `feat: add <domain> skills`.

---

## Repository Structure

```
agent-skills-library/
  README.md              <- overview and quickstart
  GUIDE.md               <- this file: practitioner guide
  REFERENCE.md           <- master skill + MCP index
  agents.md              <- per-agent config notes
  skills/
    homelab/             <- homelab domain skills
    media/               <- media/music/DJ domain skills
    obsidian/            <- obsidian vault skills
    meta/                <- meta/reasoning skills
    coding/              <- coding skills
    social/              <- social skills
  mcp/
    proxmox-mcp.json     <- Proxmox VE MCP config
    slsk-mcp.json        <- Soulseek MCP config
    slskd-mcp.json       <- slskd MCP config
    subsonic-mcp.json    <- Subsonic MCP config
```


---

## New Skills — Quick Reference

### homelab-network-auditor
Audits the homelab network for open ports, exposed services, and firewall rule gaps.

**Invoke:** `Invoke homelab-network-auditor` (OpenCode/Codex) | `/skill homelab-network-auditor` (Freebuff)

**Workflow:**
1. Define scope (IP range / VLAN).
2. Run host discovery + port scan.
3. Compare results against documented firewall rules.
4. Review exposure report for unexpected open ports.
5. Create remediation tasks in `homelab-change-planner`.
6. Log findings in `homelab-logbook`.

**Safety:** Scope confirmation required before any scan. Only scan owned infrastructure.

---

### obsidian-vault-manager
Primary interface for all Obsidian vault operations: create notes, manage folders, apply templates, and maintain internal links.

**Invoke:** `Invoke obsidian-vault-manager` (OpenCode/Codex) | `/skill obsidian-vault-manager` (Freebuff)

**Workflow:**
1. Connect to Obsidian Local REST API (port 27123).
2. Resolve target note path within vault.
3. Apply template if creating new note in templated folder.
4. Write content with correct frontmatter, tags, and wikilinks.
5. Update index notes as needed.

**MCP:** Obsidian Local REST API plugin — https://github.com/coddingtonbear/obsidian-local-rest-api
