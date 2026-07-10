# Candidate Entity Packet

## Scope

- campaign: `campaign-echoes-of-tal-dorei`
- mode: `session extraction`
- fixture: `TESTS/skills/entity-extractor/fixtures/session-006-candidate-entity-extraction.md`
- source anchor: [session-006-first-true-emon-simulated-notes.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TESTS/skills/process-session/fixtures/session-006-first-true-emon-simulated-notes.md)
- write scope: read-only rehearsal output

## Files Loaded

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/PROCESS_SESSION.md)
- [PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/WORKFLOWS/PROCESS_SESSION.md)
- [CAMPAIGN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CAMPAIGN.md)
- [known-npcs.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-npcs.md)
- [known-locations.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-locations.md)
- [known-organizations.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-organizations.md)
- [brann-copperthumb.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CANON/entities/npcs/brann-copperthumb.md)
- [ivy.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CANON/entities/npcs/ivy.md)
- [plan-session-006-first-true-emon.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/WORKING/session-plans/plan-session-006-first-true-emon.md)
- [session-006-first-true-emon-simulated-notes.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TESTS/skills/process-session/fixtures/session-006-first-true-emon-simulated-notes.md)

## Existing Records Checked

- Brann Copperthumb already exists as an approved future-facing NPC entity.
- Ivy already exists as an approved future-facing NPC entity.
- The true city of Emon already exists at derived-state level in `known-locations.md`, even though no standalone location record exists yet.
- The Time Agency already exists as an organization concept in current campaign state.

## Candidate Entities

### Strong Session-Level Candidates

- `Oren Vestrel`
  - candidate type: `npc`
  - supported facts:
    - Lyceum-connected scholar
    - associated with old civic survey records and sealed tunnels under Emon
    - found dead in a staged scene in the simulated session
  - evidence hook: direct mention throughout the Session 6 simulated notes
  - duplication risk: low in loaded scope
  - recommended scope: `session-scoped now, possible later entity if recurrence or wider relevance is confirmed`

- `Inspector Mara Thessel`
  - candidate type: `npc`
  - supported facts:
    - City Watch inspector
    - respects Brann's reputation enough to seek his help
    - practical enough to involve the party informally
  - evidence hook: direct appearance in the simulated notes and Session 6 plan
  - duplication risk: low in loaded scope
  - recommended scope: `session-scoped now, possible recurring civic contact later`

### Location Or Place-Anchor Candidates

- `Oren Vestrel's rented study`
  - candidate type: `location`
  - supported facts:
    - townhouse study used as the scholar-death scene
    - contains staging evidence and a hidden service hatch
  - evidence hook: direct scene description in the simulated notes
  - duplication risk: low
  - recommended scope: `session location only unless the investigation returns repeatedly`

- `Old service passage beneath the study`
  - candidate type: `location`
  - supported facts:
    - narrow stone passage older than the townhouse
    - contains constructs, boot prints, and survey clues
  - evidence hook: direct scene description in the simulated notes
  - duplication risk: medium with broader "under-Emon tunnels" concepts
  - recommended scope: `working or session-scoped until the undercity network is better defined`

### Lower-Priority Candidates

- `Maintenance constructs`
  - candidate type: `entity group or encounter note`
  - supported facts:
    - dormant constructs awaken when the route marker is touched
  - recommended scope: `do not promote beyond session artifact unless they recur`

- `South maintenance survey`
  - candidate type: `clue object or document`
  - supported facts:
    - phrase survives on a burned note
  - recommended scope: `keep as clue text inside session or working notes, not a standalone record`

## Candidate Relationships

- `Sadek -> Brann Copperthumb`
  - supported fact: older-cousin connection appears in approved Brann planning context and the simulated session
  - duplication risk: none
  - recommended scope: `safe future relationship candidate after live play shows it on-screen`

- `Mara Thessel -> Brann Copperthumb`
  - supported fact: professional respect and help-seeking
  - recommended scope: `session-scoped until recurrence proves durability`

- `Party -> Oren Vestrel case`
  - supported fact: the party is redirected toward the scholar investigation
  - recommended scope: `session event linkage, not a standalone relationship record`

## Keep-Session-Scoped List

- Oren Vestrel, until the case confirms broader campaign relevance
- Inspector Mara Thessel, unless she becomes a repeat Watch bridge
- the rented study
- the hidden passage
- the maintenance constructs

## Promotion Recommendations

- Do not create new entity files from this rehearsal output alone.
- If live Session 6 confirms recurrence, Oren and Mara are the strongest candidates for later persistent records.
- The hidden passage is better handled first as event and session truth, then possibly as a broader location concept if the under-Emon network becomes a lasting campaign layer.
- The Brann and Ivy records already cover the stable facts needed here; no duplicate promotion is warranted.

## Outcome

The extraction pass stays conservative in the right way: it recognizes meaningful new nouns, avoids duplicating approved entities, and recommends that nearly everything remain session-scoped until real play proves it deserves durable record weight.
