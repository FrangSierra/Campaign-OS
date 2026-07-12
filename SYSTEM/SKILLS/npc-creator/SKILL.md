---
name: npc-creator
description: Use when the user wants to create or deeply develop a new tabletop RPG NPC through optional questions about their role, relationship to the party, attitude, voice, age, ancestry, appearance, goals, secrets, or introduction. This skill keeps creative details as non-canonical working material, checks for overlap with existing entities, and can leave unanswered choices to the operator.
---

# NPC Creator

Design an NPC a GM can actually use at the table, without mistaking a compelling idea for established canon. Follow [CREATE_NPC.md](../../../COMMANDS/CREATE_NPC.md) and use `entity-extractor` principles to ground the design and avoid duplicates.

## Read First

Load only the context needed for the NPC's intended scene:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `COMMANDS/CREATE_NPC.md`
4. `TASKS/CREATE_NPC.md`
5. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
6. the smallest relevant subset of current party, locations, factions, mysteries, NPC records, relationships, and session prep

## Choose a Mode

### Quick Concept

Use when the user needs a usable NPC now. Establish the scene function and create a compact concept with only the details needed to play them.

### Guided Interview

Use when the user wants to shape the NPC collaboratively. Ask one short group of questions at a time. Always say that the user may answer, skip, or delegate every field.

### Full Delegation

Use when the user gives a scene need and asks the skill to decide the rest. Ground the choices in loaded campaign context and label them as proposals.

### Development Pass

Use when the user already has a rough NPC concept and wants voice, relationships, motives, or table-facing behavior added without overwriting confirmed facts.

## Interview Prompts

Use only the prompts that will improve this NPC. Prefer plain language.

- What job should this NPC do in the scene, and what should they want from the party?
- Should they feel welcoming, guarded, hostile, funny, unsettling, or something else?
- How do they speak or express themselves? Any verbal habit, posture, or tell?
- Do age, ancestry, culture, class, or appearance matter for this character?
- Do they have a prior tie to a party member, a faction, or a current mystery?
- Should they recur? What should remain flexible until play?

Do not turn the interview into a form. Stop asking once the user has enough control, and fill delegated details with proposals rather than facts.

## Design Workflow

1. Identify the scene need and stable user-provided anchors.
2. Check existing entities, locations, factions, and relationships for duplicates or a stronger reuse opportunity.
3. Separate confirmed anchors, campaign-supported constraints, and creative proposals.
4. Build a concise design packet with attitude, voice, practical presence, wants, limits, likely withholdings, and a relationship posture toward the party.
5. Offer up to three introduction beats or hooks if they would help. Label them as working prep, not events.
6. When a hook implies future fallout, hand it to `consequence-engine`; when it belongs in a session, hand it to `session-prep`.
7. Persist only with explicit user direction, and only in `WORKING/` until played evidence and approval establish canon.

## Output Shape

- scene function
- confirmed anchors
- campaign grounding and overlap check
- attitude, voice, and expression
- appearance and practical details
- wants, limits, and likely withholdings
- party relationship posture
- introduction beats
- flexible details and open questions

## Guardrails

- A designed NPC is not a canonical Entity.
- Do not invent prior history, secrets, knowledge, or ties that conflict with loaded records.
- Do not let the NPC solve the scene for the party.
- Treat all future hooks, consequences, and scene beats as working material.
- If the user skips an answer, continue; do not force an interview.
