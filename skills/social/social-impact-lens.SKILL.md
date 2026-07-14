---
name: social-impact-lens
description: Applies a sociological and social-work ethics lens to any feature, system design, or policy decision — surfaces equity, access, harm, and unintended consequence risks.
category: social
tags: [social, ethics, equity, sociology, harm-reduction, accessibility]
agents: [opencode, freebuff, antigravity, codex]
---

# social-impact-lens

## Purpose

Brings a sociological and social-work ethics perspective to technical and product decisions. Asks who is harmed, who is excluded, whose labor is hidden, and what structural inequities a system might reinforce or create. Not a compliance checklist — a genuine ethical reasoning process.

## Invocation

**OpenCode / Codex:** `Invoke social-impact-lens`
**Freebuff:** `/skill social-impact-lens`

## Review Dimensions

1. **Access & Equity:** Who cannot use this as designed? What barriers exist (language, disability, income, connectivity)?
2. **Data & Privacy:** Whose data is collected? Is consent meaningful? Are marginalized groups over-represented in risk?
3. **Labor & Extraction:** Does this system depend on invisible, underpaid, or coerced labor?
4. **Harm Pathways:** What is the worst realistic misuse? Who is most vulnerable to it?
5. **Structural Reinforcement:** Does this system entrench existing inequalities by design?
6. **Community Impact:** What happens to the communities adjacent to this system's deployment?

## Workflow Steps

1. **Describe the system or feature** in one paragraph.
2. **Apply each dimension** — generate 1–3 questions per dimension.
3. **Score risk** per dimension (Low / Medium / High).
4. **Summarize** the top 2–3 concerns with concrete mitigation suggestions.
5. **Flag non-negotiables** — any dimension rated High must be addressed before launch.

## Inputs

- Feature spec, system design doc, or policy description
- Optional: target user population and deployment context

## Outputs

- Dimension-by-dimension risk scores
- Top 2–3 concern summary with mitigations
- Non-negotiable flags (High-risk dimensions)

## Failure Modes

- **System is purely internal tooling** — still apply; internal tools affect workers and teams.
- **User resists the lens** — present findings factually; do not moralize. The goal is information, not persuasion.

## Companion Skills

- `grill-me` — adversarial pre-flight for the same proposal
- `prompt-auditor` — check that AI prompts don’t encode biased assumptions
- `case-note-structurer` — for direct social work practice contexts
