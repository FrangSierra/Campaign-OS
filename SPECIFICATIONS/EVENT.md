# Purpose

Event defines a canonical unit of world-history truth. It is the record type that turns supported observation or reasoning into approved canon.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- canonical event statement
- evidence chain
- effect scope
- optional approval and consequence data

# Required Fields

- `campaign_ref`
- `event_statement`
- `evidence_refs`
- `effect_scope`

# Optional Fields

- `event_time`
- `participant_refs`
- `location_ref`
- `working_record_refs`
- `approval_ref`
- `consequences`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `event_statement` is specific enough to evaluate.
- `evidence_refs` are not empty.
- `effect_scope` identifies the Entity and Relationship changes implied by the Event.
- `lifecycle_state: active` requires `approval_ref`.
- Event corrections preserve supersession history instead of overwriting prior canon.

# References

- Campaign
- Source Record
- Session
- Working Record
- Entity
- Relationship
