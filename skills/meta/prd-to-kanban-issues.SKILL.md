---
name: prd-to-kanban-issues
description: Decomposes a PRD into Kanban-ready GitHub issues with acceptance criteria, labels, and effort estimates.
category: meta
tags: [meta, prd, kanban, github, issues, planning]
agents: [opencode, freebuff, antigravity, codex]
---

# prd-to-kanban-issues

## Purpose

Takes a completed PRD and produces a set of well-scoped GitHub issues ready to drop into a Kanban board. Each issue has a clear title, description, acceptance criteria, label suggestions, and a rough effort estimate.

## Invocation

**OpenCode / Codex:** `Invoke prd-to-kanban-issues`
**Freebuff:** `/skill prd-to-kanban-issues`

## Issue Output Template

```markdown
**Title:** [type]: <short description>
**Labels:** feature | bug | chore | spike
**Estimate:** XS (< 1h) | S (1–3h) | M (3–8h) | L (1–2d) | XL (2d+)

**Description:**
<context and motivation>

**Acceptance Criteria:**
- [ ] <criterion>

**Dependencies:** <other issues or external systems>
```

## Workflow Steps

1. **Ingest PRD.**
2. **Identify** each distinct unit of work from the acceptance criteria.
3. **Write one issue per unit** using the template above.
4. **Assign labels** (feature, bug, chore, spike).
5. **Estimate effort** based on scope and dependencies.
6. **List dependencies** between issues.
7. **Present** the full issue set for user review.

## Inputs

- Completed PRD (from `write-prd-from-conversation` or existing doc)
- Optional: existing GitHub labels or project template to match

## Outputs

- Set of formatted GitHub issue bodies ready to create
- Dependency graph between issues
- Optional: Kanban column assignments (Backlog / In Progress / Review / Done)

## Failure Modes

- **PRD acceptance criteria are too vague** — ask for refinement before decomposing; vague criteria produce un-testable issues.

## Companion Skills

- `write-prd-from-conversation` — upstream PRD source
- `grill-me` — validate PRD before decomposing
