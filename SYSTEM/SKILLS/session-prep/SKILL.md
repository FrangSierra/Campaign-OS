---
name: session-prep
description: Use when the user wants to draft, revise, summarize, or pressure-test a future RPG session inside Campaign OS. This skill turns a planning brief plus current campaign context into a grounded non-canonical prep packet, and it can also produce a lightweight campaign digest for returning to play after a break.
---

# Session Prep

This skill wraps the repository's existing Plan Session command and workflow. It should help the user build a strong future-session packet without turning prep into canon.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `COMMANDS/PLAN_SESSION.md`
4. `WORKFLOWS/PLAN_SESSION.md`
5. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
6. the smallest relevant subset of:
   - `STATE/`
   - touched `CANON/sessions/`, `CANON/events/`, `CANON/entities/`, `CANON/relationships/`
   - relevant `WORKING/session-plans/`
   - relevant continuity or investigation records in `WORKING/`
   - `REFERENCE/` and `RULES/` only when they materially shape the prep
   - recent `campaign-qa` output when available

Do not load the whole campaign unless the prep request is genuinely broad.

## Purpose

This skill is strongest when the user asks for:

- a new session plan from a rough idea
- a revision of an existing plan
- a prep packet for tonight's session
- a "what matters right now?" digest
- continuity-safe spotlight, hook, and pacing guidance

## Core Responsibilities

- open or reuse the right planning scope
- synthesize the current campaign situation
- convert open mysteries into playable pressure without overcommitting answers
- separate required anchors from optional scenes
- surface continuity risks, overload, and tone mismatches
- keep prep flexible enough for live play

## Modes

Choose the narrowest mode that fits the request.

### Draft Mode

Use when the user brings a fresh brief or wants a new plan.

Produce:

- current context synthesis
- core session idea
- candidate hooks
- scene flow
- NPC suggestions when useful
- continuity risks

### Revision Mode

Use when an existing plan should be tightened, simplified, or redirected.

Focus on:

- what changed
- what was cut or postponed
- what warnings need refresh

### Prep Packet Mode

Use when the user wants a table-ready packet from current campaign context and a chosen plan.

Package:

- session purpose
- opening reminders
- spotlight beats
- active hooks
- NPC usage notes
- mystery pressure
- continuity guardrails
- likely end-state options

### Digest Mode

Use when the user wants a short "where are we and what matters now?" summary.

Keep it lightweight:

- current location and situation
- current party condition
- active mysteries
- next likely pressures

## Workflow

1. Identify the planning question and choose a mode.
2. Check whether pending canon approvals would materially change the plan.
3. Load only the campaign slices relevant to the session.
4. Distinguish approved canon, derived state, and working prep before synthesizing.
5. If a recent `campaign-qa` pass exists, use its warnings as guardrails rather than duplicating the whole audit.
6. Build the smallest prep artifact that still helps at the table.
7. Keep future material explicitly non-canonical.
8. If the user wants to keep the plan, route it through the normal commit step rather than implying canon.

## Output Shape

Depending on mode, aim for:

- context synthesis
- session purpose
- hooks
- scene structure
- spotlight notes
- NPC notes
- continuity warnings
- flexible end-state options

For digest mode, compress this into a one-page equivalent.

## Guardrails

- Prep is never canon.
- Use approved canon as baseline and mark speculative ideas clearly.
- Keep Brann-like anchor NPCs from solving the session for the party.
- Do not let one open mystery swallow every city-facing thread unless the user explicitly wants a single-master-conspiracy structure.
- If `campaign-qa` flags knowledge-boundary risks, carry those into prep as explicit guardrails.
- If a useful idea depends on unresolved canon, mark it as contingent.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/session-prep/fixtures/`
- prep packets and digests live under `TESTS/skills/session-prep/runs/`

For this campaign, a strong first packet will usually draw from:

- `STATE/current-world.md`
- `STATE/current-party.md`
- `STATE/known-mysteries.md`
- the latest committed plan in `WORKING/session-plans/`
- the latest relevant `campaign-qa` report
