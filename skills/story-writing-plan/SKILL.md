---
name: story-writing-plan
description: >
  Breaks the detailed outline into chapters and creates a structured writing plan. This skill should be used when the Fiction Forge project is in the "writing-plan" phase, when the user says "break this into chapters", "create a writing plan", "chapter breakdown", or when the story-orchestrator routes here after the detailed outline is approved.
---

# Story Writing Plan

Transform the detailed outline into a chapter-by-chapter writing plan that will guide the drafting process.

## Pre-Work

1. Read `outline/detailed-outline.md`
2. Read APPENDIX.md for character and element counts
3. Read PROJECT.md for key decisions (format, target word count, POV style)

## Format Detection

Read `format` from PROJECT.md. The writing plan adapts significantly based on format:

- **Novel / Novella**: Use full chapter breakdown below
- **Short Story**: Use the streamlined Scene Plan path (see below)
- **Screenplay**: Organize by act and sequence

### Short Story: Scene Plan Path

For short stories, scenes are the units — not chapters. Skip the full chapter breakdown and create a simple scene plan instead:

```markdown
# Scene Plan: [Title]

## Overview
- **Format**: Short Story
- **Target Length**: [Word count estimate]
- **Scenes**: [Total number]
- **POV**: [Character(s)]
- **Tense/Person**: [Past/Present, First/Third]

## Scene Plan

### Scene 1: [Title]
- **Beat**: [Structural beat reference]
- **POV**: [Character]
- **Length**: [Short / Medium / Long]
- **Key event**: [One sentence]
- **Value shift**: [X → Y]

### Scene 2: [Title]
[Same format]
```

No subplot tracking table. No word count targets per scene. No multi-chapter pacing analysis. Keep it lean.

After presenting the scene plan, transition the same way as the full plan: get approval, save, update PROJECT.md, move to writing phase.

---

## Chapter Division Principles (Novel / Novella)

Break the detailed outline into chapters following these principles:

### Natural Break Points
- Each chapter should have its own mini-arc with a value shift
- End chapters on moments that compel the reader forward (hooks, revelations, cliffhangers, or quiet moments of dread)
- Don't split scenes across chapters unless there's a deliberate reason

### Chapter Length
- Let length vary naturally, but keep a general range appropriate to the format
- Novel chapters: typically 2,000-5,000 words (can vary more)
- Novella chapters: typically 1,500-3,000 words

### POV Rotation (if applicable)
- If the story uses rotating POV, plan which character owns each chapter
- Ensure each POV character gets enough page time for their arc
- Avoid switching POV too frequently (readers need time to settle in)
- Consider grouping consecutive chapters by POV character in intense sequences

### Pacing Rhythm
- Alternate high-intensity and low-intensity chapters
- Place act climaxes at natural chapter endpoints
- The midpoint should feel like a significant shift
- Build momentum toward the end — later chapters may be shorter and faster

## Writing Plan Format

Create `outline/writing-plan.md`:

```markdown
# Writing Plan: [Title]

## Overview
- **Format**: [Novel/Novella/etc.]
- **Target Length**: [Word count estimate]
- **Chapters**: [Total number]
- **POV Style**: [Single/Rotating - which characters]
- **Tense**: [Past/Present]
- **Person**: [First/Third]

## Chapter Breakdown

### Chapter 1: [Working Title]
- **POV**: [Character name]
- **Estimated Words**: [range]
- **Scenes**: [List scene numbers from detailed outline]
- **Key Events**:
  - [Event 1]
  - [Event 2]
- **Value Shift**: [Starting value → Ending value]
- **Characters Appearing**: [Names]
- **Locations**: [Names]
- **Appendix References**: [Key entries to load]
- **Chapter Hook**: [How this chapter ends to keep the reader going]
- **Setup/Payoff Notes**: [What this chapter sets up or pays off]

### Chapter 2: [Working Title]
[Same format]

... [Continue for all chapters]

## Structural Notes
- **Act 1 ends at**: Chapter [N]
- **Midpoint at**: Chapter [N]
- **Act 2 ends at**: Chapter [N]
- **Climax at**: Chapter [N]

## Subplot Tracking
| Subplot | Introduced | Developed | Resolved |
|---------|-----------|-----------|----------|
| [Name] | Ch [N] | Chs [N-N] | Ch [N] |
```

## Present and Approve

1. Show the user the complete chapter breakdown
2. Walk through the pacing visually: "Chapters 1-4 build the world and introduce the conflict. Chapter 5 is where things accelerate. The midpoint hits at Chapter 8..."
3. Ask for feedback on: chapter count, pacing, POV distribution, any scenes that should be repositioned
4. Iterate until the user approves

## Step Discipline
Each writing session should tackle ONE scene (short story) or ONE chapter (novel). Never batch multiple chapters or scenes into one step. The writing plan exists so each step is clear and bounded.

## Transition

After approval:
1. Save `outline/writing-plan.md`
2. Update PROJECT.md: phase → writing, current step → "Ready to begin Chapter 1" (or "Ready to begin Scene 1" for short stories)
3. Update SCRATCHPAD.md with writing plan summary
4. **Tell the user explicitly**: "Writing plan is complete. We have [N] chapters/scenes mapped out. Next up: writing! We'll draft one chapter/scene at a time, with consistency checking after each. Ready to start with Chapter/Scene 1?"
