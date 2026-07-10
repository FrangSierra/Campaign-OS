# Suggest NPC

## Purpose

Generate one or more grounded NPC options for a location, mystery, faction, or session-plan need.

## Inputs

- `campaign_ref`
- optional `plan_ref`
- desired NPC role or scene function
- optional location, organization, tone, age, recurrence, or pressure to add

## Outputs

- read-only NPC suggestions
- optional updates to the active session-planning Working Record

## Dependencies

- [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md)

## Files Read

- relevant `STATE/` records
- relevant Entity and Relationship records
- relevant open Working Records
- optional active session-planning Working Record

## Files Written

- none by default
- optional update to a session-planning Working Record

## Approval

- none for read-only suggestions
- explicit request required before persisting suggestions into a Working Record

## Constraints

- each NPC suggestion should explain its role, angle, and likely usefulness
- suggested NPCs should fit the campaign's current tone and geography
- suggestions should reference relevant existing people, factions, mysteries, or places when that makes them stronger
- the task may recommend reusing or reframing an existing NPC instead of inventing a new one

## Failure

- NPC suggestion is generic and detached from campaign context
- suggestion duplicates a current NPC without purpose
- speculative NPC details are treated as established canon
