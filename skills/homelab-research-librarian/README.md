# homelab-research-librarian

Researches, evaluates, and documents homelab tooling, self-hosted application alternatives, and infrastructure patterns — produces structured comparison notes and decision records stored in Obsidian.

## Quick Start

Invoke via your agent: `Invoke homelab-research-librarian` (OpenCode/Codex) or `/skill homelab-research-librarian` (Freebuff).

## What it does

- Clarifies the research query (tool category, specific app, infrastructure pattern).
- Surveys candidates across self-hosted, open-source, and managed options.
- Scores each option on: ease of deployment, community support, resource usage, security posture, and maintenance burden.
- Produces a side-by-side comparison table.
- States a recommended option with rationale.
- Writes findings to Obsidian under `Homelab/Research/topic.md`.

## Dependencies

- Obsidian vault with write access and a `Homelab/Research/` folder
- Web access for research (or existing knowledge base)

## Companion Skills

`obsidian-homelab-logbook` · `homelab-change-planner`

See [SKILL.md](./SKILL.md) for the full canonical specification.
