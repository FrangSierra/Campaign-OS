# Plan Session

## Purpose

User-facing entry point for drafting, revising, and committing a future session plan from a vague human idea plus current campaign context.

## Inputs

- `campaign_ref`
- planning brief in pasted text or existing working notes
- optional desired tone, pacing, spotlight goals, or no-go themes
- optional reference to a prior session plan to continue revising

## Outputs

- one session-planning Working Record in `WORKING/session-plans/`
- context synthesis grounded in current campaign state
- draft hooks, scenes, investigation leads, NPC ideas, and continuity warnings
- optional committed session plan
- a durable prep artifact that can be revised before play and referenced after play without becoming canon

## Dependencies

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [WORKFLOWS/PLAN_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/WORKFLOWS/PLAN_SESSION.md)

## Files Read

- `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
- relevant approved `CANON/` records
- relevant `STATE/` records
- relevant `WORKING/` records, especially open continuity issues and prior plans
- relevant campaign references in `REFERENCE/`
- relevant system planning references in `RULES/`

## Files Written

- one or more Working Record files in `WORKING/session-plans/`

## Approval

- Drafting and revision may proceed when explicitly requested.
- Committing the plan requires explicit human confirmation that the current draft is the version to keep.
- No canon-affecting change may be applied from this command.

## Constraints

- The command follows `Open Plan -> Synthesize Context -> Draft -> Revise -> Commit`.
- It should prefer the smallest context set that still keeps the plan grounded.
- It should call out ideas that clash with the campaign's stated direction or current state.
- It may recommend dropping, replacing, or postponing ideas rather than forcing them in.
- It should load any campaign-specific lore or system planning references that have been staged for this campaign.
- After the session is actually played, this command's output remains a historical prep record rather than evidence of what happened.

## Failure

- missing campaign
- missing planning brief
- insufficient context to evaluate continuity
- plan written as canon
- plan committed without a clear current draft
