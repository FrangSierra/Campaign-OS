# Bootstrap Campaign

## Purpose

Create a new local Campaign OS campaign from either existing material or a short guided interview, without promoting unreviewed material into canon.

## Inputs

- a `campaign_id` and campaign name;
- either a folder of notes, documents, transcripts, images, PDFs, or recordings, **or** answers to a guided setup interview;
- the game system, if known;
- optional starting premise, player-character details, tone, safety boundaries, and intended campaign style.

## Modes

### Import existing material

Use this mode when the user already has a folder of campaign notes or files.

Create a local campaign scaffold, inventory the supplied material, and preserve it as source material or reference material. Do not infer canon simply because a document uses confident language. Ambiguous or conflicting material remains visible for later review.

### Guided setup

Use this mode when the user is beginning with an idea rather than files.

Ask only for the information needed to make a useful scaffold:

- campaign name and game system;
- premise, tone, and starting situation;
- player-character names or roles, if already known;
- any confirmed setting facts, no-go themes, or boundaries.

Record supplied setup facts as explicit human initialization. Leave unknowns blank rather than filling them with invented lore.

## Outputs

- `CAMPAIGNS/<campaign-id>/CAMPAIGN.md` based on the campaign template;
- the folders required for the campaign's real material;
- an import inventory or setup summary in `REPORTS/`;
- preserved source material and/or reference material when supplied;
- clear next steps for processing a played session or preparing the first session.

## Approval

Creating a new local campaign scaffold, preserving supplied source material, and writing a setup summary are allowed when explicitly requested.

Stop for human approval before creating canonical Events, updating durable Entities or Relationships, or presenting imported material as established world history.

## Constraints

- Keep raw input, observations, working interpretation, canon, and derived state separate.
- Treat files from an existing campaign as evidence or reference until their status is reviewed.
- Keep new campaign data local by default; `CAMPAIGNS/` is ignored by this repository's Git configuration.
- Prefer the smallest useful scaffold. Create narrower folders only when the campaign has material that needs them.

## Next steps

- Use [PROCESS_SESSION.md](PROCESS_SESSION.md) after the first played session.
- Use [PLAN_SESSION.md](PLAN_SESSION.md) when preparing a future session.
- Use [AGENTS.md](../AGENTS.md) for the full operating rules.
