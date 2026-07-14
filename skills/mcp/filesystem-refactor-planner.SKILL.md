---
name: filesystem-refactor-planner
description: Plans filesystem and directory structure refactors safely using MCP filesystem tools — always produces a move plan for user review before execution.
category: mcp
tags: [mcp, filesystem, refactor, planning, safety]
agents: [opencode, freebuff, antigravity, codex]
---

# filesystem-refactor-planner

## Purpose

Plans filesystem reorganisations — rename, move, restructure, or clean directories — using MCP filesystem tools. Always produces a human-readable move plan for user approval before any file is touched. Prevents accidental deletions and lost work during restructures.

## Invocation

**OpenCode / Codex:** `Invoke filesystem-refactor-planner`
**Freebuff:** `/skill filesystem-refactor-planner`

## Workflow Steps

1. **Survey:** Use MCP filesystem tool to list the current directory tree.
2. **Understand intent:** Clarify the desired end state with the user.
3. **Draft move plan:** Produce a table of every planned operation:
   - `MOVE old/path/file → new/path/file`
   - `RENAME old-name → new-name`
   - `DELETE path/file (reason)`
   - `CREATE new/dir/`
4. **Present plan:** Show the full plan to the user. Do not execute anything yet.
5. **Get approval:** Wait for explicit user confirmation.
6. **Execute:** Carry out each operation in order via MCP filesystem tool.
7. **Verify:** List the result tree and confirm it matches the plan.
8. **Log:** Record the restructure in `homelab-logbook` or project notes.

## Rules

- Never execute a destructive operation (DELETE, OVERWRITE) without explicit user confirmation.
- Never silently skip a planned operation — report any skipped step and why.
- If any operation fails mid-plan, stop and report the failure state before attempting to continue.

## Inputs

- Current filesystem root or directory to restructure
- Desired end state description
- Optional: files/directories to exclude from restructure

## Outputs

- Current directory tree snapshot
- Move plan table (MOVE / RENAME / DELETE / CREATE per row)
- Post-execution verification tree

## Failure Modes

- **MCP filesystem tool unavailable** — fall back to proposing shell commands for user to run manually.
- **File permissions block a move** — surface the permission error; do not attempt to escalate privileges silently.
- **Destination path already exists** — flag the conflict; ask user whether to overwrite, merge, or rename.

## Companion Skills

- `git-safe-ops` — if restructure involves a git repository, branch first
- `homelab-safe-ops` — if restructure is on a live homelab host
- `homelab-logbook` — log the restructure
