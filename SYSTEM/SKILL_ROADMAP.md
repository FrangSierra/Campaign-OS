# Skill Roadmap

## Purpose

This document records the current strategy for deciding:

- which capabilities should stay as `TASKS`, `COMMANDS`, or `WORKFLOWS`
- which capabilities should be elevated into real Skills
- which ideas are best merged together instead of implemented separately

This is a planning document, not an active runtime rule.

## Core Principle

Campaign OS should keep its durable operating logic in repository markdown:

- `TASKS/` for narrow procedures
- `WORKFLOWS/` for multi-step business processes
- `COMMANDS/` for user-facing entry points

Skills should sit on top of that structure.

A good Skill should:

- know when to trigger
- know what repository context to load
- orchestrate existing tasks and workflows
- add reusable judgment, routing, and domain-specific heuristics

A Skill should not replace the operating system documents that define truth, approval, provenance, or workflow boundaries.

## Current State

Current durable repo structure is already strong:

- `PROCESS_SESSION` exists as a command and workflow
- `PLAN_SESSION` exists as a command and workflow
- `SUGGEST_NPC` exists as a command/task
- campaign lore references can live in `CAMPAIGNS/<campaign-id>/REFERENCE/`
- system-specific planning references can live in `CAMPAIGNS/<campaign-id>/RULES/<system-id>/`

This means the repo is already ready for Skills. The right next move is not to rewrite the docs, but to add Skills that orchestrate them.

### Campaign Bootstrap

`campaign-bootstrap` is implemented as the entry point for new local campaigns. It supports importing a folder of existing material or starting from a guided interview, while keeping imported material out of canon until it has been reviewed through the normal flows.

### NPC Creator

`npc-creator` is implemented as the deep-design counterpart to the quick `SUGGEST_NPC` command. It uses entity-extraction and duplicate-check logic to ground a proposed NPC, then supports an optional interview for voice, attitude, party ties, appearance, and introduction hooks. Its output remains working material until play and approval establish canon.

## Decision Heuristic

Use this rule of thumb:

- keep it as a `TASK` if it is one narrow procedure
- keep it as a `WORKFLOW` if it is a durable multi-step business process
- keep it as a `COMMAND` if it is a user-facing entry point into repo procedure
- make it a `Skill` if it will be repeatedly invoked, needs smart context loading, or needs judgment across multiple tasks/workflows

## Recommended Skill Layers

### Layer 1: Keep As Docs

These should remain repository-first and not be replaced by Skills:

- Truth Pipeline rules
- approval boundaries
- canon protection
- record specifications
- templates
- narrow file update procedures

### Layer 2: Add Skills That Orchestrate Docs

These are the best high-value Skills for this repo:

1. `process-session`
2. `campaign-qa`
3. `session-prep`
4. `mystery-manager`
5. `consequence-engine`

### Layer 3: Maybe Later Skills

These are useful, but should wait until the campaign has more data or until earlier Skills exist:

- `entity-extractor`
- `knowledge-matrix`
- `campaign-health`
- `npc-simulator`
- `lore-search`

## Idea-by-Idea Mapping

### 1. Process Session

Recommended shape:

- **Keep** `COMMANDS/PROCESS_SESSION.md`
- **Keep** `WORKFLOWS/PROCESS_SESSION.md`
- **Keep** the existing supporting tasks
- **Add** a `process-session` Skill that wraps them

Why:

- this is the most important repeated operator task in the whole system
- it needs smart routing across notes, PDFs, images, transcripts, and possibly audio later
- it should remain anchored to the Truth Pipeline, so the workflow docs stay authoritative

Priority:

- `highest`

### 2. Campaign QA

Recommended shape:

- **Create** a `campaign-qa` Skill
- later add supporting task docs if recurring QA subprocedures become stable

Why:

- this is inherently cross-cutting and judgment-heavy
- it benefits from loading only the right parts of canon, state, and working records
- it is more than one narrow task and less like a single write workflow

Skill responsibilities:

- contradiction detection
- repeated clue detection
- unresolved mystery warnings
- “this NPC should not know this” warnings
- “this plot thread is dangling” warnings

Priority:

- `highest`

### 3. Generate Session Prep

Recommended shape:

- **Do not** create a separate workflow if `PLAN_SESSION` already covers drafting
- **Create** a `session-prep` Skill
- let it orchestrate:
  - existing `PLAN_SESSION`
  - planning references
  - future QA and consequence outputs

Why:

- this will probably be one of the most frequently used capabilities
- it needs a “prep packet” mode rather than always opening a new plan
- it naturally overlaps with campaign digest, reminders, hooks, and open consequences

Priority:

- `highest`

### 4. Campaign Digest

Recommended shape:

- **Merge into** `session-prep` as a lightweight mode
- optionally also expose through `campaign-qa`

Why:

- by itself, this is too small to justify a full standalone Skill
- users may want:
  - one-page summary
  - return-from-break recap
  - “what matters right now” digest

Best home:

- mode of `session-prep`

Priority:

- `high`, but not standalone

### 5. Update Timeline

Recommended shape:

- **Keep or add as a TASK**
- possibly later include inside `process-session`

Why:

