# Purpose

Working Record defines the non-canonical reasoning space used between observation and approved canon. It holds investigations, hypotheses, proposals, and continuity issues.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- working record kind
- working status
- focused issue
- affected records and proposed changes

# Required Fields

- `campaign_ref`
- `working_kind`
- `working_status`
- `focus_refs`
- `question_or_issue`

# Optional Fields

- `evidence_refs`
- `possible_interpretations`
- `proposed_event_refs`
- `proposed_entity_updates`
- `proposed_relationship_updates`
- `resolution_notes`
- `decision_ref`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `working_kind` is one of `investigation`, `hypothesis`, `proposal`, or `continuity`.
- `working_status` is one of `open`, `in_review`, `resolved`, `rejected`, or `archived`.
- `focus_refs` are not empty.
- `question_or_issue` is not empty.
- Working Records distinguish speculation from canon.
- Resolving a Working Record does not itself canonize anything.

# References

- Campaign
- Source Record
- Session
- Event
- Entity
- Relationship
