# Entity Extractor Fixture

## Status

Non-canonical test fixture for Skill rehearsal only.

## Purpose

This fixture tests whether `entity-extractor` can:

- read simulated Session 6 notes and separate existing entities from new candidates
- avoid duplicating Brann Copperthumb and Ivy, who are already approved entities
- identify which new names should stay session-scoped for now
- propose stable facts without inventing motives or future relevance

## Prompt

Use the Session 6 simulated notes to produce a conservative candidate-entity packet.

The packet should answer:

- which named people, places, or object-like anchors deserve attention
- which ones already exist in canon or derived state
- which ones should remain session-scoped until later play proves recurrence

## Expected Boundary

- read-only rehearsal output only
- no new canonical records
- no relationship or entity treated as approved truth beyond what the loaded files already support
