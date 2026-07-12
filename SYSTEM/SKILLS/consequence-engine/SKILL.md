---
name: consequence-engine
description: Use when the user wants to track delayed fallout, decision pressure, and trigger windows inside Campaign OS without prematurely turning future possibilities into canon. This skill organizes possible consequences from approved events, current prep, and unresolved mysteries so prep can decide what should fire next.
---

# Consequence Engine

This skill helps the operator manage campaign fallout over time. It is for plausible future pressure, not for retroactively declaring what already happened off-screen.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
4. `CAMPAIGNS/<campaign-id>/CAMPAIGN_STATUS.md`
5. the smallest relevant subset of:
   - `STATE/current-world.md`
   - `STATE/current-party.md`
   - `STATE/known-mysteries.md`
   - `STATE/recent-session.md`
   - `STATE/timeline.md`
   - touched `CANON/events/`, `CANON/entities/`, and `CANON/relationships/`
   - relevant `WORKING/session-plans/`
   - relevant `campaign-qa`, `session-prep`, or `mystery-manager` outputs when they shape likely fallout

Do not load the whole campaign unless the consequence question truly spans it.

## Purpose

This skill is strongest when the user asks for:

- a delayed-fallout register after a session
- a "what might come due next?" pass before prep
- trigger windows for consequences that should not fire immediately
- pressure tracking across mysteries, NPCs, and institutions
- help deciding whether a consequence should stay dormant, surface now, or be postponed

## Core Responsibilities

- track important decisions and unresolved fallout
- propose future consequence candidates without canonizing them
- assign likely trigger windows and pressure levels
- separate guaranteed aftereffects from plausible but optional ones
- prompt prep to ask whether a consequence should fire now

## Modes

Choose the narrowest mode that fits the request.

### Register Mode

Use when the user wants a fresh consequence list after a session or major event.

Produce:

- consequence candidates
- source events or decisions
- likely affected actors
- near-, mid-, or long-window timing
- trigger suggestions

### Prep Window Mode

Use when the user is planning the next session and wants to know which consequences are most ready to surface.

Focus on:

- what is already under pressure
- what would feel fair now
- what should stay dormant for later

### Fallout Audit Mode

Use when the user wants to check whether the campaign is dropping too many consequences or firing them too quickly.

Look for:

- dangling important fallout
- repeated pressure on the same mystery
- consequences that would over-centralize the plot
- soft consequences that deserve a smaller payoff before a major reveal

## Workflow

1. Identify the source event block, prep packet, or mystery cluster that created the consequence question.
2. Load only the supporting canon, state, and prep slices needed for that fallout.
3. Separate approved consequences already established in canon from future-facing consequence candidates.
4. For each candidate, note:
   - source
   - affected actors
   - what changes if it surfaces
   - likely timing window
   - what trigger would make it feel earned
5. Mark whether each consequence is:
   - already canonical
   - strongly implied future pressure
   - optional prep lever
   - speculative stretch
6. Surface over-centralization, repetition, or tone-risk warnings.
7. If the user wants to persist the result, keep it in `WORKING/` unless explicit canon authority exists.

## Output Shape

Prefer sections like:

- scope
- files loaded
- confirmed fallout already in canon
- candidate consequences
- trigger windows
- hold-for-later list
- prep questions

## Guardrails

- A future consequence is not canon until play or explicit approval establishes it.
- Do not rewrite established events to make a later payoff cleaner.
- Distinguish "must eventually matter" from "could become useful later."
- Keep one mystery or faction from swallowing every consequence lane unless the user explicitly wants that structure.
- If a consequence depends on unresolved canon, label it as contingent.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/consequence-engine/fixtures/`
- fallout registers and prep-window reports live under `TESTS/skills/consequence-engine/runs/`

Use anonymized fixtures that include one confirmed event, several possible consequences, and a future prep question.
