# Generate Change Set

## Purpose

Translate draft Events into a reviewable set of proposed Entity and Relationship updates.

## Inputs

- `campaign_ref`
- `event_refs`
- affected Entity and Relationship records

## Outputs

- one pending change set

## Dependencies

- [EVENT.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/EVENT.md)
- [ENTITY.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/ENTITY.md)
- [RELATIONSHIP.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/RELATIONSHIP.md)

## Files Read

- draft Events
- affected Entities
- affected Relationships

## Files Written

- pending change-set content for approval review

## Approval

- the change set itself does not apply canon

## Constraints

- each proposed change is backed by draft Events
- the change set is explicit enough for approval review

## Failure

- event effects cannot be mapped
- proposed changes exceed event scope
