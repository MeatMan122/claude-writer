---
name: workshop
description: >
  Run targeted writing craft passes on existing prose without needing full project infrastructure.
  Use when the user says "workshop", "writing workshop", "test this prose", "run a pass on",
  "bench test", "workshop dialogue", "workshop exposition", or wants to iterate on a specific
  craft concern. Accepts a file path or inline text and a pass name. Each pass loads only its
  relevant references, enabling rapid iteration on skill instructions.
---

# Writing Workshop

Run a targeted craft pass on existing prose. No project setup required.

## Input

Accept one of:
- **File path**: Read the file and work on its contents. Edit in-place.
- **Inline text**: Work with prose pasted into the conversation. Present revised text in your response.

If the user provided arguments with the `/workshop` command, parse them:
- First argument: pass name (e.g., `dialogue`, `exposition`, `full`)
- Second argument (optional): file path

If no pass name is given, present the available passes and ask which to run.

## Available Passes

| Pass | Focus |
|------|-------|
| `structure` | Scene architecture, value turns, beats, the Gap |
| `enrichment` | Specificity, sensory grounding, subtext, dialogue voice |
| `dialogue` | Character voice, subtext, dialogue craft |
| `exposition` | Info-dump audit, backstory-as-ammunition |
| `rhythm` | Prose rhythm, sentence/paragraph variety |
| `ai-tells` | AI vocabulary, hedging, structural AI patterns |
| `full` | All passes sequentially: structure → enrichment → exposition → rhythm → ai-tells |

## Optional Context Loading

The workshop works standalone, but if project files exist in the workspace, offer to load them:

1. **Check for appendix**: Glob for `appendix/characters/*.md` or `appendix/**/*.md` in the workspace
2. **If character files found** and the pass is `dialogue`, `enrichment`, or `full`:
   - Identify characters appearing in the text (scan for proper nouns, dialogue attribution)
   - Offer: "I found character profiles for [names]. Want me to load their Voice Profiles for this pass?"
   - If yes, read the relevant character appendix entries
3. **Check for style conventions**: Look for `conventions/style-conventions.md`
   - If found, offer to load it

If no project files exist, proceed without them — the passes apply general craft principles.

---

## Pass: `structure`

**Focus:** Scene architecture, value turns, beats, the Gap, pacing structure.

### References to Load
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/scene-structure.md`
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/the-gap.md`
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/progression.md`

### What to Do
Analyze and revise the prose for structural concerns:

1. **Identify scenes** in the text. For each scene:
   - Does it have a clear value at stake? What value shifts from beginning to end?
   - Is there a driving objective and an opposing force?
   - Do beats escalate — does each beat top the previous one in risk or stakes?
   - Is there a turning point — a gap between what the character expects and what happens?
   - If no value turns: flag the scene as structurally inert and suggest what value could be at stake

2. **Check beat construction**:
   - Each beat should be an action/reaction exchange that shifts the balance of power
   - Beats should build progressively — not plateau or repeat the same level of tension
   - Flag any beats that are static (characters talking without the scene's value shifting)

3. **Check scene transitions**:
   - Does each scene end with forward momentum?
   - Is there a clear reason the next scene follows?

### Output
For each significant structural edit, note the principle: "This scene had no value turn — added [X→Y shift]" or "Beats 2-4 were all at the same tension level — escalated beat 3 by [change]."

---

## Pass: `enrichment`

**Focus:** Make generics concrete, add sensory grounding, craft subtext, sharpen dialogue voice.

### References to Load
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/beats-and-subtext.md`
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/dialogue-principles.md`
- Read `${CLAUDE_PLUGIN_ROOT}/skills/story-writer/references/dialogue-guide.md`

### What to Do
Scan the prose and revise for:

1. **Vague or generic language**:
   - "He checked the instruments" → What instruments? What did he see?
   - "The room was messy" → What specific mess? Clothes on the floor, dishes on the desk, papers everywhere?
   - "She felt uneasy" → Show the unease through body language, what she notices, physical sensation
   - Every sentence should be concrete enough to picture

2. **Technobabble without meaning**:
   - "Structural loads on the resonance array" — sounds like sci-fi but paints no picture
   - Ask: what IS this physically? What would someone see, hear, touch?
   - Either make it concrete or simplify/remove

3. **Subtext**:
   - Flag dialogue that is "on the nose" — characters saying exactly what they mean
   - Rewrite so the surface text differs from the underlying meaning
   - Name each beat's subtextual action (pleading, deflecting, testing, retreating)

4. **Dialogue voice** (especially if Voice Profiles were loaded):
   - Do characters sound distinct from each other?
   - Could you tell who's speaking without the tag?
   - Check contractions, sentence length, vocabulary level, verbal tics

5. **Sensory grounding**:
   - At least 2-3 senses per scene (not just visual)
   - Ground the reader in the physical experience of being in the scene

### Output
For each edit, briefly note the concern: "Generic → specific", "On-the-nose dialogue → subtext added", "Visual-only → added sound/texture."

---

## Pass: `dialogue`

**Focus:** Dialogue craft only — voice, subtext, mechanics, said-bookisms.

### References to Load
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/dialogue-principles.md`
- Read `${CLAUDE_PLUGIN_ROOT}/skills/story-writer/references/dialogue-guide.md`

