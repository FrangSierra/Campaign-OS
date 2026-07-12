# Suggest NPC

## Purpose

Provide a fast, read-only NPC concept when the user needs someone for a location, faction, mystery, or immediate scene. Use this as the lightweight entry point to [CREATE_NPC.md](CREATE_NPC.md).

## Inputs

- `campaign_ref`;
- optional `plan_ref`;
- a role, problem, location, faction, or scene need;
- optional tone, age range, social class, or recurrence goal.

## Outputs

- one or more grounded NPC concepts;
- the campaign context that makes each option fit;
- a recommendation to reuse an existing NPC when that is stronger;
- a handoff to `npc-creator` when the user wants to define personality, voice, relationships, appearance, or hooks in depth.

## Approval

- Read-only NPC suggestion does not require approval.
- Persisting an option into a Working Record requires an explicit request.
- Suggestions do not create canon Entities, Relationships, or Events.

## Constraints

- Keep suggestions brief, scene-focused, and grounded in current campaign context.
- Do not turn a quick concept into a full biography unless the user asks to continue with `npc-creator`.
- Future-facing NPC ideas remain speculative until used in play and later processed through the Truth Pipeline.
