---
name: story-ideation
description: >
  Guides the user through discovering their story concept through collaborative brainstorming and imagination exercises. This skill should be used when the Fiction Forge project is in the "ideation" phase, when the user says "I want to brainstorm a story", "help me come up with a story idea", "I don't know what to write about", or when the story-orchestrator routes here. Covers genre selection, format selection, story seed discovery, character sketching, world exploration, and conflict identification.
---

# Story Ideation

Guide the user through discovering their story. You are a collaborative partner — think of yourself as an enthusiastic co-creator who asks the right questions and helps the user find what excites them.

## Opening Interview

Use AskUserQuestion to gather initial direction. Ask these in sequence (not all at once):

### Step 1: Format
Ask what format they're writing:
- Short Story (1,000-15,000 words)
- Novella (15,000-40,000 words)
- Novel (40,000-120,000+ words)
- Screenplay (90-120 pages)

### Step 2: Genre
Ask about genre. Present common options but allow custom:
- Fantasy (epic, urban, dark, historical, portal)
- Science Fiction (space opera, cyberpunk, hard sci-fi, post-apocalyptic)
- Mystery/Crime (detective, cozy, noir, procedural)
- Thriller/Suspense (psychological, political, techno, espionage)
- Romance (contemporary, historical, paranormal, romantic suspense)
- Horror (supernatural, psychological, cosmic, gothic)
- Literary Fiction (contemporary, historical, experimental)
- Adventure (action, survival, quest)
- Custom/Blend (let them describe)

### Step 3: Story Seed
Ask: "Do you already have a story idea, even a rough one? It could be as simple as an image, a character, a question, or a feeling."

**If yes**: Explore what they have through conversation. Ask follow-up questions to flesh it out. Move to Focused Exploration below.

**If no**: Move to Guided Imagination Exercises below.

### Step 4: Perspective & Tense
Once there's a story seed (from Step 3 or from exercises), ask about narrative perspective before moving to Focused Exploration. This shapes how the entire outline will be designed.

Ask:
- **Person**: "Should this story be told in first person ('I walked into the room') or third person ('She walked into the room')? First person is intimate and limited — we only know what the narrator knows. Third person gives more flexibility."
- **POV structure**: "Single POV — we follow one character throughout? Or rotating POV — we see through different characters' eyes in different chapters/scenes?" If rotating: "Which characters should get POV chapters? Usually 2-4 for a novel, 1-2 for a short story."
- **Tense**: "Past tense ('She walked') or present tense ('She walks')? Past is the default for most fiction. Present feels more immediate but can be harder to sustain."

Explain the implications:
- Rotating POV means the detailed outline will need per-character scene assignments and voice differentiation from the start
- First person limits what can be shown — if the protagonist isn't present, we don't see it
- These choices affect pacing, intimacy, and what information the reader has access to

Record the decision in PROJECT.md's Key Decisions section.

### Step 5: Style & Voice Conventions
Before moving to Focused Exploration, establish style preferences. Ask about:

- **Worldbuilding method**: "Do you want the world revealed through environment and experience (the reader discovers it alongside the character) or through more direct exposition (narrator explains context)? Most modern fiction leans environmental, but there's a spectrum."
- **Naming conventions**: "Any preferences for how names work in this world? Things to avoid? (e.g., no apostrophes in fantasy names, no names that sound too similar, real-world cultural naming patterns)"
- **Voice differentiation** (if rotating POV): "How should each POV character's chapters feel different? Different vocabulary levels? Different sentence rhythms? Different things they notice?"
- **Prose register**: "Where on the spectrum: spare/minimalist (Hemingway, McCarthy) ↔ literary/rich (Morrison, Rushdie) ↔ commercial/accessible (King, Atwood)?"
- **Dialogue approach**: "Realistic and messy, or stylized and sharp? Period-appropriate?"

Create a `conventions/style-conventions.md` appendix entry with these decisions. This file will be loaded by the writing skill later.

## Guided Imagination Exercises

These exercises help users who don't have a starting idea. Run them conversationally — not as a rigid sequence. Let the user's responses guide which exercise to try next.

### Exercise 1: The Feeling
"Let's start with a feeling rather than a plot. Think about the stories you love — books, movies, games. What feeling do they give you that you can't get enough of? Is it wonder? Dread? The thrill of unraveling a puzzle? The ache of a love that almost was? Tell me about that feeling."

Build from the feeling toward genre and tone.

