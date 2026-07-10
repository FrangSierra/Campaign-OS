# Skill Test Plan

This folder is the safe harness for developing and reviewing Campaign OS Skills before we trust them with broader live use.

## Purpose

- test Skills against the real `echoes-of-tal-dorei` corpus
- rehearse fake roleplays, synthetic session chats, and alternative outcomes
- keep non-canonical experiments out of `CANON/` and `STATE/`
- leave reviewable artifacts that can be compared across iterations

## Boundaries

- `TESTS/` is operating-system support space, not campaign truth
- test fixtures may reference real campaign entities, events, and state
- test outputs must clearly label what is copied from approved canon and what is simulated
- no skill test should write to `CANON/` or `STATE/` unless a later live run is explicitly approved

## Folder Shape

- `SYSTEM/SKILLS/`: repo-owned draft Skills before any optional global installation
- `TESTS/skills/<skill-name>/fixtures/`: fake prompts, simulated inputs, or scope briefs
- `TESTS/skills/<skill-name>/runs/`: dry-run outputs and review packets

As more Skills are added, give each one the same `fixtures/` and `runs/` pattern.

## Test Ladder

1. `Smoke`
   Confirm the Skill loads the right repo docs, campaign scope, and approval boundary.
2. `Rehearsal`
   Run the Skill against a fake roleplay, simulated session, or operator-authored chat without touching canon.
3. `Corpus Check`
   Compare the Skill's reasoning against existing campaign records, state views, and approved NPCs.
4. `Review Gate`
   Leave a result packet with concrete questions for human review before expanding the Skill.
5. `Live Pilot`
   Only after review, use the Skill on real new inputs with the normal approval pauses intact.

## Current Roadmap Coverage

- `process-session`: implemented with one simulated Session 6 dry run using Brann, Ivy, and current Emon context
- `campaign-qa`: implemented with one post-Session-5 prep-risk scan against the current campaign
- `session-prep`: implemented with one Session 6 prep-packet rehearsal grounded in current state and QA guardrails
- `mystery-manager`: implemented with one Session 6 scholar-case mystery-board rehearsal
- `consequence-engine`: implemented with one post-Session-5 fallout register and Session 6 prep-window rehearsal
- `entity-extractor`: implemented with one Session 6 candidate-entity extraction rehearsal from simulated session notes
- `knowledge-matrix`: implemented with one Session 6 knowledge-boundary rehearsal for branch memory and the scholar case

## Review Standard

Each test run should make it easy to answer:

- Did the Skill load the right context and avoid the wrong context?
- Did it preserve the line between evidence, interpretation, and canon?
- Did it use current campaign NPCs and mysteries in a believable way?
- Did it stop at the approval boundary?
- Would we trust the same Skill on a real future session?
