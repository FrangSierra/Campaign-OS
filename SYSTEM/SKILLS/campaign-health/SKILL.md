---
name: campaign-health
description: Use when the user wants a read-only synthetic assessment of campaign momentum, pressure balance, recurring cast strength, mystery load, and prep readiness inside Campaign OS. This skill summarizes health signals without changing canon or replacing detailed QA.
---

# Campaign Health

This skill is a broad read-only health snapshot for the campaign. It complements `campaign-qa` by asking whether the campaign is balanced, legible, and sustainable, not just whether it is internally consistent.

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
   - `STATE/known-locations.md`
   - `STATE/timeline.md`
   - `STATE/recent-session.md`
   - relevant `WORKING/session-plans/`
   - recent `campaign-qa`, `session-prep`, `mystery-manager`, or `consequence-engine` outputs when they inform current pressure

Do not load full canon unless the health question explicitly demands it.

## Purpose

This skill is strongest when the user asks for:

- a campaign health snapshot between arcs or sessions
- a check on whether mysteries, NPCs, and consequences are balanced
- a prep-readiness summary
- a "what is thriving and what is drifting?" pass
- early detection of over-centralization or neglected threads

## Core Responsibilities

- summarize campaign strengths and stress points
- assess mystery load, recurring cast depth, and setting attachment
- identify stale or under-supported pressure lanes
- highlight whether upcoming prep is carrying too much or too little
- give actionable watch points without mutating records

## Modes

Choose the narrowest mode that fits the request.

### Snapshot Mode

Use for a general campaign health reading.

Produce:

- current strengths
- current stress points
- watch list
- next useful maintenance actions

### Prep Readiness Mode

Use when the user mainly wants to know whether the next session is set up well.

Focus on:

- clarity of hooks
- cast support
- continuity pressure
- tone balance

### Arc Load Mode

Use when the user wants to know whether major mysteries, villains, or themes are overloading the campaign.

Look for:

- too many active central questions
- one mystery swallowing other play lanes
- recurring NPC bench that is too thin
- weak bridge between big lore and human-scale scenes

## Workflow

1. Identify whether the health question is broad, prep-facing, or arc-specific.
2. Load only the state and recent reports needed for that health lens.
3. Separate hard QA findings from softer health signals.
4. Assess:
   - mystery pressure
   - recurring cast depth
   - setting attachment
   - consequence pacing
   - prep readiness
5. Report strengths before warnings so the current campaign shape stays visible.
6. Keep maintenance advice read-only unless the user explicitly asks for follow-up changes.

## Output Shape

Prefer sections like:

- scope
- files loaded
- health status
- strengths
- stress points
- watch list
- next maintenance checks

## Guardrails

- Health assessment is operational, not canonical.
- Do not turn a soft concern into a false contradiction.
- Avoid generic advice divorced from loaded campaign context.
- If a weak signal depends on prep-only material, label it clearly as prep-facing.
- Preserve the difference between "not yet developed" and "broken."

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/campaign-health/fixtures/`
- health snapshots live under `TESTS/skills/campaign-health/runs/`

For this campaign, a strong first rehearsal should inspect the transition from Session 5 into Session 6 because it tests:

- post-prologue reset stability
- recurring NPC bench growth
- whether Emon is ready to carry grounded play
- whether Time Agency and Arven pressure are being kept in proportion
