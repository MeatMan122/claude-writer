---
name: story-outline-detailed
description: >
  Expands the broad outline into a detailed scene-by-scene treatment. This skill should be used when the Fiction Forge project is in the "detailed-outline" phase, when the user says "let's flesh out the outline", "add more detail to the outline", "scene by scene outline", or when the story-orchestrator routes here after the broad outline is approved. Handles scene design, character discovery, subtext development, and collaborative refinement.
---

# Story Outline — Detailed

Expand the broad outline into a scene-by-scene treatment following McKee's inside-out method. This is where the story takes definite shape.

## Pre-Work

1. Read `outline/broad-outline.md` for the structural skeleton
2. Read relevant appendix entries for all established characters, locations, world rules
3. Read SCRATCHPAD.md for recent context
4. **Load McKee scene design reference**: Read `${CLAUDE_PLUGIN_ROOT}/references/mckee-scene-design.md` — apply the Gap principle (what does the character expect vs. what actually happens?), beat construction, and scene-as-miniature-story structure to every scene you design
5. **Load McKee sequence and act reference**: Read `${CLAUDE_PLUGIN_ROOT}/references/mckee-sequence-and-act.md` — group scenes into sequences with identified sequence climaxes; ensure progressive complications escalate across sequences
6. **Load McKee character dimension reference**: Read `${CLAUDE_PLUGIN_ROOT}/references/mckee-character-dimension.md` — each scene should reveal character through choices under pressure, not just advance plot. Use the pressure test: design scenes that force characters into dilemmas

## The Expansion Process

Work through the broad outline beat by beat, expanding each into specific scenes. **One scene at a time** — never expand more than 1-2 scenes per exchange. Each scene gets its own focused discussion with the user.

### Step Discipline
If you find yourself batching 3-4 scenes into one response, you're going too fast. Slow down. Each scene is a creative decision point for the user. Present one, discuss it, get approval, then move to the next.

### Scene Card Format

The primary format is bullet points, not narrative paragraphs. We don't want the whole story told in the outline — we want the structural skeleton filled in. Detailed prose comes during writing.

```markdown
### Scene [Number]: [Brief Title]
**Beat**: [Which structural beat from the broad outline this belongs to, e.g., "Midpoint Reversal", "Rising Action Sequence 2"]

- What happens: [2-4 bullet points of concrete, specific action — who does what]
- The Gap: [What does the POV character expect to happen? What actually happens instead? The drama lives in this gap.]
- Value shift: [Starting value → Ending value, e.g., Trust → Betrayal]
- Emotional arc: [POV character enters feeling X → exits feeling Y]
- Subtext: [One line — what's really going on beneath the surface]
- Character reveal: [What choice or reaction in this scene reveals true character vs. characterization?]
- Setup/Payoff: [What this sets up OR what earlier setup this pays off]

Optional metadata (include when relevant):
- POV: [Character name]
- Location: [Where]
- Characters present: [Who]
- Chapter: [Expected chapter number]
```

The **Beat** reference is mandatory — every scene must hang on a structural bone from the broad outline. If a scene doesn't belong to any beat, it either needs a purpose or gets cut.

## Discovery Phase

As scenes are fleshed out, new elements will naturally emerge:
- New supporting characters needed for scenes
- Locations that didn't exist in the broad outline
- World-building details required for scenes to work
- Subplot threads that weave through multiple scenes

For each new element:
1. Flag it to the user: "This scene needs [element]. Here's what I'm thinking..."
2. Get the user's input on significant new elements
3. Create appendix entries immediately via the Appendix Manager patterns
4. Ensure new elements are consistent with existing appendix entries

### Character Discovery is Ongoing
Characters become real people during this phase — not during ideation. Ideation produced sketches; this is where characters develop through the question "How does this person react in this scene?"

- Character appendix files are living documents — expect major rewrites during detailed outlining
- When a scene reveals something new about a character (a reaction, a fear, a contradiction), update their appendix entry immediately
- Voice profiles should be refined as you discover how characters actually talk in specific situations
- Don't treat character entries as locked. They're drafts until writing begins, and even then they evolve.

### Emotional Arc Requirement
For every scene involving a major character, the emotional arc bullet is mandatory. Characters must enter and exit scenes in different emotional states. If a character enters feeling X and exits feeling X, either:
- The scene needs work (where's the emotional movement?)
- The character is furniture in this scene (consider cutting them or giving them something to do)

## User as Director

The user is the creative director. Present your scene expansions and ask for feedback:

- "Here's how I see the confrontation between [character] and [character]. Does this match your vision?"
- "I think we need a quiet scene here to let the reader breathe after that action sequence. What if [suggestion]?"
- "This scene introduces [new character]. I'm imagining them as [description]. What do you think?"
- "The subtext here is that [character] is actually feeling [emotion] even though they're saying [thing]. Does that ring true?"

Allow the user to:
- Redirect any scene
- Cut scenes they don't like
- Add scenes they want
- Change character behavior
- Adjust pacing
- Modify the emotional trajectory

## Pacing and Rhythm

Pay attention to the rhythm of scenes:
- Alternate tension and release
- Don't stack too many high-intensity scenes back to back
- Quiet character moments between action sequences
- The reader needs breathing room
- Every sequence of scenes should build to a local climax

## Completing the Detailed Outline

When all scenes are expanded:
1. Present the complete detailed outline
2. Ask for final review: "Read through this as if you're experiencing the story. Where does it drag? Where does it rush? Where are you bored? Where are you hooked?"
3. Iterate on feedback
4. Save to `outline/detailed-outline.md`
5. Update appendix with all new elements
6. Update PROJECT.md: phase → writing-plan
7. Update SCRATCHPAD.md

## Completing the Detailed Outline — Transition

When all scenes are expanded and approved:
1. Present the complete detailed outline
2. Ask for final review
3. Save to `outline/detailed-outline.md`
4. Update appendix with all new elements
5. Update PROJECT.md: phase → writing-plan
6. Update SCRATCHPAD.md
7. **Tell the user explicitly**: "Detailed outline is complete. We have [N] scenes across [N] structural beats. Next up is the Writing Plan, where we'll break these scenes into chapters with POV assignments and pacing. Ready to continue?"

## Important Principles

- This outline is the treatment — McKee's Phase 3. It should be detailed enough that writing becomes a matter of prose, not structure.
- Each scene must turn a value. If it doesn't, it either needs a purpose or it gets cut.
- Don't rush this phase. The more solid the detailed outline, the smoother the writing.
- **Concreteness over atmosphere.** The outline should name specific actions, specific objects, specific emotional states. "The alien space feels wrong" is not an outline — "The corridor extends to infinity when Maren turns left, but it's three steps when she turns right" is.
- **Bullet points, not essays.** The outline is a structural document. Save the prose for writing.
- **One scene at a time.** Never batch. Each scene is a creative decision.
