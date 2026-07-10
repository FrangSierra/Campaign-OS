# Update Derived State

## Purpose

Refresh affected Derived State after approved canon changes.

## Inputs

- `campaign_ref`
- approved `event_refs`
- updated `entity_refs`
- updated `relationship_refs`

## Outputs

- refreshed Derived State files

## Dependencies

- [DERIVED_STATE.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/DERIVED_STATE.md)

## Files Read

- current Events
- current Entities
- current Relationships
- existing Derived State

## Files Written

- updated files in `STATE/`

## Approval

- none beyond canon approval already granted

## Constraints

- refreshed state is reproducible
- refreshed state remains non-canonical
- stale state is not left marked current

## Failure

- incomplete canonical inputs
- unreproducible output
- stale state left current
