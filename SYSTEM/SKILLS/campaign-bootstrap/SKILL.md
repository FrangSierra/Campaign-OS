---
name: campaign-bootstrap
description: Use when the user wants to start a new local Campaign OS campaign from a folder of notes, documents, transcripts, images, PDFs, recordings, or a guided setup interview. This skill creates a privacy-safe campaign scaffold, preserves supplied material as evidence or reference, and records only explicit setup facts without automatically creating canon.
---

# Campaign Bootstrap

Create a small, usable campaign home without mistaking a pile of notes for approved world history. This skill follows [BOOTSTRAP_CAMPAIGN.md](../../../COMMANDS/BOOTSTRAP_CAMPAIGN.md) and keeps live campaign data local by default.

## Read First

Load only the context needed to bootstrap safely:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `COMMANDS/BOOTSTRAP_CAMPAIGN.md`
4. `TEMPLATES/CAMPAIGN.template.md`
5. `TEMPLATES/SOURCE_RECORD.template.md` when importing files

Read supplied material progressively. Start with a file inventory, then open only the files needed to answer the current setup question or preserve a source accurately.

## Choose a Mode

### Import Mode

Use when the user supplies a folder, archive, or set of campaign materials.

1. Confirm the new campaign ID and the source folder.
2. Inventory formats and identify notes, transcripts, images, PDFs, audio, rules material, and setting references.
3. Create the campaign scaffold under `CAMPAIGNS/<campaign-id>/`.
4. Preserve supplied material as source or reference material with its origin and any uncertainty intact.
5. Create a short import inventory in `REPORTS/` that says what was found, what was preserved, and what still needs review.
6. Do not create canonical Events, Entities, Relationships, or derived State from the import alone.

### Guided Setup Mode

Use when the user has an idea but no campaign files yet.

1. Ask for campaign name, game system, premise, tone, and starting situation.
2. Ask only for player-character information, confirmed setting facts, and boundaries that are already known.
3. Create the campaign scaffold and `CAMPAIGN.md` using explicit human initialization as provenance.
4. Write a setup summary in `REPORTS/` and mark unanswered questions as open rather than inventing answers.
5. Offer the next useful step: import material, prepare Session 1, or wait for the first played session.

## Scaffold Shape

Create only the folders that immediately serve the campaign. The normal starting set is:

```text
CAMPAIGNS/<campaign-id>/
  CAMPAIGN.md
  SOURCE/
  CANON/
  STATE/
  WORKING/
  REFERENCE/
  RULES/<system-id>/
  REPORTS/
  ASSETS/
```

Do not fill empty folders with speculative records. Create detailed subfolders on first real use.

## Guardrails

- Treat imported material as evidence or reference until it has passed through the appropriate review flow.
- Preserve ambiguity, conflicting notes, and unknown dates instead of smoothing them out.
- Keep prep and setup ideas in working state; they are not canon merely because they were supplied during onboarding.
- Keep raw source files intact. Do not rewrite them to make them look cleaner.
- Keep all campaign data out of the public repository unless the user explicitly chooses to publish it.
- When uncertainty remains about the intended campaign name, scope, or source folder, ask before writing.

## Handoff

End with a concise bootstrap report containing:

- the campaign path and mode used;
- files or interview answers used;
- what was created;
- facts recorded as explicit initialization;
- material left as evidence, reference, or open questions;
- the next recommended command.
