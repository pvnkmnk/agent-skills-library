---
name: orchestrator
description: Plans and delegates multi-step tasks across agents, tools, and skills — the top-level coordination layer for complex workflows.
category: meta
tags: [meta, orchestration, multi-agent, delegation, planning]
agents: [opencode, freebuff, antigravity, codex]
---

# orchestrator

## Purpose

Coordinates complex, multi-step tasks that span multiple skills, agents, or tools. Decomposes a high-level goal into ordered subtasks, assigns each subtask to the appropriate skill or agent, tracks completion, and synthesizes results.

## Invocation

**OpenCode / Codex:** `Invoke orchestrator`
**Freebuff:** `/skill orchestrator`

## Workflow Steps

1. **Ingest goal:** Understand the end state the user wants to reach.
2. **Decompose:** Break the goal into ordered, atomic subtasks.
3. **Map:** Assign each subtask to the most appropriate skill or agent.
4. **Identify dependencies:** Note which subtasks must complete before others begin.
5. **Execute:** Invoke each subtask in order (or in parallel where safe).
6. **Gate:** After each subtask, verify output before proceeding to the next.
7. **Synthesize:** Combine outputs into a cohesive result.
8. **Log:** Record the orchestration plan and outcomes.

## Inputs

- High-level goal or task description
- Available skills and agents (drawn from REFERENCE.md)
- Any constraints: time, safety, sequencing

## Outputs

- Ordered orchestration plan with skill assignments
- Execution log with subtask outcomes
- Synthesized final output
- Blockers or failures surfaced to user with recovery options

## Safety

- Never invoke a destructive skill (homelab-safe-ops, git-safe-ops class) without confirming the full plan with the user first.
- Stop and surface blockers rather than skipping steps silently.

## Failure Modes

- **Circular dependency between subtasks** — surface the cycle and ask user to resolve ordering.
- **Subtask fails mid-chain** — halt, report the failure, and present recovery options before continuing.

## Companion Skills

- `grill-me` — stress-test the orchestration plan before execution
- `eval-loop` — evaluate outputs at each gate
- `homelab-safe-ops` — safety gate for infrastructure subtasks
- `git-safe-ops` — safety gate for code subtasks
