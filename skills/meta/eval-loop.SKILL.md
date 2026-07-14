---
name: eval-loop
description: Runs structured evaluation loops on agent outputs against defined criteria — score, flag, iterate until acceptance threshold is met.
category: meta
tags: [meta, evaluation, testing, quality, iteration]
agents: [opencode, freebuff, antigravity, codex]
---

# eval-loop

## Purpose

Provides a structured framework for evaluating LLM and agent outputs against user-defined or skill-defined criteria. Scores outputs, flags failures, and iterates until the output meets the acceptance threshold or the maximum iteration count is reached.

## Invocation

**OpenCode / Codex:** `Invoke eval-loop`
**Freebuff:** `/skill eval-loop`

## Workflow Steps

1. **Define criteria:** Establish the evaluation rubric (correctness, completeness, tone, format, safety, etc.).
2. **Set threshold:** Define the minimum acceptable score per criterion and overall.
3. **Run output through criteria:** Score each criterion 1–5.
4. **Flag failures:** List criteria below threshold.
5. **Generate improvement prompt:** Write a targeted correction prompt for each failure.
6. **Re-run:** Submit the improvement prompt and re-evaluate the new output.
7. **Repeat** until all criteria meet threshold or max iterations (default: 3) is reached.
8. **Report:** Present the final output with eval scores and iteration history.

## Inputs

- Agent output to evaluate
- Evaluation criteria (user-defined or from the invoking skill)
- Acceptance threshold (default: 4/5 per criterion)
- Max iterations (default: 3)

## Outputs

- Scored evaluation report (per criterion, per iteration)
- Final accepted output
- Iteration history with improvement prompts

## Failure Modes

- **Max iterations reached without passing** — surface the best output so far and the remaining gaps; do not silently accept a failing output.
- **Criteria are contradictory** — flag the contradiction and ask user to resolve before evaluating.

## Companion Skills

- `prompt-auditor` — improve the input prompt before eval-looping the output
- `orchestrator` — use eval-loop as a quality gate within orchestration chains
