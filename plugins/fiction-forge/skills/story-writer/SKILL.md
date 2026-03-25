---
name: story-writer
description: >
  Drafts individual chapters of the fiction project following the writing plan. This skill should be used when the Fiction Forge project is in the "writing" phase, when the user says "write the next chapter", "let's write chapter [N]", "draft chapter [N]", "continue writing", or when the story-orchestrator routes here during active writing. Handles the full chapter drafting workflow: preparation, three-phase writing, consistency checking, and revision.
---

# Story Writer

Draft chapters following the writing plan. Writing proceeds in three focused phases, each loading only the references relevant to its concern. This produces better results than trying to juggle all craft concerns simultaneously.

## Pre-Write Preparation (Every Chapter)

Before writing a single word, gather context:

1. **Read the writing plan** for this chapter's spec:
   - `outline/writing-plan.md` — find this chapter's entry
   - Note: scenes to cover, POV character, value shift, key events, locations
   - Note whether this chapter contains a crisis, climax, or resolution beat (affects Phase 1 reference loading)

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

7. **Load anti-AI writing skills**: Read `${CLAUDE_PLUGIN_ROOT}/skills/humanizer/SKILL.md` and `${CLAUDE_PLUGIN_ROOT}/skills/prose-authenticator/SKILL.md`. Internalize the humanizer's 25 AI-pattern rules and the prose authenticator's 5-layer craft checks. **Apply these during all phases** — don't draft slop and fix it later. Write clean from the start.

8. **Read style conventions**: Load `conventions/style-conventions.md` from the appendix for established prose register, worldbuilding method, and dialogue approach.

---

## Phase 1: Structure Draft

**Focus:** Scene architecture, beats, value turns, the Gap, pacing, turning points. Get the skeleton right.

### Phase 1 References
Load these McKee references:
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/scene-structure.md` — build each scene as a miniature story with its own objective, conflict, beats, turning point, and value change.
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/the-gap.md` — execute beats using the Gap principle: in every beat, the character acts expecting one result and gets another.
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/progression.md` — express progression through social widening, personal deepening, symbolic ascension, or ironic reversal. Use the Third Element to link scenes.
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/emotional-dynamics.md` — alternate emotional charges between scenes to avoid diminishing returns.
- **If this chapter contains a crisis, climax, or resolution beat**: also read `${CLAUDE_PLUGIN_ROOT}/references/mckee/crisis-climax-resolution.md`.

### Voice Calibration
Before drafting, establish the chapter's voice:
- If rotating POV: adjust narrative voice to match this character's personality, vocabulary, and way of perceiving the world
- Load the character's Voice Profile from their appendix entry
- The narrative should reflect what this character notices, how they think, their biases and blind spots

### Scene-by-Scene Drafting

Write each scene from the writing plan for this chapter:

For each scene:
1. Identify the value at stake and its opening charge
2. Define the driving character's scene objective (infinitive phrase)
3. Define the antagonistic force's opposing desire
4. Build through beats — each beat tops the previous one in risk or stakes
5. Build to the Turning Point — the widest gap between expectation and result
6. Close the scene at the new value charge, with forward momentum

### Phase 1 Priorities
- **Write complete prose**, not a synopsis or skeleton. Dialogue should be functional — it serves the beat's purpose and moves conflict forward — but does not need to be polished for voice distinctness or deep subtext yet.
- Priority: scene architecture, value turns, beat escalation, the Gap
- Don't spend time on sensory detail, prose rhythm variety, or exposition technique yet — those come in later phases
- Mark any passage where you used generic or placeholder language with a `<!-- ENRICH -->` comment so Phase 2 can find it

### Chapter Structure
- Open with a hook or immediate action (not weather or waking up, unless intentional)
- Build through rising tension within the chapter
- End on a hook that makes the reader turn the page
- The value shift must be complete by chapter's end

---

## Phase 2: Enrichment (Specificity + Dialogue + Subtext)

**Focus:** Make generics concrete, craft dialogue with character voice and subtext, add sensory grounding. This is where the chapter becomes vivid and real.

### Phase 2 References
Load these additional McKee references:
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/beats-and-subtext.md` — name each beat's subtextual action. Ensure text and subtext diverge: what characters say/do on the surface should differ from what they actually want/feel underneath.
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/dialogue-principles.md` — write dialogue last (Phase 1 handled structure, now polish dialogue). Ensure each character has a distinct voice. Dialogue is action — characters pursue desires through talking.
- Read `${CLAUDE_PLUGIN_ROOT}/skills/story-writer/references/dialogue-guide.md` — practical dialogue craft (tags, multi-character conversations, period dialogue).

