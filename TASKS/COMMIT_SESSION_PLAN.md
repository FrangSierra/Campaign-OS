# Commit Session Plan

## Purpose

Mark the current session-planning Working Record as the approved planning draft to keep for future use.

## Inputs

- `campaign_ref`
- active `plan_ref`
- explicit human confirmation to commit
- optional decision note

## Outputs

- updated session-planning Working Record with commit notes

## Dependencies

- [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md)

## Files Read

- active session-planning Working Record

## Files Written

- updated session-planning Working Record

## Approval

- requires explicit human confirmation that the current draft is the version to keep

## Constraints

- committed plan remains non-canonical and future-facing
- the record should capture what was approved and what remains flexible
- `working_status` should normally move to `resolved` unless the human wants the plan kept open
- `decision_ref` should point to the human approval note when one exists

## Failure

- plan is committed without a clear current draft
- committed plan is mistaken for canon
- unresolved caveats are lost
