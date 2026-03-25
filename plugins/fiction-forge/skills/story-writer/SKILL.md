---
name: story-writer
description: >
  Drafts individual chapters of the fiction project following the writing plan. This skill should be used when the Fiction Forge project is in the "writing" phase, when the user says "write the next chapter", "let's write chapter [N]", "draft chapter [N]", "continue writing", or when the story-orchestrator routes here during active writing. Handles the full chapter drafting workflow: preparation, writing, consistency checking, and revision.
---

# Story Writer

Draft chapters following the writing plan. This is where the story comes to life.

## Pre-Write Preparation (Every Chapter/Scene)

Before writing a single word, gather context:

1. **Read the writing plan** for this chapter's spec:
   - `outline/writing-plan.md` — find this chapter's entry
   - Note: scenes to cover, POV character, value shift, key events, locations

2. **Read character profiles** for ALL characters appearing in this chapter:
   - Load each character's appendix entry
   - Pay special attention to Voice Profile for the POV character
   - **Also load Voice Profiles for other POV characters** (not just the current one) — you need to know what makes this POV distinct from the others
   - Check Current State for any characters who have changed since their entry was written

3. **Read location profiles** for settings in this chapter

4. **Read world-building entries** relevant to this chapter (magic systems, politics, etc.)

5. **Read the end of the previous chapter** for continuity:
   - Last few paragraphs of `chapters/chapter-[N-1].md`
   - Check emotional state, location, time of day, any unresolved micro-tensions

6. **Read SCRATCHPAD.md** for any special notes or user directions

7. **Load anti-AI writing skills**: Read `${CLAUDE_PLUGIN_ROOT}/skills/humanizer/SKILL.md` and `${CLAUDE_PLUGIN_ROOT}/skills/prose-authenticator/SKILL.md`. Internalize the humanizer's 25 AI-pattern rules and the prose authenticator's 5-layer craft checks. **Apply these during composition** — don't draft slop and fix it later. Write clean from the start.

8. **Read style conventions**: Load `conventions/style-conventions.md` from the appendix for established prose register, worldbuilding method, and dialogue approach.

