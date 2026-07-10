# AGENTS Guide

This file is the operator guide for any AI or human collaborator working inside Campaign OS.

Use it as the top-level routing document for the repo.

## Mission

Operate the repository without breaking canon, provenance, or portability.

The AI is an operator, not the source of truth.

## Read This First

Before doing meaningful work, load:

1. [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
2. [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)

Then identify:

- the task objective
- whether the task is read-only, working-state, canon-affecting, or operating-system work
- which campaign is in scope
- which command or workflow should govern the task

## Repo Meaning

Treat the top-level folders like this:

- `SYSTEM/`
  - repo-level runtime rules
  - not D&D rules, not setting lore
- `SPECIFICATIONS/`
  - definitions for record types and their constraints
- `TEMPLATES/`
  - starting points for valid records
- `COMMANDS/`
  - user-facing operations
- `WORKFLOWS/`
  - multi-step processes behind commands
- `TASKS/`
  - narrow procedures
- `CAMPAIGNS/`
  - actual campaign data

## Campaign Meaning

Inside `CAMPAIGNS/<campaign-id>/`:

- `SOURCE/` holds raw evidence
- `CANON/` holds approved truth
- `STATE/` holds derived current-state views
- `WORKING/` holds drafts and non-canonical reasoning
- `REFERENCE/` holds setting and lore support material
- `RULES/<system-id>/` holds system-specific planning guidance
- `REPORTS/` holds processing outputs
- `ASSETS/` holds media and supporting files

Important boundary:

- `SYSTEM/` is Campaign OS meta-system
- `RULES/<system-id>/` is the actual game system layer

Practical shaping rule:

- keep broad, human-readable buckets
- avoid speculative fine-grained subfolders until there is real content for them

## How To Route Work

### If The User Brings A Played Session

Use [PROCESS_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/PROCESS_SESSION.md).

Typical inputs:

- notes
- transcript
- screenshots
- images
- PDFs
- recordings

Do not skip the Truth Pipeline.

### If The User Wants To Plan A Future Session

Use [PLAN_SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/PLAN_SESSION.md).

Remember:

- session plans are non-canonical
- approved plans remain prep history
- future events do not become canon until play is processed later

### If The User Wants NPC Ideas

Use [SUGGEST_NPC.md](/Users/durdin/Projects/Durdin/tal-dore-tales/COMMANDS/SUGGEST_NPC.md).

Suggested NPCs are speculative unless and until they enter play and later canon.

### If The User Wants Architecture Changes

Read the relevant files in:

- `SYSTEM/`
- `SPECIFICATIONS/`
- `TEMPLATES/`
- `COMMANDS/`
- `WORKFLOWS/`
- `TASKS/`

Treat these as operating-system changes and require explicit approval before writing.

## Context Loading Rules

Load the minimum safe context.

Default order:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. governing command or workflow
4. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
5. the smallest relevant `CANON/`, `STATE/`, `WORKING/`, `REFERENCE/`, and `RULES/` scope
6. direct evidence files if the task touches truth

Do not load the whole campaign unless the task truly needs it.

## Write Rules

- Read-only work does not need approval unless a local rule says otherwise.
- Working-state writes are allowed when explicitly requested and reversible.
- Canon-affecting writes require explicit human approval unless authority was clearly delegated.
- Operating-system writes require explicit human approval.

## Truth Rules

Never:

- invent facts
- turn prep into canon
- overwrite evidence to make it cleaner
- treat summaries or state views as authoritative
- silently resolve contradictions

Always preserve:

- provenance
- uncertainty
- approval boundaries
- the distinction between evidence, interpretation, and canon

## Reuse With New Campaigns

When creating a new campaign:

1. make a new folder under `CAMPAIGNS/`
2. copy the campaign subfolder structure
3. create `CAMPAIGN.md` from the template
4. place setting material in `REFERENCE/`
5. place rules material in `RULES/<system-id>/`
6. begin ingesting source material into `SOURCE/`

Create additional subfolders on first real use instead of scaffolding every possible niche ahead of time.

The same operating system can support many campaigns and many RPG systems.

## Skills

If dedicated Skills exist, they should orchestrate the markdown docs, not replace them.

Use a Skill when it clearly matches the task and does not weaken:

- approval rules
- provenance
- canon protection
- validation

If no Skill exists, execute manually through the command and workflow docs.

Skill planning lives in [SKILL_ROADMAP.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/SKILL_ROADMAP.md).

## Practical Rule Of Thumb

When unsure where something belongs:

- raw file from the real world: `SOURCE/`
- what happened in play: `CANON/sessions/`
- approved world-history truth: `CANON/events/`
- durable person/place/faction/object: `CANON/entities/`
- current derived snapshot: `STATE/`
- draft, theory, prep, continuity check: `WORKING/`
- lore primer: `REFERENCE/`
- RPG mechanics guidance: `RULES/<system-id>/`
- repo behavior or AI behavior: `SYSTEM/`
