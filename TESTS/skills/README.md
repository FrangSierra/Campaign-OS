# Skill Test Plan

This folder is the safe harness for developing and reviewing Campaign OS Skills before we trust them with broader live use.

## Purpose

- test Skills against synthetic, anonymized, or deliberately shared material
- rehearse fake roleplays, synthetic session chats, and alternative outcomes
- keep non-canonical experiments out of `CANON/` and `STATE/`
- leave reviewable artifacts that can be compared across iterations

## Boundaries

- `TESTS/` is operating-system support space, not campaign truth
- test fixtures must not include private campaign entities, events, or state unless the repository is intentionally private
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

## Privacy Default

The public repository tracks this guide but ignores files placed in individual `fixtures/` and `runs/` directories. Keep private rehearsal material there locally. If you want to publish an example, anonymize it first and add it intentionally.

## Review Standard

Each test run should make it easy to answer:

- Did the Skill load the right context and avoid the wrong context?
- Did it preserve the line between evidence, interpretation, and canon?
- Did it use current campaign NPCs and mysteries in a believable way?
- Did it stop at the approval boundary?
- Would we trust the same Skill on a real future session?
