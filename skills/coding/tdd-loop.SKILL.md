---
name: tdd-loop
description: Drives a strict red-green-refactor TDD loop for any feature or fix — write the failing test first, make it pass with minimal code, then refactor.
category: coding
tags: [coding, tdd, testing, refactor, quality]
agents: [opencode, freebuff, antigravity, codex]
---

# tdd-loop

## Purpose

Enforces test-driven development discipline. No production code is written before a failing test exists. Keeps code minimal, covered, and continuously refactorable.

## Invocation

**OpenCode / Codex:** `Invoke tdd-loop`
**Freebuff:** `/skill tdd-loop`

## The Loop

```
Red → Green → Refactor → repeat
```

1. **Red:** Write a failing test that describes the desired behavior.
2. **Green:** Write the minimum code to make the test pass. No more.
3. **Refactor:** Clean up the implementation without changing behavior. All tests must still pass.
4. **Commit:** Commit the red state and green state separately if working in git.
5. **Repeat** for the next unit of behavior.

## Rules

- Never write production code without a failing test first.
- Green means all tests pass — not just the new one.
- Refactor only when green. Never refactor while red.
- One behavior per test. If a test covers two behaviors, split it.

## Inputs

- Feature description or bug report
- Existing test suite (if any)
- Language and test framework in use

## Outputs

- Failing test (red state)
- Minimal passing implementation (green state)
- Refactored implementation with full test suite passing
- Commit log with red/green/refactor checkpoints

## Failure Modes

- **No existing test framework** — suggest the canonical framework for the language; do not skip TDD.
- **Test is too broad** — decompose into smaller, focused tests before writing any code.

## Companion Skills

- `refactor-with-tests` — post-feature refactoring
- `git-safe-ops` — safe commit checkpointing
- `security-audit` — security pass after coverage is established
