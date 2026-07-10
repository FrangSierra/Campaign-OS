# Open Session Plan

## Purpose

Create or reopen a Working Record for planning a future session.

## Inputs

- `campaign_ref`
- human planning brief
- optional target session label
- optional continuation from an existing `plan_ref`

## Outputs

- one Working Record file in `WORKING/session-plans/`

## Dependencies

- [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md)
- [TEMPLATES/SESSION_PLAN_WORKING_RECORD.template.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TEMPLATES/SESSION_PLAN_WORKING_RECORD.template.md)

## Files Read

- campaign metadata
- optional prior session-planning Working Record
- optional supporting notes referenced by the human

## Files Written

- one Working Record in `WORKING/session-plans/`

## Approval

- none beyond the explicit request to begin planning

## Constraints

- `working_kind` should normally be `proposal`
- the original human brief remains recoverable inside the record
- future-session material remains clearly non-canonical
- no implied canon correction is applied here

## Failure

- human brief is lost or normalized beyond recognition
- plan is opened without enough context to identify its scope
- future plan is framed as historical truth
