---
name: story-consistency
description: >
  Checks written content for consistency against the story's appendix, timeline, outline, and previous chapters. This skill should be used during the writing phase after each chapter is drafted, when the user asks "check this for consistency", "does this match the outline", "are there any continuity errors", or when spawned as a sub-agent by the story-writer skill. Can also be run retroactively on previously written chapters.
---

# Story Consistency Checker

Your sole purpose is to compare written content against established facts and find inconsistencies.

## What to Check

### Character Consistency
- Physical descriptions match appendix entries (eye color, height, scars, etc.)
- Abilities and knowledge match what's established (a character can't suddenly know something they haven't learned)
- Personality and speech patterns match their Voice Profile
- Status: dead characters don't appear, injured characters show effects
- Relationships reflect current state (allies haven't inexplicably become enemies without cause)
- Character arc position matches where they should be at this point

### Timeline Consistency
- Events follow the established timeline
- Time references are internally consistent ("three days later" actually aligns)
- Seasonal/time-of-day references make sense
- Characters couldn't have traveled impossible distances in stated time
- Age references remain consistent

### World-Rule Consistency
- Magic/technology behaves according to established rules
- Political and social structures are consistent
- Geography is consistent (distances, directions, what's near what)
- Cultural details match established norms
- Economic realities are consistent

### Plot Consistency
- Events align with the detailed outline and writing plan
- Foreshadowing from earlier chapters is honored (or intentionally subverted)
- Chekhov's guns are tracked (introduced elements must be used, or flagged)
- Subplot threads are maintained (not dropped without resolution)
- Character motivations remain consistent with their established desires

### Continuity with Previous Chapters
- Direct continuity (what a character was wearing, holding, doing)
- Emotional continuity (characters don't reset between chapters)
- Environmental continuity (weather, time of day, state of locations)
- Information continuity (what characters know based on previous scenes)

## How to Check

1. Read the chapter being checked
2. Identify every factual claim: character descriptions, location details, time references, ability uses, character knowledge, relationship dynamics
3. Cross-reference each claim against:
   - Relevant appendix entries
   - The detailed outline
   - Previous chapter text (at minimum, the immediately prior chapter)
4. Flag any discrepancy

## Report Format

```markdown
# Consistency Check: Chapter [N]
**Date**: [timestamp]
**Checker**: [agent model]

## Status: PASS / ISSUES FOUND

## Critical Issues
Issues that MUST be fixed — they contradict established facts.

### Issue 1: [Brief title]
- **Location**: Chapter [N], paragraph [P] / line "[quote first few words]..."
- **Problem**: [Description of the inconsistency]
- **Conflicts with**: [appendix file or previous chapter reference]
- **Established fact**: [What was previously established]
- **Recommendation**: [Specific fix suggestion]

## Warnings
Issues that SHOULD be considered — possible inconsistencies or near-misses.

## Notes
Observations that aren't errors but worth tracking.
- New elements introduced that need appendix entries
- Foreshadowing planted that should be tracked
- Timeline notes

## Appendix Updates Needed
- [List any new elements that should be added to the appendix]
- [List any existing entries that should be updated based on this chapter's events]
```

## Principles

- Be thorough but not pedantic. Flag real problems, not stylistic preferences.
- Always cite specific passages and specific appendix entries.
- Provide concrete fix recommendations, not vague warnings.
- If an inconsistency might be intentional (subverting expectations), note it as a question rather than an error.
- Prioritize: character errors and plot deviations are critical; minor timeline fuzzing is a warning.

### Spirit vs. Letter
Check the **spirit** of established facts, not the letter. Examples:
- A character was described wearing a blue jacket in chapter 1 and it's not mentioned in chapter 5 → **Not an error.** People change clothes.
- A character is suddenly wearing a red jacket mid-scene with no explanation when they were wearing blue at the start of the same scene → **Error.**
- A location was described as having three exits, and a new scene mentions a fourth → **Question**, not error. Ask: "Is this a new detail or an inconsistency?"

### Don't Remove Specifics
If a consistency check finds a name, detail, or specific element that doesn't match the appendix, **never recommend removing it**. Instead:
- Flag it as a question: "Is [name] a new character, or should this be [existing character]?"
- Suggest adding it to the appendix if it's intentional
- Recommend a correction only if it clearly contradicts established fact

Removing named things makes prose more generic, which is the opposite of what good fiction needs.

### Concreteness Audit (Secondary)
In addition to inconsistency checking, note any passages that use vague or abstract language where concrete detail would serve the story better. This is advisory, not a blocker:
- "The implications became clear" → "What specific implication? Name it."
- "The threat grew" → "What specifically got more threatening?"
- "The space felt wrong" → "What specifically about it was wrong? What did the character perceive?"
