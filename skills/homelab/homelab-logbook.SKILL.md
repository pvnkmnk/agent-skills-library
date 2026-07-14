---
name: homelab-logbook
description: Systematizes logging of homelab changes and incidents, linked to topology diagrams and Obsidian.
category: homelab
tags: [homelab, logging, documentation, audit]
agents: [opencode, freebuff, antigravity, codex]
---

# homelab-logbook

## Purpose

Every homelab change and incident should be logged. This skill defines the structure and process for maintaining the homelab logbook.

## Invocation

**OpenCode / Codex:** `Invoke homelab-logbook`
**Freebuff:** `/skill homelab-logbook`

## Log Entry Format

For each change or incident, produce an entry with:

```markdown
## [YYYY-MM-DD] <Short Title>

**Type:** Change | Incident | Maintenance
**Severity:** Info | Warning | Critical (for incidents)
**Affected:** <nodes/services affected>
**Author:** pvnkmnk

### What Happened
<Summary of the change or incident>

### Steps Taken
1. <step>
2. <step>

### Outcome
<Result: success, partial, or failure and why>

### Follow-Up
- [ ] <any open tasks>

### References
- Topology: [[homelab-topology]]
- Change plan: [[change-plan-YYYY-MM-DD]]
```

## Where to Log

1. **Obsidian vault** — via `obsidian-homelab-logbook` skill (primary long-term record)
2. **Git repo** — commit log as secondary audit trail
3. **Proxmox notes** — add a note to the affected VM/CT in Proxmox UI for quick reference

## Rules

- Log every change, no matter how small.
- Log incidents even if nothing was done (for trend analysis).
- Always link to the relevant topology and change plan.
- Never delete log entries; supersede them with new entries if needed.

## Companion Skills

- `obsidian-homelab-logbook` — Obsidian-specific logging
- `homelab-change-planner` — log the plan before execution
- `homelab-monitoring-analyst` — log incident summaries