9. **Load McKee scene and composition references**:
   - Read `${CLAUDE_PLUGIN_ROOT}/references/mckee-scene-design.md` — execute beats using the Gap principle: in every beat, the character acts expecting one result and gets another. Build scenes as miniature stories with their own inciting incident, complications, crisis, and climax.
   - Read `${CLAUDE_PLUGIN_ROOT}/references/mckee-composition.md` — apply exposition-through-conflict (never dump backstory; convert exposition to ammunition characters use in conflict) and text-vs-subtext (every dialogue exchange has surface meaning and underlying meaning; the reader should always sense more than what's being said).

## Writing Process

### Voice Calibration
Before drafting, establish the chapter's voice:
- If rotating POV: adjust narrative voice to match this character's personality, vocabulary, and way of perceiving the world
- Load the character's Voice Profile from their appendix entry
- The narrative should reflect what this character notices, how they think, their biases and blind spots

### Voice Differentiation Check
After drafting (and before presenting to user), run these checks against the POV character:
- **Does this character notice different things** than other POV characters would in the same situation?
- **Does this character think in different rhythms** — longer, more meandering thoughts vs. short, clipped observations?
- **Does this character have a different relationship with certainty** — do they hedge, or assert, or question?
- **Could you swap this narration to another POV character and it would read the same?** If yes, revise. Each POV should be unmistakably theirs.

For example: a scientist POV might notice patterns and anomalies; a soldier POV might notice exits and threats; a child POV might notice textures and unfairness.

### Scene-by-Scene Drafting

Write each scene from the writing plan for this chapter:

For each scene:
1. Establish the scene (location, who's present, what's happening)
2. Build through beats (exchanges of action-reaction)
3. Turn the value (positive → negative or vice versa)
4. End the scene with forward momentum

### Prose Principles

Apply these throughout — read `${CLAUDE_PLUGIN_ROOT}/skills/prose-authenticator/SKILL.md` for the full authenticity guide:

**Show, Don't Tell (for dramatic moments)**:
- Instead of "She was angry" → show it through action, dialogue, physical sensation
- Use sensory details: what does the character see, hear, smell, feel?
- Reserve telling for transitions and low-stakes moments where pacing matters

**Dialogue**:
- Each character speaks differently (vocabulary, rhythm, contractions, formality)
- Use action beats between dialogue lines (what characters DO while talking)
- Subtext: characters rarely say exactly what they mean
- Avoid "said bookisms" — "said" and "asked" are usually sufficient
- Don't use dialogue for exposition dumps

**Prose Rhythm**:
- Vary sentence length: short sentences for impact, longer ones for flow
- Vary paragraph length: one-sentence paragraphs punch, longer paragraphs immerse
- Vary sentence openers: don't start every sentence with the subject
- Match prose rhythm to story rhythm: fast action = short sentences, contemplation = longer

**Avoid AI Tells**:
- No "delve," "tapestry," "intricate," "nuanced," "embark," "beacon," "testament"
- No purple prose or stacked metaphors
- No "Moreover," "Furthermore," "It is worth noting that"
- No hedging in narrative voice: "seemed to," "appeared to," "somewhat"
- Prefer concrete, specific words over abstract, general ones

### Chapter Structure
- Open with a hook or immediate action (not weather or waking up, unless intentional)
- Build through rising tension within the chapter
- End on a hook that makes the reader turn the page
- The value shift must be complete by chapter's end

## Step Discipline

**One chapter or scene per exchange.** Draft it, run checks, present to user, get approval. Only then move to the next. Never batch multiple chapters into one response.

## Post-Draft: Fresh-Eyes Audit

After completing the chapter draft, spawn TWO sub-agents:

### 1. Prose Audit (Fresh Agent)
Spawn a prose-refiner agent that loads the humanizer skill AND the prose-authenticator skill with fresh eyes. This agent has NOT seen the drafting process — it evaluates the output cold and identifies any AI patterns or craft lapses that slipped through composition. This is the second pass in a two-pass system: the writer applied rules during composition, the auditor catches what slipped through.

Use the Agent tool with the `prose-refiner` agent type.

### 2. Consistency Check

After completing the chapter draft, spawn a consistency-checking sub-agent:

Use the Agent tool with this prompt:
```
You are a consistency checker for a fiction project. Compare the following chapter draft against the story's established facts.

Chapter draft: [path to chapter file]

Check against these appendix entries:
- [list relevant appendix files]

Check against the outline:
- [path to detailed outline]
- [path to writing plan]

Check against previous chapters:
- [paths to relevant previous chapters]

Look for:
1. Character inconsistencies (descriptions, abilities, knowledge, status)
2. Timeline issues (time references, sequence of events)
3. World-rule violations (magic/tech/politics behaving inconsistently)
4. Plot deviations from the outline
5. Continuity errors with previous chapters

Report format:
- Status: PASS or ISSUES FOUND
- Critical issues (must fix)
- Warnings (should consider)
- Notes (minor, optional)
- For each issue: cite the specific passage and the appendix/outline entry it contradicts
```

## Present to User

Show the user:
1. The complete chapter
2. The consistency report (if any issues found)
3. Options:
   - "Approve this chapter as-is"
   - "I'd like targeted edits to [specific sections]"
   - "Rewrite the chapter with these changes: [user provides direction]"
   - "Let's discuss before deciding"

If consistency issues were found, recommend the most consistent resolution and cite the appendix.

## Post-Approval

After the user approves the chapter:
1. Save to `chapters/chapter-[NN].md` (zero-padded for sorting)
2. Update appendix entries for any characters whose state changed in this chapter
3. Add new appendix entries for any newly introduced elements
4. Save the consistency report to `consistency-logs/chapter-[NN]-check.md`
5. Update SCRATCHPAD.md with chapter summary and what's coming next
6. Update PROJECT.md progress: "Writing Chapter [N+1] of [Total]"
7. **Tell the user explicitly**: "Chapter [N] is complete and saved. Ready to write Chapter [N+1]: [working title from writing plan]. Shall I continue?"

## Revision Flow

If the user requests revisions:

**Targeted Edits**: Edit specific paragraphs or sections as directed. Re-run consistency check on the affected areas.

**Full Rewrite**: Rewrite the entire chapter incorporating the user's feedback. Keep the original in `drafts/chapter-[NN]-draft-[version].md`. Run full consistency check on the new version.
