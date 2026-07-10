# Create Session

## Purpose

Create one Session from Source Records for the current run.

## Inputs

- `campaign_ref`
- `source_record_refs`
- optional session labeling notes

## Outputs

- one Session file

## Dependencies

- [SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/SESSION.md)

## Files Read

- current Source Records
- campaign metadata

## Files Written

- one Session file in `CANON/sessions/`

## Approval

- none

## Constraints

- observations are non-empty
- Source Record links are preserved
- observation remains distinct from interpretation

## Failure

- missing Source Records
- insufficient provenance
- observation collapsed into canon
