---
name: homelab-monitoring-analyst
description: Interprets homelab metrics and logs, summarizes incidents, and suggests investigation paths.
category: homelab
tags: [homelab, monitoring, observability, incidents]
agents: [opencode, freebuff, antigravity, codex]
---

# homelab-monitoring-analyst

## Purpose

Helps agents interpret monitoring data from homelab services, summarize what is happening, and suggest next steps for investigation or remediation.

## Invocation

**OpenCode / Codex:** `Invoke homelab-monitoring-analyst`
**Freebuff:** `/skill homelab-monitoring-analyst`

## Workflow

### Reading Metrics
1. Ask the user which monitoring source to use: Proxmox dashboard, Netdata, Grafana, service logs, or Docker stats.
2. Interpret the data: identify CPU/memory/disk pressure, failed services, high error rates, or unusual traffic.
3. Summarize in plain language: what is normal, what is abnormal, and what is the trend.

### Incident Triage
1. Classify severity: **Info / Warning / Critical**
2. Identify affected services and downstream dependencies.
3. Suggest specific investigation steps (e.g., check logs at `/var/log/`, inspect Docker container, review recent changes in homelab-logbook).
4. Recommend remediation if the issue is clear; escalate to user if not.

### Post-Incident Summary
After resolution, produce a brief incident summary:
- What happened
- When it started and ended
- Root cause (or best hypothesis)
- What was done to fix it
- What to watch going forward

Log the summary to `homelab-logbook` and `obsidian-homelab-logbook`.

## Monitoring Tools Reference

- Proxmox dashboard: https://pve.proxmox.com/wiki/Web_Interface
- Netdata: https://learn.netdata.cloud/
- Grafana: https://grafana.com/docs/
- Uptime Kuma: https://github.com/louislam/uptime-kuma

## Companion Skills

- `homelab-safe-ops` — always active
- `homelab-logbook` — log incidents and resolutions
- `homelab-change-planner` — if remediation requires a change
