# Propose Events

## Purpose

Create draft Event records from the current Session and any Working Records.

## Inputs

- `campaign_ref`
- `session_ref`
- optional `working_record_refs`

## Outputs

- draft Event files

## Dependencies

- [EVENT.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/EVENT.md)

## Files Read

- current Session
- supporting Source Records
- related Working Records

## Files Written

- draft Event files in `CANON/events/`

## Approval

- draft creation allowed
- activation not allowed

## Constraints

- each Event has evidence
- each Event has explicit effect scope
- draft Events remain non-active until approval

## Failure

- unsupported Event proposal
- vague event statement
- unclear effect scope
