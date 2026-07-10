# Process Session Rehearsal Report

## Run Summary

- campaign: `campaign-echoes-of-tal-dorei`
- mode: `rehearsal`
- workflow: `process-session`
- fixture: `TESTS/skills/process-session/fixtures/session-006-first-true-emon-simulated-notes.md`
- write scope: `TESTS/skills/process-session/` only
- canon changes applied: `no`
- approval required before live use: `yes`

## Context Loaded

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/PROCESS_SESSION.md)
- [PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/WORKFLOWS/PROCESS_SESSION.md)
- [CAMPAIGN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CAMPAIGN.md)
- [current-world.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/current-world.md)
- [recent-session.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/recent-session.md)
- [known-npcs.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-npcs.md)
- [known-mysteries.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-mysteries.md)
- [brann-copperthumb.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CANON/entities/npcs/brann-copperthumb.md)
- [ivy.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CANON/entities/npcs/ivy.md)
- [plan-session-006-first-true-emon.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/WORKING/session-plans/plan-session-006-first-true-emon.md)

## Context Handling Notes

- The Session 6 plan was used only to confirm Brann and Ivy's approved planning roles and the intended Emon tone.
- No plan-only beat was treated as evidence unless it also appeared in the simulated fixture.
- This run intentionally stops before any Event activation, Entity update, Relationship update, or Derived State refresh.

## Source Record Preview

- proposed id: `source-test-session-006-first-true-emon`
- source kind: `notes`
- source status: `captured`
- captured from: `operator-authored simulated session fixture`
- session hint: `Session 6 - First True Emon`

Handling notes:

- Evidence is secondhand and synthetic, so confidence is suitable for rehearsal only.
- The input clearly separates public rumor, direct scene observation, and Brann's interpretation, which makes it a good Skill test for evidence hygiene.

## Session Preview

- proposed id: `session-test-006-first-true-emon`
- session status: `draft-preview`
- likely participant refs:
  - `entity-helmut`
  - `entity-kallista`
  - `entity-phirina`
  - `entity-soren`
  - `entity-sadek`
  - `entity-perry-the-parrot`
  - `entity-brann-copperthumb`
  - `entity-ivy`

Observation-layer summary:

- The party arrived at the true Emon with Sadek and Perry after the stable-world reset.
- Separate city-facing scenes converged on rumors surrounding Master Archivist Oren Vestrel's death and his research into old survey tunnels.
- Sadek introduced the group to Brann Copperthumb, who redirected a Watch case toward them without taking the field himself.
- Inspector Mara Thessel involved the party informally in the scholar case.
- The study scene contained signs of staging rather than a straightforward locked-room murder.
- A hidden service passage, awakened constructs, fresh boot prints, and Oren's tunnel warning pointed below the city rather than toward a simple household killing.

Unresolved questions:

- Who wanted the death scene to read as a clean murder?
- Was Oren uncovering buried civic infrastructure, archive tampering, or both?
- Who removed the public call for investigators before the party could claim it openly?
- Is Ivy merely observant, or is she already tied into the same rumor network as Brann and the Watch?

## Working Record Preview

- proposed id: `working-test-session-006-archive-and-tunnels`
- reason to open: the fixture presents a stable death but an unstable explanation, plus possible hidden civic tampering beneath Emon

Working focus:

- separate direct scene evidence from city rumor
- test whether the tunnel clue suggests conspiracy, cover-up, or simple hidden infrastructure
- hold any theory about Ivy's network position outside canon
- hold any theory about archive corruption outside canon

## Draft Event Preview

1. `event-test-session-006-true-emon-arrival`
   The party reaches the restored real Emon and begins re-entry into ordinary city life after the prologue.
2. `event-test-session-006-vestrel-rumors-converge`
   Multiple district-facing hooks converge on the reported death of Master Archivist Oren Vestrel and his research into old tunnel records.
3. `event-test-session-006-brann-redirects-the-case`
   Sadek introduces Brann Copperthumb, and Brann plus Inspector Mara Thessel steer the unofficial scholar case toward the party.
4. `event-test-session-006-study-scene-shows-staging`
   The party inspects Oren Vestrel's study and finds evidence that the apparent locked-room murder was carefully staged.
5. `event-test-session-006-hidden-tunnel-trail-opened`
   The party discovers a concealed service passage, defeats awakened maintenance constructs, and uncovers a fresh lead pointing deeper beneath Emon.

## Pending Change-Set Preview

If this had been a live processed session, likely approval questions would include:

- Should Brann's entity record be updated from pre-appearance planning status to first on-screen ally and investigator anchor?
- Should Ivy's entity record gain a first confirmed on-screen contact note with Kallista?
- Should a new relationship record be proposed for Sadek and Brann as explicit cousins, or is that better preserved on entity timelines first?
- Does Oren Vestrel merit a new entity record immediately, or should he remain session-scoped until the case resolves further?

Current rehearsal answer:

- no canon write should be applied yet
- first live use should keep Oren session-scoped unless later evidence makes him recurring
- Brann and Ivy look safe as future entity-update candidates, but only after actual played evidence exists

## Validation Notes

- The Skill correctly stayed within the Truth Pipeline and did not jump from rumor to canon.
- The Skill had enough context to use Brann, Ivy, and current Emon state without loading the full campaign.
- The strongest place to keep uncertainty is the Working Record, not the Event layer.
- The fixture appears good for future regression testing because it mixes civic tone, NPC introduction, investigation setup, and ambiguous evidence.

## Review Questions

- Does Brann's voice and role feel right for his first on-screen use?
- Is Ivy introduced at the right density, or does she need to be even lighter-touch?
- Should the first Emon mystery lean more toward `murder scene with hidden motive` or `staged death hiding civic secrets`?
- When we move from rehearsal to live use, do you want full preview files per artifact or a single review packet like this one?

## Outcome

The first `process-session` rehearsal looks structurally sound. It uses real campaign context, preserves approval boundaries, and leaves a reviewable packet for a human pass before any live session processing.
