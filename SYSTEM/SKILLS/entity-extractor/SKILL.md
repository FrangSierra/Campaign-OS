---
name: entity-extractor
description: Use when the user wants to identify candidate NPCs, factions, locations, objects, or relationships from evidence, canon, prep, or imported material without automatically promoting them into canonical records. This skill proposes structured candidates, duplicates checks, and scope recommendations.
---

# Entity Extractor

This skill identifies durable campaign nouns that may deserve records later. It is for proposal and triage, not automatic canon creation.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
4. when the source is session evidence, also load:
   - `COMMANDS/PROCESS_SESSION.md`
   - `WORKFLOWS/PROCESS_SESSION.md`
5. the smallest relevant subset of:
   - supplied evidence or source material
   - touched `CANON/entities/`, `CANON/relationships/`, and `CANON/events/`
   - `STATE/known-npcs.md`
   - `STATE/known-locations.md`
   - `STATE/known-organizations.md`
   - relevant `WORKING/` plans or investigations when they explain why an entity candidate matters

Do not load broad canon just to be exhaustive. Load enough to avoid obvious duplication and bad promotion.

## Purpose

This skill is strongest when the user asks for:

- candidate NPCs or locations from session notes
- entity proposals from a PDF, transcript, or lore packet
- a pass on whether something should stay session-scoped
- duplicate checks against existing campaign records
- structured extraction before a later human review

## Core Responsibilities

- identify candidate entities, locations, organizations, objects, and relationships
- separate named mention from durable importance
- check whether a candidate duplicates an existing record
- recommend whether each candidate should remain session-scoped, working-only, or graduate toward canon later
- preserve exact evidence hooks for every suggested candidate

## Modes

Choose the narrowest mode that fits the request.

### Session Extraction Mode

Use when the source is played-session evidence or a rehearsal fixture.

Focus on:

- recurring NPC candidates
- session-only names that should stay local
- durable clue objects or places that may matter later

### Lore Ingest Mode

Use when the source is reference material, setting notes, or imported worldbuilding.

Focus on:

- what belongs in `REFERENCE/`
- what deserves entity proposals
- what is only background color

### Prep Cast Mode

Use when the source is a plan and the user wants proposed supporting cast.

Focus on:

- prep-scoped candidates
- why each character or place exists in the plan
- which ideas are too thin to persist yet

## Workflow

1. Identify the source material and whether it is canon, evidence, prep, or reference.
2. Load only the existing entity and state slices needed to avoid duplicate proposals.
3. List every meaningful candidate noun, then trim away mentions that are not durable enough to matter.
4. For each remaining candidate, capture:
   - candidate type
   - source evidence
   - stable facts actually supported
   - likely campaign role
   - duplication risk
   - recommended scope
5. Keep uncertain motives, backstory, and interpretation out of the stable-facts line.
6. If the user wants persistence, route proposals into `WORKING/` or a review packet before any canon write.

## Output Shape

Prefer sections like:

- scope
- files loaded
- existing records checked
- candidate entities
- candidate relationships
- keep-session-scoped list
- promotion recommendations

## Guardrails

- Extraction is not canonization.
- One scene does not automatically justify a new persistent record.
- Do not fill missing biography, motive, or allegiance with guesses.
- Prefer a smaller set of strong candidates over a bloated directory of one-scene names.
- If a candidate exists only in prep, label it as prep-scoped or speculative.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/entity-extractor/fixtures/`
- extraction packets live under `TESTS/skills/entity-extractor/runs/`

For this campaign, a strong first rehearsal should use the Session 6 simulated notes because they mix:

- approved future-facing NPCs already known to the campaign
- new session-only names
- a candidate location layer beneath Emon
- clues that matter without yet deserving standalone object records
