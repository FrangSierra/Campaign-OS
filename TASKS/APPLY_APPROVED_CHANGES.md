# Apply Approved Changes

## Purpose

Apply approved Event, Entity, and Relationship changes to canon.

## Inputs

- `campaign_ref`
- approved `event_refs`
- approved change set

## Outputs

- active Events
- updated Entities
- updated Relationships

## Dependencies

- [EVENT.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/EVENT.md)
- [ENTITY.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/ENTITY.md)
- [RELATIONSHIP.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/RELATIONSHIP.md)

## Files Read

- draft Events
- approval decision
- affected canon records

## Files Written

- activated Event files
- updated Entity files
- updated Relationship files

## Approval

- explicit human approval required

## Constraints

- only approved changes are applied
- supersession history is preserved
- downstream canon matches approved Event effects

## Failure

- missing approval
- applied scope exceeds approval
- provenance chain would be broken
