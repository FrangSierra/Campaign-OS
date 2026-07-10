---
name: campaign-qa
description: Use when the user wants a read-only quality pass over a Campaign OS campaign, session block, mystery cluster, NPC knowledge boundary, or prep packet. This skill checks for contradictions, repeated clues, unresolved mystery pressure, NPC knowledge leaks, and dangling plot threads without changing canon.
---

# Campaign QA

This skill performs read-only campaign analysis across canon, derived state, and working material. It is for finding risks, not for silently fixing them.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
4. `CAMPAIGNS/<campaign-id>/CAMPAIGN_STATUS.md`
5. the smallest relevant subset of:
   - `STATE/`
   - touched `CANON/sessions/`, `CANON/events/`, `CANON/entities/`, `CANON/relationships/`
   - relevant `WORKING/`
   - `REFERENCE/` or `RULES/` only if they affect the specific QA question

Do not load the whole campaign unless the QA request is explicitly broad.

## Purpose

This skill is strongest when the user asks questions like:

- "What contradictions are forming?"
- "What mysteries are still alive?"
- "What should NPCs not know yet?"
- "What plot threads are dangling?"
- "Give me a campaign health pass before prep."

## Core Responsibilities

- contradiction detection
- repeated clue detection
- unresolved mystery warnings
- NPC knowledge-boundary warnings
- dangling plot-thread warnings

Optional lightweight modes that still remain read-only:

- digest
- health snapshot
- prep-risk scan

## Modes

Choose the narrowest mode that matches the request.

### Contradiction Scan

Use when continuity or state alignment is the main concern.

Look for:

- state summaries that overclaim beyond canon
- entity or relationship status that no longer matches approved events
- session-level facts incorrectly promoted to durable truth
- prep-only material accidentally treated as played fact

### Mystery and Thread Scan

Use when the campaign needs narrative pressure management.

Look for:

- open mysteries with no recent traction
- multiple clues pointing at the same answer too loudly
- mysteries that were resolved in practice but still appear open in state
- threads likely to be forgotten if not surfaced during the next prep cycle

### Knowledge-Boundary Scan

Use when intrigue or secrecy matters.

Look for:

- NPCs appearing to know facts they should not know yet
- public-world summaries that accidentally preserve branch-only knowledge
- prep documents assigning certainty where canon only supports rumor

### Prep-Risk Scan

Use when reviewing a session plan against current canon and state.

Look for:

- prep that contradicts approved state
- hooks that over-centralize too many mysteries
- new recurring NPCs being asked to do too much too early
- any pressure that would pull the campaign away from the intended tone

## Workflow

1. Identify the QA question and choose the smallest fitting mode.
2. Load only the campaign slices relevant to that question.
3. Separate canon, derived state, and working prep before comparing them.
4. Produce findings, if any, ordered by severity.
5. If no direct contradictions are present, say so clearly.
6. Surface warnings and follow-up checks separately from hard contradictions.
7. Do not mutate files unless the user explicitly asks for follow-up fixes in a later step.

## Output Shape

Prefer this structure:

- scope
- files loaded
- contradictions
- warnings
- watch list
- suggested next checks

If there are no contradictions, say that explicitly before listing softer concerns.

## Guardrails

- QA findings are not canon changes.
- Do not rewrite records while auditing.
- Distinguish hard contradiction from soft risk.
- If a fact exists only in `WORKING/`, report it as planned or speculative, never established truth.
- Approved future-facing entities may exist canonically before first scene appearance, but unplayed scene details still remain unconfirmed.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/campaign-qa/fixtures/`
- reports live under `TESTS/skills/campaign-qa/runs/`

A good first QA pass on this repo should usually inspect:

- `CAMPAIGN_STATUS.md`
- `STATE/current-world.md`
- `STATE/current-party.md`
- `STATE/known-mysteries.md`
- `STATE/known-npcs.md`
- `STATE/timeline.md`

Expand into `WORKING/` only when the QA question touches upcoming prep or unresolved continuity reasoning.
