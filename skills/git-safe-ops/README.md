# git-safe-ops

The always-on safety contract for all git operations — enforces branching discipline, blocks force-pushes to protected branches, and prevents credential leakage across every coding and infrastructure session.

## Quick Start

Invoke via your agent: `Invoke git-safe-ops` (OpenCode/Codex) or `/skill git-safe-ops` (Freebuff).

This skill is **always-on** — it should be active in every session where any git command might be executed.

## What it does

- Blocks force-pushes to `main`/`master`; permits `--force-with-lease` on feature branches only.
- Requires all work to happen on a named branch before any merge.
- Enforces a PR or `git diff main` review gate before merging.
- Validates commit messages follow `type: summary` convention.
- Stops the agent before any staged changeset that contains credentials or `.env` values.
- Requires explicit confirmation before `git clean`, `git reset --hard`, or branch deletion.
- Enforces release tagging for any deployment commit.

## Dependencies

- Any git repository accessible to the agent
- Optional: GitHub MCP or local git CLI

## Companion Skills

`homelab-safe-ops` · `memory-layer-bridge` · `tdd-loop` · `refactor-with-tests`

See [SKILL.md](./SKILL.md) for the full canonical specification.
