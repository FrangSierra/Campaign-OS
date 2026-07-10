# Purpose

Session defines the structured observation of one play occurrence. It turns Source Records into organized observation without declaring final world-history truth.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- supporting Source Record set
- session handling status
- observed play content
- optional unresolved questions and event proposals

# Required Fields

- `campaign_ref`
- `source_record_refs`
- `session_status`
- `observations`

# Optional Fields

- `session_label`
- `session_date`
- `in_world_time`
- `participant_refs`
- `unresolved_questions`
- `working_record_refs`
- `proposed_event_refs`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `source_record_refs` resolve to Source Records in the same Campaign.
- `session_status` is one of `captured`, `reconciled`, `corrected`, or `archived`.
- `observations` are not empty.
- Observation remains distinguishable from interpretation.
- `proposed_event_refs`, if present, are supportable from the Session evidence chain.

# References

- Campaign
- Source Record
- Working Record
- Event
- Entity
- Relationship
