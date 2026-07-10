# Plan Session Workflow

## Purpose

Business process for turning a vague future-session idea into a grounded, non-canonical session plan that can be revised with the human until explicitly committed.

## Inputs

- `campaign_ref`
- human planning brief supplied in chat or stored as working notes
- optional target session label, in-world timing, or pacing goal
- optional constraints, no-go themes, or spotlight goals

## Outputs

- one session-planning Working Record
- context synthesis tied to current campaign state
- one or more draft session structures
- optional NPC suggestion set
- one committed session plan in working state
- a durable non-canonical planning artifact that remains available until and after the real session is played

## Steps

1. Check whether pending canon approvals could materially affect planning.
2. Load the smallest current campaign context needed for the idea.
3. Open or update a session-planning Working Record.
4. Synthesize constraints, opportunities, mysteries, and continuity risks.
5. Draft a proposed session structure.
6. Suggest NPCs when useful.
7. Pause for human discussion and revision.
8. Repeat drafting and revision until the human approves the direction.
9. Commit the current plan as a durable Working Record without treating it as canon.
10. Preserve the committed plan as prep history when the real session is later processed from actual play evidence.

## Dependencies

- [TASKS/OPEN_SESSION_PLAN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/OPEN_SESSION_PLAN.md)
- [TASKS/SYNTHESIZE_SESSION_CONTEXT.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/SYNTHESIZE_SESSION_CONTEXT.md)
- [TASKS/DRAFT_SESSION_PLAN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/DRAFT_SESSION_PLAN.md)
- [TASKS/SUGGEST_NPC.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/SUGGEST_NPC.md)
- [TASKS/REVISE_SESSION_PLAN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/REVISE_SESSION_PLAN.md)
- [TASKS/COMMIT_SESSION_PLAN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TASKS/COMMIT_SESSION_PLAN.md)

## Approval

- Planning drafts and revisions are working-state writes and do not change canon.
- Committing a session plan confirms a human-approved working plan only.
- If planning reveals desired canon corrections, route those changes through the normal Truth Pipeline instead of mutating canon here.

## Constraints

- Planning outputs remain explicitly future-facing and non-canonical.
- Approved canon is the baseline for planning; pending canon must be flagged when relevant.
- The workflow must distinguish required anchors from optional ideas.
- The workflow should surface contradictions, overload, or tone mismatches instead of forcing every idea into the draft.
- Session plans should remain flexible enough for live play.
- An approved plan remains a working artifact even if play later diverges sharply from it.
- Actual session truth must still enter through `SOURCE/` and the normal `Process Session` workflow rather than being inferred from the approved plan.

## Failure

- pending canon materially changes the plan but is ignored
- future speculation is written as canon
- planning drifts away from current campaign state without being marked speculative
- contradictory or overloaded ideas are silently merged
- committed plan lacks traceable context for why its pieces were chosen
