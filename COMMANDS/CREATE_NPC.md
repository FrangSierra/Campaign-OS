# Create NPC

## Purpose

Create a grounded, deeply usable NPC through an optional guided conversation. This command designs a future-facing working proposal; it does not create a canonical Entity.

## Inputs

- `campaign_ref`;
- optional `plan_ref`;
- a scene need, role, faction, location, or relationship to the party;
- any answers the user wants to provide about attitude, voice, age, ancestry, appearance, goals, secrets, or recurrence.

The user may skip any question or leave the entire design to the operator.

## Outputs

- a design packet with confirmed anchors, proposed details, and flexible table-facing notes;
- duplicate and overlap checks against existing NPCs, factions, places, and relationships;
- optional introduction beats, hooks, or future-pressure ideas, clearly labelled as non-canonical prep;
- an optional Working Record update when the user explicitly asks to keep the NPC.

## Dependencies

- [AI_RUNTIME.md](../SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](../SYSTEM/INVARIANTS.md)
- [TASKS/CREATE_NPC.md](../TASKS/CREATE_NPC.md)
- [npc-creator](../SYSTEM/SKILLS/npc-creator/SKILL.md)
- [entity-extractor](../SYSTEM/SKILLS/entity-extractor/SKILL.md) for candidate and duplicate-check logic

## Approval

- Read-only design and interview work requires no additional approval.
- Persisting the result in `WORKING/` requires an explicit request.
- Canonical Entity, Relationship, or Event changes require the normal approval path.

## Constraints

- Ask only useful follow-up questions, one small group at a time.
- State clearly that every unanswered field may be skipped or delegated.
- Keep user-confirmed anchors distinct from operator proposals.
- Treat hooks and introduction beats as prep, not as events that have happened.
- Do not give the NPC knowledge, history, or relationships that the campaign context does not support.
