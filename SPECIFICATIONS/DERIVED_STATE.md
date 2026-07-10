# Purpose

Derived State defines reproducible current-state outputs generated from approved campaign knowledge. It improves usability without becoming canon.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- derived state kind
- freshness status
- derivation inputs
- generation timestamp

# Required Fields

- `campaign_ref`
- `state_kind`
- `derived_status`
- `derived_from_refs`
- `generated_at`

# Optional Fields

- `summary`
- `entity_refs`
- `relationship_refs`
- `event_refs`
- `staleness_reason`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `state_kind` is not empty.
- `derived_status` is one of `current`, `stale`, `regenerating`, or `archived`.
- `generated_at` is present.
- `derived_from_refs` are present unless the record explicitly represents empty initialization.
- Derived State is reproducible from its declared inputs.
- Derived State never overrides canonical records.

# References

- Campaign
- Session
- Event
- Entity
- Relationship
- Working Record
