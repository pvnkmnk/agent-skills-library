# homelab-logbook

The primary audit trail for all homelab operations — records every change, incident, and maintenance event in a structured, searchable log format with consistent fields.

## Quick Start

Invoke via your agent: `Invoke homelab-logbook` (OpenCode/Codex) or `/skill homelab-logbook` (Freebuff).

## What it does

- Classifies the event: change, incident, maintenance, or observation.
- Captures date/time, host/service, severity, summary, details, and result.
- Appends the entry to the running log and pushes to `obsidian-homelab-logbook` for vault storage.
- Applies host and severity tags, and updates the homelab log index when a new host or service appears.

## Dependencies

- Any homelab environment with a running log file or Obsidian vault
- Optional: `obsidian-homelab-logbook` for vault-native storage

## Companion Skills

`obsidian-homelab-logbook` · `homelab-change-planner` · `homelab-monitoring-analyst`

See [SKILL.md](./SKILL.md) for the full canonical specification.