- this is a narrow and deterministic post-session update procedure
- it does not need to be its own Skill unless timeline handling becomes much more complex

Priority:

- `medium`

### 6. Entity Extractor

Recommended shape:

- start as a **task or subroutine** inside `process-session`
- later elevate to Skill only if standalone extraction becomes common

Why:

- most entity extraction happens while processing sessions or external materials
- as a standalone feature it is useful, but not foundational yet

Possible later use:

- “read this document and propose NPCs, factions, clues, artifacts”

Priority:

- `medium`

### 7. Relationship Mapper

Recommended shape:

- **Keep as a task/reporting capability**
- possibly surfaced through `campaign-qa`

Why:

- relationship mapping is useful, but it is generally derivative of canon and QA
- it does not yet need its own top-level Skill

Priority:

- `medium`

### 8. Mystery Manager

Recommended shape:

- **Create** a `mystery-manager` Skill
- later support it with structured task docs if needed

Why:

- your campaign direction is investigation-heavy
- this is a genuinely distinct cognitive workflow
- it needs separation between:
  - player-known clues
  - false clues
  - hidden truth
  - unresolved questions
  - player theories

Priority:

- `high`

### 9. Consequence Engine

Recommended shape:

- **Create** a `consequence-engine` Skill

Why:

- this is one of the most valuable long-term memory tools for a long campaign
- it is not just a list; it requires judgment about trigger timing, scale, and affected actors
- it will likely become more valuable after 10+ sessions than in the first few

Skill responsibilities:

- track decisions
- create future consequence candidates
- assign likely trigger windows
- ask during prep whether a consequence should fire now

Priority:

- `high`

### 10. NPC Simulator

Recommended shape:

- **Possible later Skill**

Why:

- very useful for intrigue-heavy play
- strongest once there is a larger stable canon NPC network
- best if it is constrained to:
  - goals
  - fears
  - knowledge
  - resources
  - relationships

Risk:

- if implemented too early, it may encourage invented psychology unsupported by canon

Priority:

- `later`

### 11. Knowledge Matrix

Recommended shape:

- initially a **mode or report** inside `campaign-qa`
- later maybe its own Skill

Why:

- extremely useful for intrigue
- but likely better to prove it inside QA before splitting it into a standalone system

Best first use:

- “who knows what about clue X / event Y / NPC Z”

Priority:

- `medium-high`, but not standalone first

### 12. Canon Protector

Recommended shape:

- **Do not create as a Skill**
- keep it as a runtime principle and system invariant

Why:

- canon protection is not a feature
- it is a governing rule over every feature

Priority:

- already implemented conceptually

### 13. Lore Search

Recommended shape:

- initially **not a Skill**
- current repo search plus structured records are enough
- later consider a Skill only if semantic indexing or embeddings are added

Why:

- right now the repo is still small enough for `rg` and structured markdown
- a real lore-search Skill is most useful when exact wording is hard to remember and the corpus is large

Priority:

- `later`

### 14. Campaign Health

Recommended shape:

- start as a **report mode** of `campaign-qa`
- later spin out only if it becomes large enough

Why:

- this is a periodic synthetic assessment
- it overlaps strongly with QA

Outputs could include:

- forgotten NPCs
- unresolved hooks
- dead villains
- stale mysteries
- orphan clues
- over-centralized plot load

Priority:

- `medium-high`, but not standalone first

## Recommended Skill Roadmap

### Phase 1

Build these first:

1. `process-session`
2. `campaign-qa`
3. `session-prep`

Reason:

- these cover the most repeated and highest-value campaign operations

### Phase 2

Build after Phase 1 is stable:

1. `mystery-manager`
2. `consequence-engine`

Reason:

- these deepen the campaign's actual genre strengths

### Phase 3

Build only after the campaign corpus is larger:

1. `entity-extractor`
2. `knowledge-matrix`
3. `campaign-health`
4. `npc-simulator`
5. `lore-search`

## Suggested Folder Naming

If these become Skills later, recommended names are:

- `process-session`
- `campaign-qa`
- `session-prep`
- `mystery-manager`
- `consequence-engine`
- `npc-creator`
- `entity-extractor`
- `knowledge-matrix`
- `campaign-health`
- `npc-simulator`
- `lore-search`

## Important Boundary

Even after Skills are added:

- `WORKFLOWS/` remain the durable process contracts
- `TASKS/` remain the narrow procedures
- `COMMANDS/` remain the user-facing repo entry points
- Skills should orchestrate these, not silently replace them

## Current Recommendation Summary

Elevate or create as Skills:

- `process-session`
- `campaign-qa`
- `session-prep`
- `mystery-manager`
- `consequence-engine`
- `npc-creator`

Keep as tasks/workflows/commands:

- `PROCESS_SESSION`
- `PLAN_SESSION`
- `SUGGEST_NPC`
- timeline updates
- relationship updates
- canon protection rules

Merge into broader Skills rather than making standalone Skills:

- `campaign digest` into `session-prep`
- `campaign health` into `campaign-qa`
- `knowledge matrix` into `campaign-qa` first

Re-evaluate later:

- `entity-extractor`
- `npc-simulator`
- `lore-search`
