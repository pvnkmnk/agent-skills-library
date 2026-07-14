# homelab-monitoring-analyst

Translates raw metrics, alerts, and logs from the homelab observability stack into actionable diagnoses and ranked remediation recommendations.

## Quick Start

Invoke via your agent: `Invoke homelab-monitoring-analyst` (OpenCode/Codex) or `/skill homelab-monitoring-analyst` (Freebuff).

## What it does

- Pulls current CPU, RAM, disk, and network stats from the configured monitoring endpoint (Prometheus, Netdata, or equivalent).
- Reviews active and recently fired alerts.
- Scans service logs for errors, warnings, and restart events.
- Correlates metric spikes with log events and recent change history.
- Diagnoses the root cause or most likely cause.
- Proposes remediation steps ranked by confidence.
- Hands off to `homelab-change-planner` when a structural fix is needed.

## Dependencies

- At least one active monitoring source: Prometheus/Alertmanager, Grafana, Netdata, Docker stats, or `journalctl`
- Optional: `mcp/proxmox-mcp.json` for Proxmox task log access

## Companion Skills

`homelab-change-planner` · `homelab-safe-ops` · `homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
