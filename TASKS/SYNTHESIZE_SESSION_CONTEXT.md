# Synthesize Session Context

## Purpose

Gather only the current campaign context needed to judge whether a planned session fits the world, current continuity, open mysteries, and player-facing direction.

## Inputs

- `campaign_ref`
- human planning brief
- optional `plan_ref`

## Outputs

- context synthesis appended to the active session-planning Working Record

## Dependencies

- [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md)

## Files Read

- current campaign metadata
- relevant approved Sessions and Events
- current `STATE/` records
- relevant Entity and Relationship records
- relevant open Working Records
- any campaign-specific planning references stored alongside session plans

## Files Written

- updated session-planning Working Record

## Approval

- none

## Constraints

- approved canon is the default baseline
- pending approvals must be called out when they could change the plan
- context loading stays intentionally narrow
- synthesis distinguishes facts, open questions, and planning opportunities

## Failure

- important continuity risk is missed
- irrelevant full-campaign history is loaded instead of focused context
- pending canon is treated as settled truth without warning
