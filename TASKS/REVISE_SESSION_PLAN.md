# Revise Session Plan

## Purpose

Update the active session-planning Working Record after human feedback while preserving the evolution of the plan.

## Inputs

- `campaign_ref`
- active `plan_ref`
- human revision notes

## Outputs

- revised session-planning Working Record

## Dependencies

- [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md)

## Files Read

- active session-planning Working Record
- any directly referenced campaign context needed to validate the revision

## Files Written

- updated session-planning Working Record

## Approval

- none until the human explicitly asks to commit the current draft

## Constraints

- revision history remains understandable
- removed ideas should not silently disappear if they affect the reasoning trail
- continuity warnings should be refreshed when the draft changes materially
- revisions may simplify, replace, postpone, or cut ideas

## Failure

- revision obscures why the plan changed
- continuity warnings are left stale
- current draft cannot be distinguished from older options