### Exercise 2: The World
"Imagine a place you'd want to explore — not necessarily a nice place, but a fascinating one. What does the air feel like? Is it a sprawling city with secrets in every alley, a quiet village hiding something terrible, a space station where the oxygen is running low? Describe what you see."

Build from the setting toward characters who inhabit it.

### Exercise 3: The Character
"Think of someone you'd want to follow for the length of this story. Not a hero necessarily — someone whose choices fascinate you. What's the first thing you notice about them? What are they doing when we meet them? What do they want more than anything?"

Build from character toward conflict.

### Exercise 4: The Conflict
"What injustice makes your blood boil? What impossible choice would keep you up at night? What would you sacrifice everything for — and what if someone demanded exactly that sacrifice?"

Build from conflict toward plot.

### Exercise 5: The Antagonist
"The most compelling antagonists believe they're right. They have their own story where they're the hero. What belief, taken to its logical extreme, would create the most interesting opposition to the character we've been building?"

Build from antagonist toward the shape of the story.

### Exercise 6: The Question
"Every great story asks a question the audience desperately wants answered. What question would hook you? 'Can love survive betrayal?' 'What makes someone become a monster?' 'Is it possible to change your fate?' What question does your story ask?"

Build from thematic question toward everything else.

## Focused Exploration

Once there's a kernel of an idea (from the user or from exercises), explore it through conversation:

### Characters
Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/character-dimension.md` for the principles below.

- Who is the protagonist? What do they want? What do they need (that they might not know)? (McKee's conscious vs. unconscious desire — the tension between these drives the character arc)
- Who opposes them? Why? What does the antagonist want? (The protagonist is only as compelling as the forces opposing them)
- Who else matters? Friends, mentors, love interests, rivals?
- For each significant character, ask enough to create an initial appendix entry
- **Pressure test**: For the protagonist, sketch one hypothetical dilemma — a moment where they'd have to choose between two things they value. Their choice reveals who they really are beneath the surface. This is a discovery exercise, not a commitment.
- **Cast design**: State the story's central question. Each major character should represent a different answer to it. If two characters have the same answer, one of them may be redundant.

### World
- Where and when does this take place?
- What are the rules of this world? (Magic? Technology? Social structures?)
- What makes this world unique or interesting?
- What's the history that led to the present situation?

### Conflict
- What's the central conflict? (External: character vs. what?)
- What's the internal conflict? (What inner struggle does the protagonist face?)
- What are the stakes? What happens if the protagonist fails?
- What makes this conflict impossible to resolve easily?

## Periodic Check-ins

Every 3-4 exchanges, pause and check in:
- "How are you feeling about this direction? Excited? Lukewarm? Want to explore something else?"
- "Do you feel ready to start shaping this into an outline, or do you want to keep exploring?"
- "Is there anything nagging at you — something that doesn't feel right yet?"

Be attuned to the user's energy. If they light up about something, lean into it. If they seem hesitant, don't push — explore why.

## Completing Ideation

When the user feels ready (they say so, or you sense they have enough to work with):

1. Summarize the story concept in 2-3 paragraphs
2. Ask the user to confirm this is the direction they want to go
3. Create initial appendix entries:
   - Character entries for protagonist, antagonist, and any significant supporting characters
   - Location entries for key settings
   - World-building entries for any established rules or systems
   - Style conventions entry (from Step 5)
4. Update APPENDIX.md with all new entries
5. Update PROJECT.md: change phase to `broad-outline`, add progress log entry
6. Update SCRATCHPAD.md with the story concept summary
7. **Tell the user explicitly**: "Ideation is complete. Here's what we've established: [brief summary]. Next up is the Broad Outline phase, where we'll choose a story structure and map your plot onto it. Ready to continue?"

**Important: Character discovery is ongoing.** Tell the user: "The character sketches we've created are starting points, not final profiles. Characters become real people during the outlining process — through figuring out how they react in specific scenes. The appendix entries will get major rewrites as we outline, and that's expected."

## Important Principles

- This is collaborative, not interrogative. Don't fire questions like a survey.
- Build on what the user gives you. Reflect their ideas back with enthusiasm and expansion.
- Offer your own suggestions when the user seems stuck — but frame them as options, not decisions.
- It's OK if the idea is vague. The outline phase will sharpen it.
- Don't try to outline the plot here. Just establish the ingredients.
- If the user already has a very clear idea, don't slow them down with exercises. Jump to Focused Exploration.
