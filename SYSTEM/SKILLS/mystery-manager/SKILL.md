---
name: mystery-manager
description: Use when the user wants to structure an investigation-heavy RPG mystery inside Campaign OS, including clue tracking, false-clue handling, hidden-truth separation, unresolved-question management, and player-theory pressure. This skill helps build or audit a mystery board without turning speculative answers into canon.
---

# Mystery Manager

This skill supports investigation-heavy campaign play by organizing mysteries as distinct layers instead of a single blended summary. It is especially useful when clues, rumor, hidden truth, and player interpretation need to stay clearly separated.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
4. the smallest relevant subset of:
   - `STATE/known-mysteries.md`
   - relevant `STATE/` summaries
   - touched `CANON/sessions/`, `CANON/events/`, `CANON/entities/`, `CANON/relationships/`
   - relevant `WORKING/session-plans/`
   - relevant `campaign-qa` and `session-prep` outputs when they shape the investigation

Do not load the whole campaign unless the mystery genuinely spans the whole campaign.

## Purpose

This skill is strongest when the user asks for:

- a mystery board for an upcoming or current investigation
- separation between player-known clues and hidden truth
- a theory ledger
- false-clue or red-herring management
- reveal pacing help
- a "what does the party actually know right now?" pass

## Core Responsibilities

- separate observed clues from interpretation
- separate real hidden truth from possible hidden truth
- separate player-facing pressure from GM-only structure
- prevent one mystery from swallowing unrelated campaign threads too early
- keep mystery answers flexible until play or canon actually supports them

## Modes

Choose the narrowest mode that fits the request.

### Board Mode

Use when the user wants a full mystery structure.

Produce:

- mystery premise
- what is publicly believed
- player-known clues
- false or ambiguous clues
- hidden-truth candidates
- unresolved questions
- reveal guardrails

### Theory Ledger Mode

Use when the user wants to compare likely interpretations.

Track:

- theory
- support
- weakness
- what evidence would confirm or break it

### Reveal Audit Mode

Use when the user wants pacing help.

Look for:

- clues that reveal too much too soon
- bottlenecks where one missed clue breaks the mystery
- NPCs who risk overexplaining
- twists that are unsupported or under-seeded

### Knowledge Snapshot Mode

Use when the user wants to know what the party, public, and GM layers each know.

Keep the layers separate:

- public belief
- party-visible clues
- NPC-held knowledge
- GM-only possibilities

## Workflow

1. Identify the mystery scope and choose a mode.
2. Load only the campaign slices needed for that mystery.
3. Separate canon, state, and prep before building the board.
4. Mark each item as one of:
   - established from canon
   - established from current state
   - planned for prep
   - speculative possibility
5. Keep hidden truth provisional unless the user explicitly wants a designed answer for prep.
6. Surface over-centralization, clue bottlenecks, or premature reveals.
7. Keep the final artifact useful at the table.

## Output Shape

Prefer sections like:

- scope
- mystery premise
- public belief
- player-known clues
- ambiguous or false clues
- hidden-truth candidates
- open questions
- reveal risks
- next best clue paths

## Guardrails

- A mystery board is not canon.
- Do not promote prep-only answers into world truth.
- If a hidden answer is only one design option, label it as such.
- Keep player theory separate from GM intent.
- If `campaign-qa` warns about secrecy boundaries, carry those into the mystery structure.
- If the mystery introduces new NPCs, keep them session-scoped until play proves recurrence.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/mystery-manager/fixtures/`
- mystery boards and audits live under `TESTS/skills/mystery-manager/runs/`

For this campaign, a strong first rehearsal should use the Session 6 scholar case because it already contains:

- a staged-death frame
- city-facing clue channels
- optional NPC contacts
- a clean distinction between visible evidence and deeper hidden causes
