# Process Session Workflow

## Purpose

Business process for taking one session from raw input to proposed canon, approved updates, refreshed Derived State, and a Processing Report.

## Inputs

- `campaign_ref`
- raw session input supplied either as pasted content or as files already stored in `SOURCE/`
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

## Steps

1. Create Source Records.
2. Create one Session.
3. Open Working Records only when needed.
4. Propose draft Events.
5. Generate the pending change set.
6. Pause for human approval.
7. Apply approved canon changes.
8. Refresh Derived State.
9. Generate the Processing Report.

## Dependencies

- [TASKS/CREATE_SOURCE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/CREATE_SOURCE_RECORD.md)
- [TASKS/CREATE_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/CREATE_SESSION.md)
- [TASKS/OPEN_WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/OPEN_WORKING_RECORD.md)
- [TASKS/PROPOSE_EVENTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/PROPOSE_EVENTS.md)
- [TASKS/GENERATE_CHANGE_SET.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/GENERATE_CHANGE_SET.md)
- [TASKS/APPLY_APPROVED_CHANGES.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/APPLY_APPROVED_CHANGES.md)
- [TASKS/UPDATE_DERIVED_STATE.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/UPDATE_DERIVED_STATE.md)
- [TASKS/GENERATE_PROCESSING_REPORT.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/GENERATE_PROCESSING_REPORT.md)

## Approval

- Pause between change-set generation and canon application.

## Constraints

- Each step leaves durable output for the next.
- No task may bypass the Truth Pipeline.
- The final report must explain the run from raw input to final state.

## Failure

- provenance break
- approval missing
- unsupported canonical proposal
- unreproducible Derived State
