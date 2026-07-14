---
name: obsidian-homelab-logbook
description: Logs homelab events, changes, incidents, and maintenance notes to structured Obsidian notes.
category: obsidian
tags: [obsidian, homelab, logging, incidents, maintenance]
agents: [opencode, freebuff, antigravity, codex]
---

# obsidian-homelab-logbook

## Purpose

Provides a structured Obsidian journaling layer for homelab operations. Captures change events, incident reports, maintenance windows, VM/container state changes, and network topology updates. Complements `homelab-logbook` with Obsidian-native formatting and cross-linking.

## Invocation

**OpenCode / Codex:** `Invoke obsidian-homelab-logbook`
**Freebuff:** `/skill obsidian-homelab-logbook`

## Workflow Steps

1. **Event type:** Classify event (change, incident, maintenance, observation).
2. **Context:** Capture timestamp, affected host/service, severity.
3. **Write:** Create note under `Homelab/Logs/YYYY-MM-DD-event-title.md`.
4. **Link:** Backlink to host or service note in vault.
5. **Tag:** Apply status and host tags.
6. **Index:** Update `Homelab/MOC.md` if a new service or host note is created.

## Safety

- Writes only to Obsidian vault; never modifies live infrastructure.
- Sensitive credentials must never be written to vault notes.

## References

- [Obsidian Help](https://help.obsidian.md/)

## Companion Skills

- `homelab-logbook`, `homelab-change-planner`, `homelab-monitoring-analyst`, `obsidian-vault-architect`
