# Suggest NPC

## Purpose

User-facing entry point for generating grounded NPC options from the current world, location, mystery, faction, or session-plan need.

## Inputs

- `campaign_ref`
- optional `plan_ref`
- a role, problem, location, faction, or scene need
- optional tone, age range, social class, or recurrence goal

## Outputs

- one or more NPC suggestions
- links to the campaign context that make each NPC fit
- optional Working Record updates if the human wants the NPC added to a session plan

## Dependencies

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [TASKS/SUGGEST_NPC.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/SUGGEST_NPC.md)

## Files Read

- relevant `STATE/` records
- relevant `CANON/entities/`
- relevant `CANON/relationships/`
- relevant `STATE/known-locations.md`, `STATE/known-organizations.md`, and `STATE/known-mysteries.md`
- optional active session-planning Working Record

## Files Written

- none by default
- optional Working Record update when explicitly requested

## Approval

- Read-only NPC suggestion does not require approval.
- Persisting NPC suggestions into a Working Record may proceed when explicitly requested.
- NPC suggestions do not create canon Entities by themselves.

## Constraints

- Suggested NPCs must be grounded in the current world and campaign tone.
- Suggestions should state why the NPC exists in the scene and what pressure they add.
- Suggestions should avoid duplicating an existing NPC unless deliberate.
- Future-facing NPC ideas remain speculative until used in play and processed through the Truth Pipeline.

## Failure

- NPC suggestion ignores campaign context
- suggestion duplicates an existing NPC without intent
- speculative NPC is treated as canon
