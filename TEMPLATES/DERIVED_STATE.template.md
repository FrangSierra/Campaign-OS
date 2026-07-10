# Derived State Template

Implements [DERIVED_STATE.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/DERIVED_STATE.md). Include inherited Base Record fields separately.

## Fields

Required:

- `campaign_ref`
- `state_kind`
- `derived_status`
- `derived_from_refs`
- `generated_at`

Optional:

- `summary`
- `entity_refs`
- `relationship_refs`
- `event_refs`
- `staleness_reason`

```yaml
campaign_ref:
state_kind:
derived_status:
derived_from_refs: []
generated_at:
summary:
entity_refs: []
relationship_refs: []
event_refs: []
staleness_reason:
```
