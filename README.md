# Campaign OS

Campaign OS is a markdown-first operating system for tabletop campaigns.

It is built to help a human GM and an AI collaborator work together without losing canon, provenance, or campaign continuity.

## What This Repo Is For

Use this repo to:

- preserve raw session evidence
- turn played sessions into structured canon
- plan future sessions without treating prep as truth
- track NPCs, factions, mysteries, and state over time
- keep a campaign portable across tools and AI runtimes

## Core Idea

Campaign OS separates:

- evidence
- observation
- working interpretation
- approved canon
- derived current state

That separation is the whole point. It keeps the campaign usable after months of play and makes contradictions fixable instead of invisible.

## Repo Map

- `SYSTEM/`
  - Campaign OS runtime and invariants
  - repo-level operating rules
  - not RPG system rules
- `SPECIFICATIONS/`
  - contracts for record types like `Session`, `Event`, `Entity`, and `Working Record`
- `TEMPLATES/`
  - starter templates for those record types
- `COMMANDS/`
  - user-facing entry points such as `PROCESS_SESSION`, `PLAN_SESSION`, and `SUGGEST_NPC`
- `WORKFLOWS/`
  - multi-step business processes behind the commands
- `TASKS/`
  - narrow procedures used by workflows
- `CAMPAIGNS/<campaign-id>/`
  - actual campaign data

## Campaign Data Map

Inside a campaign directory:

- `SOURCE/`
  - raw notes, transcripts, images, audio, PDFs
- `CANON/`
  - approved sessions, events, entities, and relationships
- `STATE/`
  - derived current-state views
- `WORKING/`
  - non-canonical drafts, investigations, continuity notes, and session plans
- `REPORTS/`
  - processing outputs and run summaries
- `REFERENCE/`
  - setting and lore material used for grounding
- `RULES/<system-id>/`
  - system-specific guidance such as `dnd-5.5` or `call-of-cthulhu`
- `ASSETS/`
  - maps, handouts, images, and supporting media

Not every subfolder needs to exist on day one.

Keep the stable buckets that help humans navigate the repo, but prefer creating narrow subfolders only when they are actually used.

## Main Flows

### Process A Played Session

Use [PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/PROCESS_SESSION.md).

This flow takes raw session input and moves it through the Truth Pipeline:

`Source -> Session -> Working (optional) -> Event proposals -> Approval -> Canon updates -> State refresh -> Report`

### Plan A Future Session

Use [PLAN_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/PLAN_SESSION.md).

This flow turns a vague idea into a durable prep record.

Important:

- session plans are non-canonical
- approved plans stay useful after play as prep history
- actual canon still comes later from the played session

### Suggest An NPC

Use [SUGGEST_NPC.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/SUGGEST_NPC.md).

This is for generating grounded NPC options from the current campaign, location, factions, and scene pressure.

## First-Time Setup For A New Campaign

1. Create a new folder under `CAMPAIGNS/<new-campaign-id>/`.
2. Copy the same top-level campaign subfolders used by the existing campaign.
3. Create `CAMPAIGN.md` from [CAMPAIGN.template.md](/Users/durdin/Projects/Durdin/tal-dore-tales/TEMPLATES/CAMPAIGN.template.md).
4. Put lore and setting primers in `REFERENCE/`.
5. Put game-system planning material in `RULES/<system-id>/`.
6. Store raw notes and files in `SOURCE/`.
7. Use `PROCESS_SESSION` for played sessions and `PLAN_SESSION` for future prep.

If a campaign does not need a niche subfolder yet, do not precreate it just for symmetry.

## Reusing This With Another Game System

The top-level `SYSTEM/` folder stays the same because it defines Campaign OS itself.

To support another RPG:

- keep using the same Truth Pipeline
- create a new `RULES/<system-id>/` folder inside the campaign
- add system-specific references, heuristics, and planning notes there
- keep setting/lore material in `REFERENCE/`

Example:

- `RULES/dnd-5.5/`
- `RULES/call-of-cthulhu/`
- `RULES/blades-in-the-dark/`

## Skills

This repo already works without custom Skills because the operating behavior lives in markdown.

Skills should be optional orchestration layers on top of the docs, not replacements for them.

Current skill planning is tracked in [SKILL_ROADMAP.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/SKILL_ROADMAP.md).

## For AI Operators

Use [AGENTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/AGENTS.md) as the routing and behavior guide.

It explains:

- what to load first
- how to choose the right command or workflow
- where different kinds of information belong
- when approval is required

## Portability

Campaign OS is designed so the campaign remains usable even without generated helpers, indexes, or one specific AI vendor.

Markdown records are the source of truth.