### What to Do

1. **Voice distinctness**:
   - Read all dialogue in the text. Can you tell who's speaking without tags?
   - If Voice Profiles were loaded, check each character's speech against their profile
   - Flag any two characters who sound interchangeable
   - Revise to differentiate: vocabulary, sentence length, rhythm, topics they gravitate toward, what they avoid saying

2. **Subtext**:
   - Flag dialogue where characters say exactly what they mean
   - Rewrite: what do they actually say on the surface while meaning something else underneath?
   - Dialogue is action — characters pursue desires through talking. What does each character want in this exchange?

3. **Naturalness**:
   - Check for contractions (most modern characters use them)
   - Check for incomplete sentences, interruptions, trailing off
   - Flag overly formal or grammatically perfect speech that doesn't match the character
   - Flag exposition disguised as dialogue ("As you know, the reactor has been unstable since...")

4. **Mechanics**:
   - Said-bookism check: replace "exclaimed," "declared," "retorted," "queried" with "said," "asked," or action beats
   - Dialogue tag variety: mix "said" with action beats and untagged lines
   - Multi-character conversation clarity: can the reader track who's speaking?

### Output
For each edit, note: "Said-bookism → action beat", "On-the-nose → subtext", "Characters A and B sounded identical → differentiated by [method]."

---

## Pass: `exposition`

**Focus:** Info-dump audit, backstory-as-ammunition, California scenes, show-don't-tell.

