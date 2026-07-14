---
name: refactor-with-tests
description: Safely refactors existing code using the test suite as the safety net — characterise behavior first, then restructure.
category: coding
tags: [coding, refactor, testing, safety, quality]
agents: [opencode, freebuff, antigravity, codex]
---

# refactor-with-tests

## Purpose

Provides a disciplined process for restructuring existing code without breaking behavior. Establishes test coverage as a safety net before any structural change is made.

## Invocation

**OpenCode / Codex:** `Invoke refactor-with-tests`
**Freebuff:** `/skill refactor-with-tests`

## Workflow Steps

1. **Characterise:** Run existing tests; note coverage gaps.
2. **Cover gaps:** Write characterisation tests for uncovered paths.
3. **Baseline:** Confirm all tests pass before touching implementation.
4. **Refactor in small steps:** One structural change at a time.
5. **Verify after each step:** All tests must pass before the next change.
6. **Commit per step:** Small, atomic commits with clear messages.
7. **Final review:** Confirm no behavior changed; check for new coverage gaps introduced.

## Rules

- Never start refactoring without a green test baseline.
- Never change behavior and structure in the same commit.
- If a refactor reveals a bug, stop and fix the bug in a separate commit before continuing.

## Inputs

- Code module or file to refactor
- Existing test suite (even if partial)
- Refactoring goal (e.g., extract method, split module, rename, reduce coupling)

## Outputs

- Characterisation test additions
- Refactored code with all tests passing
- Commit log with atomic refactor steps

## Failure Modes

- **No existing tests at all** — write a minimal characterisation suite before any refactoring begins.
- **Refactor scope grows** — stop, re-scope to the original goal, and create a new issue for the expanded work.

## Companion Skills

- `tdd-loop` — for new features alongside refactoring
- `git-safe-ops` — safe branching and commit discipline
- `architecture-improvement` — for larger structural redesigns
