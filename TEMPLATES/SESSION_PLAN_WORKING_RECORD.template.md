# Session Plan Working Record Template

Implements [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md) for future-session planning. Include inherited Base Record fields separately.

## Recommended Use

- store future-session plans in `WORKING/session-plans/`
- use `working_kind: proposal`
- keep the record non-canonical even after the human commits the plan

## Fields

Required:

- `campaign_ref`
- `working_kind`
- `working_status`
- `focus_refs`
- `question_or_issue`

Optional:

- `evidence_refs`
- `possible_interpretations`
- `resolution_notes`
- `decision_ref`

```yaml
campaign_ref:
working_kind: proposal
working_status: open
focus_refs: []
question_or_issue:
evidence_refs: []
possible_interpretations: []
proposed_event_refs: []
proposed_entity_updates: []
proposed_relationship_updates: []
resolution_notes:
decision_ref:
```

## Suggested Body Structure

```markdown
# Session Plan - <label>

## Human Brief

Paste or summarize the original planning idea with minimal normalization.

## Planning Constraints

- campaign direction
- no-go themes
- pacing targets
- character spotlight goals

## Current Context

- relevant current state
- open mysteries
- relationships or factions that matter
- pending canon warnings

## Core Session Idea

One paragraph describing what this session is really about.

## Candidate Hooks

- hook 1
- hook 2

## Proposed Scene Flow

1. opening situation
2. investigation development
3. midpoint complication
4. climax or reveal
5. likely end-state

## NPC Candidates

- name or placeholder
- role in the session
- tie to world, faction, or mystery
- pressure they add

## Continuity Risks

- contradictions to watch
- ideas that may be too much
- items waiting on human decision

## Revision Notes

Track what changed after each discussion round.

## Commit Notes

Record what the human approved and what remains flexible.
```
