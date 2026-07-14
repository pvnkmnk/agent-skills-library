---
name: case-note-structurer
description: Structures case notes for social work and community support contexts — SOAP/DAP format, privacy-safe, professional tone.
category: social
tags: [social, case-notes, social-work, documentation, privacy, dap, soap]
agents: [opencode, freebuff, antigravity, codex]
---

# case-note-structurer

## Purpose

Helps social workers and community support practitioners write structured, professional case notes quickly. Applies SOAP (Subjective, Objective, Assessment, Plan) or DAP (Data, Assessment, Plan) format depending on context. Maintains privacy and professional tone throughout.

## Invocation

**OpenCode / Codex:** `Invoke case-note-structurer`
**Freebuff:** `/skill case-note-structurer`

## Note Formats

### SOAP
- **S — Subjective:** What the client reported, in their own words.
- **O — Objective:** Observable, measurable facts (attendance, affect, behaviors).
- **A — Assessment:** Practitioner's interpretation and clinical impression.
- **P — Plan:** Next steps, referrals, follow-up timeline.

### DAP (simpler, common in community settings)
- **D — Data:** Factual account of the contact (who, what, when, where).
- **A — Assessment:** Professional judgment on client status and needs.
- **P — Plan:** Actions, referrals, next contact.

## Workflow Steps

1. **Determine format:** SOAP for clinical settings; DAP for community/non-clinical.
2. **Ingest raw notes** from the practitioner (voice notes, bullet points, etc.).
3. **Restructure** into the chosen format.
4. **Privacy check:** Remove or anonymise identifying information not required for the note.
5. **Tone check:** Professional, non-judgmental, behaviorally descriptive language.
6. **Present** for practitioner review and sign-off before filing.

## Privacy Rules

- Never include full names in example outputs — use initials or role descriptors.
- Do not retain client information between sessions.
- Flag any content that may breach confidentiality obligations.

## Inputs

- Raw practitioner notes (any format)
- Contact type (in-person, phone, home visit, group)
- Format preference: SOAP or DAP

## Outputs

- Structured case note in chosen format
- Privacy flags for any content that should be reviewed
- Optional: Obsidian note for practitioner's own records (never for formal case files)

## Failure Modes

- **Notes are too sparse to complete all sections** — fill what is possible; clearly mark gaps as [TO COMPLETE].
- **Content contains potential mandatory reporting triggers** — flag immediately; do not proceed without practitioner review.

## Companion Skills

- `social-impact-lens` — systemic context for the practice setting
- `obsidian-vault-manager` — store practitioner’s personal notes in vault
