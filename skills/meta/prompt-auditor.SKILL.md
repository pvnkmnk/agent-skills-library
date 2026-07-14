---
name: prompt-auditor
description: Reviews and rewrites prompts for clarity, specificity, safety, and agent-compatibility before they are sent to any LLM or agent.
category: meta
tags: [meta, prompts, audit, rewrite, safety, clarity]
agents: [opencode, freebuff, antigravity, codex]
---

# prompt-auditor

## Purpose

Ensures every prompt sent to an agent or LLM is clear, specific, appropriately scoped, and free of ambiguity that could produce hallucinations or unexpected behavior. Reviews prompts before dispatch and proposes rewrites when necessary.

## Invocation

**OpenCode / Codex:** `Invoke prompt-auditor`
**Freebuff:** `/skill prompt-auditor`

## Audit Dimensions

1. **Clarity:** Is the instruction unambiguous? Could it be read in two different ways?
2. **Specificity:** Are format, scope, length, and output type defined?
3. **Context:** Does the prompt include enough background for the model to answer accurately?
4. **Safety:** Does the prompt risk eliciting harmful, biased, or hallucinated output?
5. **Agent compatibility:** If this prompt is for a tool-calling agent, does it correctly scope the tools available?
6. **Redundancy:** Is any part of the prompt restating information already in the system prompt?

## Workflow Steps

1. **Receive prompt draft.**
2. **Score** each dimension (1–5).
3. **Flag issues** with specific line references.
4. **Rewrite** the prompt addressing all flagged issues.
5. **Compare:** Present original and rewrite side-by-side.

## Inputs

- Draft prompt text
- Optional: target model or agent context (OpenCode, Freebuff, raw API, etc.)

## Outputs

- Scored audit report per dimension
- Rewritten prompt
- Side-by-side diff

## Failure Modes

- **Prompt is a single word** — expand the prompt into a properly scoped version and ask user to confirm.
- **Prompt contains instructions that conflict with system prompt** — flag the conflict; do not silently override.

## Companion Skills

- `grill-me` — pre-flight the idea before writing the prompt
- `eval-loop` — evaluate output after sending the audited prompt