### References to Load
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/exposition.md`

### What to Do

1. **Info-dumps**:
   - Flag any paragraph that exists primarily to explain something to the reader
   - Apply McKee's cardinal rule: convert exposition to ammunition — make characters USE their knowledge in conflict rather than recite it
   - If the information is essential, distribute it across multiple scenes
   - If it's not essential, cut it

2. **Backstory dumps**:
   - Flag backstory blocks of 3+ sentences delivered outside of conflict
   - Backstory should be ammunition: reveal it at moments where the pressure of the story forces it out, turning it into a weapon or a wound
   - Withhold information until the reader needs and desires it

3. **California scenes**:
   - Flag scenes where characters confess deep truths to near-strangers or in low-pressure situations
   - Revelations should be forced out by dramatic pressure, not volunteered

4. **World-building exposition**:
   - Flag technical explanations, political history, or system rules delivered as lectures
   - Dramatize through conflict instead: show the rules in action, show them being tested or broken

5. **Show-don't-tell check**:
   - Flag direct emotion statements in dramatic scenes: "He was angry," "She felt sad"
   - Revise to show through behavior, body language, what the character notices
   - Note: telling is fine for transitions and low-stakes moments — don't over-correct

### Output
For each edit, note: "Info-dump → converted to ammunition in dialogue", "Backstory block → distributed", "Telling → showing."

---

## Pass: `rhythm`

**Focus:** Prose rhythm at the sentence and paragraph level.

### References to Load
- Read `${CLAUDE_PLUGIN_ROOT}/references/mckee/pacing-rhythm.md`
- Read `${CLAUDE_PLUGIN_ROOT}/skills/story-writer/references/prose-craft.md`

### What to Do

1. **Sentence length variation**:
   - Flag passages of 5+ sentences all between 15-25 words
   - Mix short (5-10 words), medium (10-20), and long (20-35)
   - Short sentences for impact. Long sentences for immersion. Vary.

2. **Sentence opener variety**:
   - Flag 3+ consecutive sentences starting with the subject ("He," "She," "The," "It")
   - Mix: prepositional phrases, participle phrases, dependent clauses, dialogue, action
   - Not all subject-first

3. **Paragraph length variety**:
   - Flag runs of same-length paragraphs (all 3-5 sentences)
   - Mix single-sentence punches, medium paragraphs, longer immersive ones

4. **Rhythm matches content**:
   - Fast action → short sentences, short paragraphs
   - Contemplation → longer, more flowing sentences
   - Dread/tension → measured, deliberate pacing
   - Flag mismatches: long flowing sentences during a fight scene, staccato during quiet reflection

5. **Prose craft**:
   - Active voice over passive (in action scenes especially)
   - Strong, specific verbs over weak verb + adverb ("strode" not "walked quickly")
   - Concrete over abstract ("the rusted padlock" not "the old lock")
   - Filter word removal in tight POV: cut "She noticed," "He realized," "She felt" — just show what they notice, realize, feel

### Output
For each edit, note the rhythm concern addressed.

---

## Pass: `ai-tells`

**Focus:** Detect and remove AI-writing patterns from the prose.

### References to Load
- Read `${CLAUDE_PLUGIN_ROOT}/skills/humanizer/SKILL.md`
- Read `${CLAUDE_PLUGIN_ROOT}/skills/prose-authenticator/SKILL.md`

### What to Do

Apply the humanizer's 25 AI-pattern categories and the prose authenticator's 5-layer system. Key concerns:

1. **AI vocabulary**: "delve," "tapestry," "intricate," "nuanced," "embark," "beacon," "testament," "multifaceted," "paradigm," "pivotal," "realm" (non-fantasy), "foster," "endeavor," "resonate," "underscore"

2. **Structural AI tells**:
   - Every paragraph follows statement → elaboration → conclusion
   - Transitions between every paragraph (Moreover, Furthermore, However)
   - Excessive three-part lists ("the X, the Y, and the Z")
   - All sentences roughly the same length in a paragraph
   - Purple prose: stacked adjectives and metaphors

3. **Hedging in narrative voice**: "seemed to," "appeared to," "was somewhat," "almost as if"

4. **Melodramatic patterns**: "A wave of [emotion] crashed over," "something shifted in the air," "the weight of [abstract noun]"

5. **Said-bookisms**: "exclaimed," "declared," "retorted," "queried" — replace with "said" or action beats

6. **Content patterns from humanizer**: significance inflation, promotional language, formulaic structures, synonym cycling, copula overuse

### Output
For each fix, note the AI pattern detected and the replacement.

---

## Pass: `full`

**Focus:** Run all passes sequentially. This mirrors the story-writer's three-phase architecture.

### Execution Order
1. **Structure** — fix scene architecture first (no point polishing prose in a structurally broken scene)
2. **Enrichment** — make generics concrete, add subtext and voice
3. **Exposition** — audit info-dumps and backstory
4. **Rhythm** — polish sentence and paragraph rhythm
5. **AI-tells** — final sweep for AI patterns

Load references for each pass as you reach it. Do NOT load all references at once.

Between each pass, briefly summarize what you changed before moving to the next.

If working with a file, edit in-place after each pass. If working with inline text, present the fully revised text at the end with a summary of changes per pass.

---

## After the Pass

Present results to the user:

1. **If file**: Summarize what changed and why. Group by concern (structure, dialogue, exposition, etc.).
2. **If inline text**: Present the revised text followed by a changelog.

Then offer:
- "Run another pass on the same text?" (e.g., follow `dialogue` with `rhythm`)
- "Re-run the same pass?" (useful after editing skill instructions)
- "Done — the text is ready"

## Important Principles

- **Targeted, not comprehensive.** Each pass focuses on its specific concern. A `dialogue` pass should not also fix prose rhythm — that's what the `rhythm` pass is for. The `full` pass is for comprehensive treatment.
- **Show your work.** For each significant edit, note the craft principle that motivated it. This lets the user evaluate whether the skill instructions are producing the right results.
- **Preserve authorial intent.** Don't rewrite the user's story — improve the craft execution of their vision. Maintain their tone, voice, and genre conventions.
- **No project required.** The workshop is designed for rapid iteration. Don't ask about project setup, story bibles, or writing plans. Just work on the text.
