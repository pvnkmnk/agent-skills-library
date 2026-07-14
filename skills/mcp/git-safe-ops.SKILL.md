---
name: git-safe-ops
description: Encodes safe git operation rules — no force-push to main, always branch, always review before merge. Always-on skill for all coding sessions.
category: mcp
tags: [git, safety, version-control, always-on]
agents: [opencode, freebuff, antigravity, codex]
---

# git-safe-ops

## Purpose

Provides the standing safety contract for all git operations. Prevents destructive version-control actions by encoding a non-negotiable rule set that applies across every coding session. This skill is **always-on** — it must be active in every session that touches any git repository.

## Invocation

**OpenCode / Codex:** `Invoke git-safe-ops`
**Freebuff:** `/skill git-safe-ops`

## Core Safety Rules

1. **Never force-push to `main` or `master`.** `git push --force` to a protected branch is forbidden. Use `--force-with-lease` on feature branches only, with explicit user confirmation.
2. **Always branch before changing.** No direct commits to `main`. Create a feature or fix branch first: `git checkout -b <type>/<description>`.
3. **Review before merge.** Always show a `git diff` or PR diff before merging. Never auto-merge without user review.
4. **No `git reset --hard` on shared branches.** Destructive history rewrites on shared branches require explicit user confirmation with a clear explanation of consequences.
5. **Commit messages must be descriptive.** Use Conventional Commits format: `<type>(<scope>): <description>`. Never commit with `--no-verify` without explaining why.
6. **Stash before switching context.** If there are uncommitted changes, run `git stash` before checking out another branch. Never discard changes silently.
7. **Tag releases explicitly.** Do not rely on branch names to communicate release versions. Use annotated tags: `git tag -a v1.x.x -m "<changelog>"`.
8. **Secrets stay out of commits.** Before committing, check for hardcoded credentials, tokens, or API keys. Use `.gitignore`, `.env` files, and secret managers.

## Escalation Rules

Stop and ask the user if:
- Any operation would rewrite shared branch history.
- A merge would result in conflicts that cannot be safely auto-resolved.
- A commit includes new files that might contain secrets.
- The working tree is dirty and the intent of the next operation is ambiguous.

## Inputs

- Current repository state (branch, uncommitted changes, remote status)
- Intended git operation (from user request or agent plan)

## Outputs

- Pre-flight safety assessment of the intended operation
- Safe alternative if the requested operation violates a rule
- Confirmed safe operation execution

## Failure Modes

- **Ambiguous branch target** — user says "push this" without specifying branch; always confirm target branch before pushing.
- **Detached HEAD state** — user attempts to commit; surface the detached state and guide back to a named branch.
- **Remote diverged from local** — surface divergence before pull or push; do not auto-resolve.

## Safety

- This skill enforces rules; it does not override explicit user instructions. If the user explicitly requests a normally-forbidden operation after being warned, comply and log the decision.
- Never silently modify or skip a safety check.

## References

- Conventional Commits: https://www.conventionalcommits.org/
- Git docs: https://git-scm.com/docs
- GitHub branch protection: https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches
- git-secret / git-crypt: https://git-secret.io/

## Companion Skills

- `homelab-safe-ops` — sister always-on safety skill for infrastructure
- `memory-layer-bridge` — always-on context routing
- `tdd-loop` — safe code iteration alongside safe git ops
- `refactor-with-tests` — safe refactoring with commit checkpoints
