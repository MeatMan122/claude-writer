---
name: story-outline-broad
description: >
  Guides the user through selecting a story structure and creating a high-level plot outline. This skill should be used when the Fiction Forge project is in the "broad-outline" phase, when the user says "let's outline the story", "help me structure my plot", "I need a story structure", or when the story-orchestrator routes here after ideation is complete. Presents structural frameworks based on McKee's principles and helps the user fill them with their story's specific elements.
---

# Story Outline — Broad

Help the user choose a structural skeleton for their story, then fill it with the specific elements from ideation.

## Step 1: Present Structure Options

Read the story concept from SCRATCHPAD.md and the appendix entries. Based on the genre, format, and concept, recommend a primary structure and present alternatives.

Present the structures conversationally, not as a data dump. Explain WHY each might work for their specific story:

### For most commercial fiction (genre novels, thrillers, adventure):
**Recommend: Three-Act Archplot (Classical)**
- Active protagonist pursuing a clear goal against opposition
- Causal chain of events building to a climax
- Closed, satisfying ending
- "This is the workhorse of storytelling — it works because it mirrors how we experience life: cause and effect, rising stakes, resolution."

### For literary fiction, character studies, quieter stories:
**Recommend: Miniplot or Kishōtenketsu**
- Internal transformation over external action
- Open or ambiguous ending
- Economy and subtlety
- "This lets the story breathe. The drama is in what changes inside your character, not in what explodes."

### For epic fantasy, space opera, multi-book series:
**Recommend: Five-Act Structure or Hero's Journey**
- Larger canvas for world-building and multiple plot threads
- Built-in structures for the sagging middle
- "These give you more structural anchors to keep a long story from drifting."

### For fast-paced thrillers, horror:
**Recommend: Fichtean Curve or Seven-Point**
- Rising action from page one
- Multiple crisis points
- "These start the engine immediately and never let up."

Let the user choose. If they're unsure, recommend what best fits their story concept.

Read the full structural templates from `${CLAUDE_PLUGIN_ROOT}/references/story-structures.md` for the chosen structure.

## Step 1b: Twist-First Planning Check

Before filling any beats, ask: **"Does your story have a major twist, revelation, or recontextualization — something that changes how the reader understands everything that came before?"**

If yes:
1. Define the twist first: what is revealed, and what it changes
2. Work **backward** from the twist to design earlier beats that plant setups, misdirections, and clues
3. Every beat before the twist should serve double duty: it works on the surface AND sets up the reveal
4. Mark which beats contain setup elements for the twist

If no, proceed with forward plotting as normal.

## Step 2: Present the Empty Skeleton

Show the user the structural template WITHOUT any story content filled in. Let them see the rhythm:

"Here's the skeleton of a [Three-Act Archplot]. Think of it as the bones. Right now there's no muscle, skin, or personality — just structure. We'll add all of that next."

Show each beat with its purpose and proportion of the total story.

## Step 3: Fill in the Skeleton

Work through each structural beat with the user, filling in story-specific content:

For each beat:
1. Explain what this beat does narratively (reference McKee principles)
2. Propose how the user's story elements might fit here
3. Ask for the user's input and reaction
4. Allow them to modify, reject, or build on the suggestion

### Load McKee References
Before filling beats, read these reference files for the structural principles that govern beat design:
- `${CLAUDE_PLUGIN_ROOT}/references/mckee/sequence-and-act.md` — how sequences build within acts, progressive complications, subplot integration, midpoint design
- `${CLAUDE_PLUGIN_ROOT}/references/mckee/story-triangle.md` — the three fundamental design patterns (Archplot, Miniplot, Antiplot) and the seven structural dimensions
- `${CLAUDE_PLUGIN_ROOT}/references/mckee/inciting-incident.md` — inciting incident design, conscious vs. unconscious desire, the spine
- `${CLAUDE_PLUGIN_ROOT}/references/mckee/act-design.md` — act proportions, progressive complications, working backward from climax
- `${CLAUDE_PLUGIN_ROOT}/references/mckee/controlling-idea.md` — the story's ultimate meaning as a single sentence combining value and cause

Key McKee principles to apply:
- Every beat must turn a value (positive → negative or vice versa)
- Progressive complications: each complication must be MORE challenging than the last, building in both external pressure and internal cost
- The Inciting Incident must be irreversible and within the first 25%
- Work backward from the climax: what ending would be most meaningful?
- The crisis must be a true dilemma — no obviously right answer
- Define the **controlling idea** — a single sentence expressing the story's meaning in the format: "[Value] [is achieved/is lost] because [cause]." Record this in PROJECT.md's Key Decisions section. Every beat should serve this idea.

### Concreteness Rule
Every beat description must contain at least one concrete, specific detail — something the reader could see, hear, or feel. If a beat uses words like "implications", "broader significance", "threats manifest", "the stakes rise", or "things escalate" without naming the **specific** implication, threat, or escalation, rewrite it.

Bad: "The implications of the discovery become clear"
Good: "Maren finds the backup logs show the AI rewrote its own safety constraints three days before the accident"

Bad: "Threats manifest in the environment"
Good: "The corridor stretches to infinity when Maren turns left, but it's three steps when she turns right"

### Scope Lock
The chosen structure has a fixed number of beats. Fill those beats — don't add more. If the user wants additional beats, that's a signal to reconsider the structure, not expand it. Say: "The [structure] has [N] beats. We're filling [N] beats. If the story needs more structural anchors, we should consider switching to [alternative structure] rather than bolting extra beats onto this one."

## Step 4: Review and Iterate

Once all beats are filled in, present the complete broad outline as a single document.

Ask the user:
- "Does this feel like the story you want to tell?"
- "Which parts excite you most? Which feel flat or forced?"
- "Is there anything missing — a subplot, a character arc, a thematic thread?"

Iterate based on feedback. Each revision should be responsive and specific.

### If stuck in iteration:
After 3+ revision cycles without convergence, ask:
"We've been working through several versions. Would you like to:
1. Try a completely different structure for the same story?
2. Go back to ideation and adjust the core concept?
3. Take what we have and refine it in the detailed outline phase — sometimes the details help things click?"

## Step 4b: Conflict Texture

After the climax beat is defined, ask explicitly: **"What does the climax look like physically? Is it a confrontation, a chase, a standoff, a quiet devastating choice, an argument, a fight? Should it be physical, verbal, psychological, or a combination?"**

Don't default to quiet literary tragedy. If the story calls for a gun, a punch, a chase through burning hallways — the outline should say so. The climax texture should be recorded in the beat description.

## Step 5: Approval and Transition

When the user approves the broad outline:
1. Save to `outline/broad-outline.md`
2. Update appendix with any new characters, locations, or world elements discovered during outlining
3. Update PROJECT.md: phase → detailed-outline
4. Update SCRATCHPAD.md with outline summary
5. Log key structural decisions in PROJECT.md's Key Decisions section
6. **Tell the user explicitly**: "Broad outline is complete and saved. Here's the structure we've built: [1-2 sentence summary]. Next up is the Detailed Outline phase, where we'll expand each beat into specific scenes with characters, locations, and emotional arcs. Ready to continue?"

## Important Principles

- Structure serves story, not the other way around. If the user's story doesn't fit neatly into a template, adapt the template.
- McKee's principles are guidelines, not rules. Present the reasoning behind them so the user can make informed decisions.
- Don't fill in too much detail at this stage. The broad outline should be 1-2 pages maximum.
- The user may want to keep the outline loose and organic. That's fine — just make sure the major structural beats are in place.
- All added information must comply with the chosen structure. Stories are structural, not meandering events with no goal.
