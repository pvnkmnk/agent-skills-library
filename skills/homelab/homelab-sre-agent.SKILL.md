---
name: homelab-sre-agent
description: SRE-style agent behavior over homelab monitoring tools and MCP endpoints — scheduled health checks, incident detection, and triage.
category: homelab
tags: [homelab, sre, monitoring, automation, reliability]
agents: [opencode, freebuff, antigravity, codex]
---

# homelab-sre-agent

## Purpose

Applies SRE (Site Reliability Engineering) principles to homelab operations: systematic health checks, incident detection, triage, and resolution tracking.

## Invocation

**OpenCode / Codex:** `Invoke homelab-sre-agent`
**Freebuff:** `/skill homelab-sre-agent`

## SRE Agent Behaviors

### Scheduled Health Checks
When triggered (manually or on a schedule), run through:
1. Are all expected Docker containers running? (`docker compose ps` on each stack)
2. Are Proxmox VMs/LXCs in expected states?
3. Is the reverse proxy responding and routing correctly?
4. Is the media server (Navidrome/Subsonic) responding to API pings?
5. Is slskd connected to the Soulseek network?
6. Are backups running on schedule? (Check PBS or backup logs)

### Incident Detection Rules
- Container in `Exit` state → immediate triage
- High CPU/RAM sustained >15 min → investigation
- Disk usage >80% → alert
- Failed backup → alert
- Service returning 5xx for >5 min → triage

### Triage Flow
1. Identify affected service.
2. Check recent changes in `homelab-logbook`.
3. Check container/service logs.
4. Apply known fix if available; otherwise escalate to user with full context.
5. Log resolution in `homelab-logbook` and `obsidian-homelab-logbook`.

## MCP Integration

Uses Proxmox MCP (`mcp/proxmox-mcp.json`) for:
- VM/LXC state queries
- Resource usage checks
- Node health status

Does NOT execute destructive operations autonomously. Always confirms with user before restarting or stopping services.

## Safety

- `homelab-safe-ops` is always active.
- No autonomous destructive actions (no `docker rm`, no VM deletion, no `docker system prune`).
- All findings are logged to `homelab-logbook`.

## Companion Skills

- `homelab-safe-ops` — always active
- `homelab-monitoring-analyst` — metric interpretation
- `homelab-change-planner` — for any remediation requiring changes
- `homelab-logbook` — incident and resolution logging
