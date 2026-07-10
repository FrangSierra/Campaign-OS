# Campaign QA Report

## Scope

- campaign: `campaign-echoes-of-tal-dorei`
- mode: `prep-risk scan`
- fixture: `TESTS/skills/campaign-qa/fixtures/post-session-005-prep-risk-scan.md`
- intent: audit the campaign after Session 5 canonization and before Session 6 play
- write scope: read-only

## Files Loaded

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [CAMPAIGN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CAMPAIGN.md)
- [CAMPAIGN_STATUS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CAMPAIGN_STATUS.md)
- [current-world.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/current-world.md)
- [current-party.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/current-party.md)
- [known-mysteries.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-mysteries.md)
- [known-npcs.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-npcs.md)
- [known-organizations.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-organizations.md)
- [known-locations.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/known-locations.md)
- [timeline.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/timeline.md)
- [recent-session.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/STATE/recent-session.md)
- [working-session-005-prologue-boundary.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/WORKING/investigations/session-005-prologue-boundary.md)
- [plan-session-006-first-true-emon.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/WORKING/session-plans/plan-session-006-first-true-emon.md)
- [brann-copperthumb.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CANON/entities/npcs/brann-copperthumb.md)
- [ivy.md](/Users/durdin/Projects/Durdin/tal-dore-tales/CAMPAIGNS/echoes-of-tal-dorei/CANON/entities/npcs/ivy.md)

## Contradictions

No hard canon contradictions were found in the loaded scope.

Notes:

- `CAMPAIGN_STATUS.md` reports `known_contradictions: 0`, and the loaded canon and state files are consistent with that operational summary.
- The restored-timeline model is applied consistently: Sessions 1 through 5 remain lived canon for the party, while public world history resets to stable reality.
- Brann Copperthumb and Ivy are present as approved pre-appearance entities, and the current prep draft does not overstate their played history.

## Warnings

### Knowledge boundary pressure around the restored timeline

The biggest campaign risk is not contradiction but leakage. The loaded state consistently says only the party, Sadek, and Perry remember the collapsed branch, so Session 6 and future prep should keep public Emon reactions grounded in ordinary city knowledge rather than prologue memory.

### Session 6 prep must keep Brann as an anchor, not a solver

The approved prep draft already states this well, but Brann carries enough authority and reputation that he could easily absorb the party's agency if scenes drift. This is a design-risk warning, not a canon issue.

### Ivy should stay light-touch until real play defines her

Ivy is canonically approved as a recurring contact, but only at a stable high level. The prep draft is still safe; the caution is that future summaries should not backfill motives, loyalties, or methods from rehearsal material.

## Watch List

### Active mysteries that need visible traction soon

- Whether other versions of Arven still exist
- What the Time Agency ultimately wants
- Whether the collapsed branch left hidden consequences
- What became of people and histories unique to the branch

These are healthy open threads, but the campaign will benefit if the next few sessions either advance one of them lightly or deliberately establish that Emon-facing mysteries can stand on their own.

### Emerging Emon thread that could over-centralize too fast

The Session 6 draft points toward hidden tunnels, erased survey records, Lyceum-adjacent scholarship, Brann, Ivy, and the Watch all at once. That is promising, but the first case should avoid making every new city-facing institution part of the same answer immediately.

### Session-level versus durable record pressure

Oren Vestrel, Inspector Mara Thessel, and any tunnel conspirators should probably remain session-scoped until actual play proves recurrence. The repo is currently behaving conservatively here, which is good.

## Suggested Next Checks

- Run `campaign-qa` again after live Session 6 processing to check whether public Emon knowledge stayed cleanly separated from branch memory.
- Use `campaign-qa` before each prep cycle to keep the Time Agency from swallowing grounded city mysteries by accident.
- When more NPCs are introduced, add a knowledge-boundary pass focused on who knows about Arven, the branch, and the Time Agency.

## Outcome

The current campaign state looks stable. The primary QA value here is guarding tone, secrecy boundaries, and scope discipline rather than correcting broken canon.
