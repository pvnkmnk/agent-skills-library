---
name: write-prd-from-conversation
description: Turns a freeform conversation, transcript, or discussion thread into a structured Product Requirements Document (PRD) with goals, user stories, and acceptance criteria.
category: meta
tags: [meta, prd, planning, product, documentation]
agents: [opencode, freebuff, antigravity, codex]
---

# write-prd-from-conversation

## Purpose

Transforms unstructured conversations — chat threads, voice transcripts, brainstorm notes — into a formatted PRD with clear goals, scope, user stories, acceptance criteria, and open questions.

## Invocation

**OpenCode / Codex:** `Invoke write-prd-from-conversation`
**Freebuff:** `/skill write-prd-from-conversation`

## PRD Output Structure

```markdown
# PRD: <feature/project name>
Date: YYYY-MM-DD
Author: <from conversation context>

## Problem Statement
<what problem this solves>

## Goals
- <goal 1>
- <goal 2>

## Non-Goals
- <explicitly out of scope>

## User Stories
- As a <persona>, I want <action> so that <outcome>.

## Acceptance Criteria
- [ ] <criterion 1>
- [ ] <criterion 2>

## Open Questions
- <unresolved decision 1>

## References
- <relevant links or prior art>
```

## Workflow Steps

1. **Ingest** the conversation or notes.
2. **Extract** goals, constraints, and decisions made.
3. **Identify** personas and user stories implied by the discussion.
4. **Draft** the PRD using the structure above.
5. **Flag** open questions and unresolved decisions.
6. **Present** for user review and sign-off.

## Inputs

- Conversation transcript, chat export, brainstorm notes, or voice transcript
- Optional: existing feature spec or prior PRD to extend

## Outputs

- Complete PRD in Markdown (ready to copy into Obsidian or a GitHub issue)
- List of open questions requiring resolution

## Failure Modes

- **Conversation too short to derive full PRD** — fill what is knowable and leave gaps as explicit open questions.
- **Conflicting requirements in conversation** — surface the conflict; do not silently pick a side.

## Companion Skills

- `grill-me` — stress-test the PRD before it is handed to engineering
- `prd-to-kanban-issues` — decompose the PRD into work tickets
