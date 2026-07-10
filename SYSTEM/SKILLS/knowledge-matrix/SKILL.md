---
name: knowledge-matrix
description: Use when the user wants a structured answer to who knows what about a mystery, event, clue, NPC, or secret inside Campaign OS. This skill maps knowledge by actor layer, confidence, and source so intrigue-heavy play can stay legible without flattening uncertainty.
---

# Knowledge Matrix

This skill builds a disciplined knowledge map across public belief, party knowledge, NPC knowledge, and GM-only or prep-only layers. It is for separation and comparison, not for inventing hidden certainty.

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
   - `STATE/known-npcs.md`
   - `STATE/recent-session.md`
   - touched `CANON/events/`, `CANON/entities/`, and `CANON/relationships/`
   - relevant `WORKING/session-plans/`
   - relevant `campaign-qa`, `session-prep`, and `mystery-manager` outputs when the matrix is prep-facing

Do not load extra campaign scope unless the knowledge question truly requires it.

## Purpose

This skill is strongest when the user asks for:

- "Who knows what about this clue or event?"
- secrecy-boundary checks before a session
- reveal planning for an investigation
- a comparison between public belief, party knowledge, and GM design
- help spotting where a mystery is too easy or too opaque

## Core Responsibilities

- map knowledge claims by actor or actor group
- distinguish direct knowledge, rumor, inference, and hidden truth
- show confidence and provenance for each layer
- surface knowledge leaks, overexposure, and clue bottlenecks
- keep prep-only assumptions from being mistaken for canon

## Modes

Choose the narrowest mode that fits the request.

### Subject Matrix Mode

Use when the user wants a focused answer about one subject or a small cluster of linked subjects.

Produce:

- subjects under review
- actor layers
- what each layer knows, suspects, or believes

### Secrecy Audit Mode

Use when the user mainly wants to protect hidden information.

Look for:

- NPCs who know too much too early
- public summaries that leak branch-only truth
- prep that assumes a reveal has already happened

### Reveal Prep Mode

Use when the user wants to stage future discoveries fairly.

Focus on:

- which clues are already visible
- which truths still need seed support
- where the next reveal can land without collapsing the mystery

## Workflow

1. Identify the subject, clue cluster, or secret boundary the matrix should track.
2. Load only the campaign slices needed for those subjects.
3. Define actor layers before filling in any knowledge claims.
4. For each claim, label it as:
   - known from canon
   - visible in current state
   - planned in prep
   - speculative possibility
5. Distinguish:
   - knows
   - suspects
   - publicly believes
   - should not know yet
6. Surface leaks, mismatches, and overly dense reveal paths.
7. Keep the final matrix readable enough to use during prep or review.

## Output Shape

Prefer sections like:

- scope
- files loaded
- actor layers
- subject matrix
- leak warnings
- next reveal opportunities

## Guardrails

- A matrix is a map of knowledge state, not a source of new truth.
- Do not promote prep-only hidden answers into canon.
- If an NPC's knowledge is unsupported, say it is unsupported rather than smoothing it over.
- Keep public rumor separate from what the party personally witnessed.
- If the matrix includes planned future reveals, label them as prep only.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/knowledge-matrix/fixtures/`
- knowledge matrices live under `TESTS/skills/knowledge-matrix/runs/`

For this campaign, a strong first rehearsal should compare:

- the collapsed-branch memory boundary
- the Time Agency truth
- the visible Oren Vestrel case setup
- Brann and Ivy's approved planning roles without overstating what they know
