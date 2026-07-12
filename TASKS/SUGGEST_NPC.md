# Suggest NPC

## Purpose

Generate fast, grounded NPC concepts for an immediate campaign need without opening the full character-design flow.

## Procedure

1. Load only the context needed to understand the scene, faction, location, and existing NPC roster.
2. Offer a small number of distinct options or recommend an existing NPC to reuse.
3. State each concept's scene role, pressure, and reason it fits the campaign.
4. If the user wants personality, voice, party ties, appearance, age, ancestry, or introduction hooks in depth, hand off to `CREATE_NPC` and `npc-creator`.
5. Keep every suggestion non-canonical unless the user explicitly asks to save it in `WORKING/`.

## Failure

- generic concepts disconnected from campaign context;
- duplication without a deliberate reason;
- detailed invented biography presented as established truth.
