# Process Session

## Purpose

User-facing entry point for processing one session through the full MVP Truth Pipeline.

## Inputs

- `campaign_ref`
- raw session input supplied either as pasted content or as files from `SOURCE/notes/`, `SOURCE/images/`, `SOURCE/audio/`, `SOURCE/transcripts/`, or `SOURCE/pdf/`
- optional session labeling notes

## Outputs

- Source Records
- one Session
- optional Working Records
- draft Events
- pending change set
- approved Entity and Relationship updates
- refreshed Derived State
- one Processing Report

## Dependencies

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [WORKFLOWS/PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/WORKFLOWS/PROCESS_SESSION.md)

## Files Read

- `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
- raw inputs already stored under `CAMPAIGNS/<campaign-id>/SOURCE/`
- existing canon touched by the session
- existing `STATE/` records

## Files Written

- Source Record files
- one Session file
- optional Working Record files
- draft Event files
- approved Entity and Relationship updates
- refreshed `STATE/` files
- one report in `REPORTS/`

## Approval

- Source Record, Session, and Working Record creation do not require approval.
- Event activation requires human approval.
- Entity and Relationship updates require human approval.

## Constraints

- The command follows `Source Record -> Session -> Working Record (optional) -> Event proposals -> Approval -> Entity updates -> Relationship updates -> Derived State -> Processing Report`.
- No canon-affecting write occurs before approval.
- Every proposed canonical change remains traceable to evidence.

## Failure

- missing campaign
- missing or unusable source input
- insufficient provenance
- unsupported Event proposal
- missing approval for canon changes
- Derived State refresh failure
- report generation failure