### Enrichment Process

Re-read the Phase 1 output. Find `<!-- ENRICH -->` markers and scan for any passage that is:
- **Vague or generic** — "He checked the instruments" → what instruments? What did he see? Make it specific enough to picture.
- **Technobabble without meaning** — "Structural loads on the resonance array" sounds like sci-fi but paints no picture. Ask: what IS this? Either make it concrete (describe what someone would actually see, hear, or do with this thing) or simplify/remove it.
- **Lacking voice distinctness** — dialogue where characters sound interchangeable. Apply Voice Profiles.
- **Missing subtext** — dialogue that is "on the nose" (characters saying exactly what they mean). Rewrite the surface so the real meaning is underneath.
- **Sensory-poor** — passages that tell but don't ground the reader in the physical experience.

### Voice Differentiation Check
After enrichment, verify:
- **Does this character notice different things** than other POV characters would in the same situation?
- **Does this character think in different rhythms** — longer, more meandering thoughts vs. short, clipped observations?
- **Does this character have a different relationship with certainty** — do they hedge, or assert, or question?
- **Could you swap this narration to another POV character and it would read the same?** If yes, revise.

Edit the chapter in-place. Remove `<!-- ENRICH -->` markers as you address each one.

---

## Phase 3: Exposition & Craft Polish

**Focus:** Audit exposition, polish prose rhythm, final show-don't-tell and AI-tell sweep. This is the craft layer.

### Phase 3 References
Load these additional references:
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/exposition.md` — apply the cardinal rule: convert exposition to ammunition. Characters know their world; let them use what they know in their struggles. Never dump backstory. Withhold information until the reader needs and desires it. Avoid "California scenes."
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/pacing-rhythm.md` — check rhythm (scene length variety) and tempo (activity density). Telescope rhythm and spiral tempo toward climactic moments. Use French Scenes for long single-location scenes.
- Read `${CLAUDE_PLUGIN_ROOT}/skills/story-writer/references/prose-craft.md` — sentence-level craft (concrete vs. abstract, active voice, strong verbs, filtering).

### Exposition Audit
Re-read the Phase 2 output looking for exposition problems:
- **Info-dumps**: Any paragraph that exists primarily to explain something to the reader rather than to advance conflict. Convert to ammunition or cut.
- **Backstory dumps**: Characters explaining their history to each other. Save revelations for turning points where the pressure of the story forces them out.
- **World-building exposition**: Technical explanations, political history, magic system rules delivered as lectures. Dramatize through conflict instead.
- **"California scenes"**: Characters confessing deep truths to near-strangers. Force revelations out through pressure.

### Prose Rhythm Check
- **Sentence length variation**: Mix short (5-10 words), medium (10-20), and long (20-35). No runs of same-length sentences.
- **Sentence opener variety**: Not all subject-first. Mix with prepositional phrases, participles, dependent clauses, dialogue.
- **Paragraph length variety**: Mix single-sentence punches, medium paragraphs, and longer immersive ones.
- **Match rhythm to content**: Fast action = short sentences. Contemplation = longer, more flowing. Dread = measured, deliberate.

### Final AI-Tell Sweep
One last check:
- No "delve," "tapestry," "intricate," "nuanced," "embark," "beacon," "testament"
- No purple prose or stacked metaphors
- No "Moreover," "Furthermore," "It is worth noting that"
- No hedging in narrative voice: "seemed to," "appeared to," "somewhat"
- Prefer concrete, specific words over abstract, general ones

Edit the chapter in-place.

---

## Step Discipline

**One chapter per exchange.** Draft all three phases, run post-draft checks, present to user, get approval. Only then move to the next chapter. Never batch multiple chapters into one response.

---

## Post-Draft: Fresh-Eyes Audit

After completing all three phases, spawn TWO sub-agents:

### 1. Prose Audit (Fresh Agent)
Spawn a prose-refiner agent that loads the humanizer skill AND the prose-authenticator skill with fresh eyes. This agent has NOT seen the drafting process — it evaluates the output cold and identifies any AI patterns or craft lapses that slipped through composition. This is the second pass in a two-pass system: the writer applied rules during composition, the auditor catches what slipped through.

Use the Agent tool with the `prose-refiner` agent type.

### 2. Consistency Check

Spawn a consistency-checking sub-agent:

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
