# Obsidian Homelab Logbook

Structured Obsidian journaling layer for homelab operations — captures change events, incidents, maintenance windows, VM/container changes, and network topology updates with full vault cross-linking.

## Quick Start

Invoke via your agent: `Invoke obsidian-homelab-logbook` (OpenCode/Codex) or `/skill obsidian-homelab-logbook` (Freebuff).

## What it does

- Classifies the event (change, incident, maintenance, observation).
- Captures timestamp, affected host/service, and severity.
- Creates a structured note at `Homelab/Logs/YYYY-MM-DD-event-title.md`.
- Backlinks to the relevant host or service note in the vault.
- Applies status and host tags, and updates `Homelab/MOC.md` when new services are added.

## Dependencies

- Obsidian vault with write access and a `Homelab/` folder structure
- Optional: `homelab-change-planner` output to link change plans

## Companion Skills

`homelab-logbook` · `homelab-change-planner` · `homelab-monitoring-analyst` · `obsidian-vault-architect`

See [SKILL.md](./SKILL.md) for the full canonical specification.
