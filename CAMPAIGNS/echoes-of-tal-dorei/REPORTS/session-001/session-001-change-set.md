# Session 1 Approved Change Set

## Scope

This change set was generated from Session 1 artifacts and approved on 2026-07-10 with targeted reductions to long-term canonical clutter.

## Approved Event Activations

- `event-session-001-caravan-departure`
- `event-session-001-road-anomalies`
- `event-session-001-fog-discontinuity`
- `event-session-001-false-emon-arrival`

## Rejected One-Scene Entity Creations

- `entity-garrick-thornwall`
  - kind: `npc`
  - primary name: `Garrick Thornwall`
  - proposed notes: caravan master; initially praised Emon and referred to Mira and Finn as central to his better life; after the fog he denied ever having had them.
- `entity-mira`
  - kind: `npc`
  - primary name: `Mira`
  - proposed notes: caravan companion present before the fog and absent afterward.
- `entity-finn`
  - kind: `npc`
  - primary name: `Finn`
  - proposed notes: caravan companion present before the fog and absent afterward.
- `entity-elira-voss`
  - kind: `npc`
  - primary name: `Elira Voss`
  - proposed notes: elderly traveler who remembered some events differently and later disappeared, leaving a key behind.

## Applied Entity Updates

- `entity-sadek`
  - add supportable note that he is a dwarf hunter travelling with Perry and that he remarked that nature felt wrong.
- `entity-perry-the-parrot`
  - add supportable note that Perry is Sadek's talking parrot and made odd comments that hinted at the discontinuity.
- `entity-helmut`
  - add session-start identity notes from the supplied summary only after approval.
- `entity-soren`
  - add session-start identity notes from the supplied summary only after approval.
- `entity-kallista`
  - add session-start identity notes from the supplied summary only after approval.
- `entity-phirina`
  - add session-start identity notes from the supplied summary only after approval.

## Applied Relationship Updates

- create `relationship-sadek-companion-of-perry`
  - subject: `entity-sadek`
  - predicate: `companion_of`
  - object: `entity-perry-the-parrot`
  - status: `active`
- no Garrick, Mira, or Finn family relationship was created because those one-scene NPCs were intentionally not retained as standalone Entities.

## Current Asset Linkage

- Detected current player sheet PDFs:
  - `ASSETS/pdf/player-character-sheets/helmut.pdf`
  - `ASSETS/pdf/player-character-sheets/kallista.pdf`
  - `ASSETS/pdf/player-character-sheets/phirina.pdf`
  - `ASSETS/pdf/player-character-sheets/soren.pdf`
- These sheets appear to reflect post-Session-3 level state and were therefore not used to infer Session 1 canonical facts.
- The asset links have now been attached separately to the player records and do not change Session 1 canon.

## Outcome

- All four Session 1 Events were approved and activated.
- Sadek, Perry, and the four player-character records were updated.
- The Sadek/Perry companion relationship was created.
- Garrick Thornwall, Mira, Finn, and Elira Voss were intentionally left out of the long-term Entity roster.
