---
name: homelab-change-planner
description: Plans infrastructure changes with explicit risk assessment and rollback steps before execution.
category: homelab
tags: [homelab, change-management, planning, risk]
agents: [opencode, freebuff, antigravity, codex]
---

# homelab-change-planner

## Purpose

Ensures every homelab change is planned before execution, with clear risk assessment, success criteria, and rollback procedures.

## Invocation

**OpenCode / Codex:** `Invoke homelab-change-planner`
**Freebuff:** `/skill homelab-change-planner`

## Workflow

For every proposed change, produce a change plan with these sections:

### 1. Change Summary
- What is changing?
- Why is it changing?
- Which nodes/services are affected?

### 2. Risk Assessment
- **Low / Medium / High** risk rating
- What could go wrong?
- What is the blast radius if it fails?

### 3. Prerequisites
- Is there a recent backup? When was it taken?
- Are dependent services noted?
- Is there a staging environment to test on first?

### 4. Steps
- Numbered, atomic steps
- Each step includes: what to do, expected output, and how to verify success

### 5. Rollback Plan
- How to undo each step
- Which backup to restore from if needed
- Time estimate to roll back

### 6. Post-Change Verification
- How to confirm the change succeeded
- Which services to test
- What to monitor for 30 minutes after the change

## Safety

- Never execute a change without a completed plan.
- Always invoke `homelab-safe-ops` alongside this skill.
- Log the completed change plan to `homelab-logbook`.

## Companion Skills

- `homelab-safe-ops` — safety constraints
- `homelab-topology-mapper` — understand affected components
- `homelab-logbook` — log the change after execution
- `homelab-monitoring-analyst` — watch for issues post-change
