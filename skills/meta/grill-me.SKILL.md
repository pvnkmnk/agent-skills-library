---
name: grill-me
description: Interrogates a plan or idea with pointed, adversarial questions to expose gaps, assumptions, and failure modes before execution begins.
category: meta
tags: [meta, planning, adversarial, review, pre-flight]
agents: [opencode, freebuff, antigravity, codex]
---

# grill-me

## Purpose

Forces rigorous pre-flight review of any plan, idea, feature, or decision by asking the questions the proposer hasn’t asked themselves. Operates as an internal devil's advocate — not to block progress, but to surface the gaps before they become production bugs or wasted effort.

## Invocation

**OpenCode / Codex:** `Invoke grill-me`
**Freebuff:** `/skill grill-me`

Natural triggers:
- "Grill this plan before I start"
- "What am I missing?"
- "Play devil's advocate on this approach"
- "Pre-flight check on [idea/feature/decision]"

## Workflow Steps

1. **Read the proposal:** Ingest the plan, idea, feature spec, or decision in full.
2. **Classify the risk surface:** Identify the domain (infrastructure, code, product, data, security, UX).
3. **Generate 5–10 grilling questions** across these axes:
   - **Assumptions:** What is being assumed that hasn’t been verified?
   - **Failure modes:** What happens when this goes wrong?
   - **Edge cases:** What inputs or states wasn’t considered?
   - **Dependencies:** What external systems or people does this rely on?
   - **Reversibility:** How hard is this to undo if it's wrong?
   - **Scope creep:** Is this doing more than it needs to?
   - **Security / privacy:** Does this create new attack surface?
4. **Present questions** without answers — the user answers them.
5. **Evaluate answers:** For each answer, assess whether it adequately addresses the gap. Flag insufficient answers.
6. **Summarize gaps:** Produce a short list of unresolved gaps that must be addressed before proceeding.

## Inputs

- Plan, idea, feature spec, or decision text (any format)
- Optional: domain context (infrastructure, coding, product, social)

## Outputs

- Ordered list of 5–10 pointed questions
- Gap summary after user answers
- Go / Conditional Go / No-Go recommendation with rationale

## Safety

- This skill is adversarial by design. If the user finds a question unfair or out of scope, they may dismiss it — the skill should not repeat dismissed questions.

## Failure Modes

- **Proposal is too vague to grill** — ask for a minimum viable description before proceeding.
- **Questions become repetitive** — if the plan is simple, 3–5 high-quality questions beat 10 mediocre ones.

## Companion Skills

- `prompt-auditor` — grill the prompt before grilling the plan
- `write-prd-from-conversation` — turn the grilled plan into a formal PRD
- `homelab-change-planner` — infrastructure-specific change pre-flight
