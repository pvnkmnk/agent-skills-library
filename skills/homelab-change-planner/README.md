# homelab-change-planner

Produces a structured change plan before any homelab infrastructure modification — defines scope, risk level, rollback path, and approval gate before a single command runs.

## Quick Start

Invoke via your agent: `Invoke homelab-change-planner` (OpenCode/Codex) or `/skill homelab-change-planner` (Freebuff).

## What it does

- Runs `homelab-topology-mapper` first to capture current state of affected hosts and services.
- Defines the intended change, target host/container/service, and expected outcome.
- Performs impact analysis: downstream dependencies, affected services, data at risk.
- Assigns a risk rating: LOW / MEDIUM / HIGH based on reversibility and blast radius.
- Writes a step-by-step rollback plan before proceeding.
- Requires explicit user confirmation (**approval gate**) before any execution begins.
- Executes changes step by step, confirming each step.
- Runs a post-change health check and logs the event to `homelab-logbook`.

## Dependencies

- `homelab-topology-mapper` for pre-flight state snapshot
- `homelab-logbook` for post-change logging
- Optional: `homelab-monitoring-analyst` for post-change health verification

## Companion Skills

`homelab-safe-ops` · `homelab-topology-mapper` · `homelab-logbook` · `homelab-monitoring-analyst`

See [SKILL.md](./SKILL.md) for the full canonical specification.
