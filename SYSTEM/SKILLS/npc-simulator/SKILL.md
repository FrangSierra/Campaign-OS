---
name: npc-simulator
description: Use when the user wants a bounded rehearsal of how an established NPC might respond, react, or move under current campaign conditions without turning speculative behavior into canon. This skill models likely choices from supported goals, knowledge, fears, resources, and relationships.
---

# NPC Simulator

This skill offers constrained NPC rehearsal. It is useful for pressure-testing scenes, but it must never pretend that simulated dialogue or motivation is established truth.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
4. the smallest relevant subset of:
   - touched NPC entity files in `CANON/entities/`
   - relevant `CANON/relationships/` and `CANON/events/`
   - `STATE/current-world.md`
   - `STATE/current-party.md`
   - `STATE/known-npcs.md`
   - relevant `WORKING/session-plans/`
   - relevant `campaign-qa`, `knowledge-matrix`, `mystery-manager`, or `session-prep` outputs when they constrain the scene

Do not load broader canon unless the simulated question truly requires it.

## Purpose

This skill is strongest when the user asks for:

- likely NPC reactions to a current scene or reveal
- a safe rehearsal of how an NPC might handle a clue, lie, or request
- off-screen movement guesses before prep
- bounded dialogue or posture samples grounded in existing records

## Core Responsibilities

- derive likely behavior from supported facts only
- separate stable anchors from live inference
- distinguish what an NPC knows from what the operator wants them to reveal
- provide useful rehearsal without locking in hidden truth
- flag where the source context is too thin for confident simulation

## Modes

Choose the narrowest mode that fits the request.

### Response Probe Mode

Use when the user wants to know how an NPC would likely react in a specific interaction.

Produce:

- stable anchors
- likely priorities
- likely first response
- what they would probably withhold

### Off-Screen Motion Mode

Use when the user wants a bounded guess about what an NPC may do between scenes.

Focus on:

- goals
- resources
- constraints
- plausible next moves

### Social Pressure Rehearsal Mode

Use when the user wants to test secrecy, persuasion, fear, or trust pressure.

Look for:

- what would earn trust
- what would shut the NPC down
- what questions they might ask back

## Workflow

1. Identify the NPC, the scene question, and the narrowest fitting mode.
2. Load only the entity, relationship, state, and prep slices that constrain behavior.
3. Extract stable anchors:
   - known role
   - supported relationships
   - approved knowledge
   - resources or limits
4. State where inference begins.
5. Offer likely behaviors as bounded ranges, not certainties.
6. If the loaded context is too thin, say so and stay high level.
7. Mark the output as rehearsal only unless live play later confirms it.

## Output Shape

Prefer sections like:

- scope
- files loaded
- stable anchors
- likely priorities
- likely response profile
- likely withholdings
- simulation limits

## Guardrails

- Simulated behavior is not canon.
- Do not invent deep psychology that the loaded files do not support.
- Do not give an NPC hidden knowledge they have not earned.
- If prep says an NPC exists before first appearance, keep the simulation light and role-focused.
- Prefer "likely," "plausible," and "unsupported" over false certainty.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/npc-simulator/fixtures/`
- simulation packets live under `TESTS/skills/npc-simulator/runs/`

Use anonymized fixtures with an established NPC, a constrained scene, and enough known relationships to reveal whether the simulation drifts beyond the evidence.
