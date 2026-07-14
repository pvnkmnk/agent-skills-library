# homelab-sre-agent

Applies Site Reliability Engineering discipline to homelab operations — defines SLOs, tracks error budgets, manages incident lifecycles, identifies toil, and drives continuous improvement through post-incident reviews.

## Quick Start

Invoke via your agent: `Invoke homelab-sre-agent` (OpenCode/Codex) or `/skill homelab-sre-agent` (Freebuff).

## What it does

- **SLO management:** Defines availability and latency targets per service; tracks burn rate and error budget consumption; recommends interventions when the budget is low.
- **Toil reduction:** Identifies repetitive manual operations and proposes automation (scripts, cron jobs, Ansible tasks); tracks toil-hours saved.
- **Incident management:** Detects, triages, mitigates, root-causes, and writes blameless post-incident reviews with action items.
- **Reliability reviews:** Periodically reviews change frequency, MTTR, and incident count; flags fragile components and proposes hardening.

## Dependencies

- Monitoring stack (Prometheus, Grafana, or Netdata) for SLO data
- `homelab-logbook` for incident records

## Companion Skills

`homelab-monitoring-analyst` · `homelab-change-planner` · `homelab-logbook` · `homelab-safe-ops`

See [SKILL.md](./SKILL.md) for the full canonical specification.
