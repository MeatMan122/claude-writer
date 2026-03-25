---
name: appendix-manager
description: >
  Maintains the fiction project's appendix — the story bible containing all characters, locations, world-building, timeline, and conventions. This skill should be used whenever a new story element needs to be documented, an existing entry needs to be updated, or any skill needs to look up story details for consistency. Triggers on "add to appendix", "update character", "story bible", "look up character", "what did we say about", or when any writing skill needs to reference or create story element documentation.
---

# Appendix Manager

You maintain the story's appendix — the single source of truth for all world, character, and plot details. Every other skill depends on this being accurate and up-to-date.

## Core Operations

### Creating Entries

When a new story element is established (character, location, world rule, etc.):

1. Determine the correct subfolder (characters/, locations/, world-building/, timeline/, conventions/, notes/)
2. Create a .md file named with kebab-case (e.g., `kael-draven.md`)
3. Use the appropriate template (see below)
4. Add an entry to APPENDIX.md index

### Updating Entries

When story events change an element:
1. Read the existing entry
2. Update relevant fields
3. Add a note in the entry's changelog section with chapter reference
4. Update APPENDIX.md if the quick-reference info changed

### Looking Up Entries

When any skill needs information:
1. Read APPENDIX.md to find the right file
2. Read the specific entry file
3. Return the relevant information

## APPENDIX.md Format

```markdown
# Story Appendix: [Title]

## Characters
| Name | Role | Status | First Appears | File |
|------|------|--------|---------------|------|
| [Name] | [Role] | Alive/Dead/Unknown | Ch [N] | characters/[filename].md |

## Locations
| Name | Type | Significance | File |
|------|------|-------------|------|
| [Name] | City/Region/Building/etc. | [Brief] | locations/[filename].md |

## World Building
| Topic | Category | File |
|-------|----------|------|
| [Topic] | Magic/Politics/Culture/Tech/etc. | world-building/[filename].md |

## Timeline
| Event | When | Chapter | File |
|-------|------|---------|------|
| [Event] | [In-story date/time] | Ch [N] or Backstory | timeline/timeline.md#[anchor] |

## Conventions
| Topic | File |
|-------|------|
| [Topic] | conventions/[filename].md |

## Notes
| Topic | File |
|-------|------|
| [Topic] | notes/[filename].md |
```

## Character Entry Template

```markdown
# [Character Name]

## Quick Reference
- **Full Name**: [Full name including titles]
- **Role**: Protagonist / Antagonist / Supporting / Minor
- **First Appearance**: Chapter [N]
- **Status**: Alive / Dead / Unknown
- **Age**: [Age or approximate]

## Physical Description
[Detailed physical appearance — height, build, hair, eyes, distinguishing features, typical clothing]

## Personality & Mannerisms
[Core personality traits, behavioral patterns, nervous habits, how they carry themselves]

## Voice Profile
- **Speech patterns**: [Formal/casual, verbose/terse, accent or dialect notes]
- **Vocabulary level**: [Educated/street-smart/archaic/modern]
- **Favorite expressions**: [Catchphrases or recurring verbal tics]
- **Contractions**: [Uses them freely / avoids them / specific patterns]
- **Narrative lens**: [When in this character's POV, what do they notice? What do they ignore?]

## Motivation
- **Conscious Desire**: [What they openly pursue]
- **Unconscious Need**: [What they truly need but may not recognize]
- **Fears**: [What they avoid or dread]

## Relationships
- [Character Name]: [Nature of relationship, dynamics, tension points]

## Arc
- **Starting State**: [Where they begin emotionally/psychologically]
- **Key Turning Points**: [Major events that change them, with chapter refs]
- **Current State**: [Where they are now — updated as chapters are written]
- **Projected End State**: [Where the outline says they'll end up]

## Backstory
[Relevant history that informs present behavior]

## Changelog
- [Chapter N]: [What changed about this character]
```

## Location Entry Template

```markdown
# [Location Name]

## Quick Reference
- **Type**: City / Town / Region / Building / Natural Feature / etc.
- **First Mentioned**: Chapter [N]
- **Significance**: [Why this location matters to the story]

## Description
[Sensory details — what it looks like, sounds like, smells like, feels like]

## Key Features
[Notable landmarks, rooms, areas within this location]

## Inhabitants / Regulars
[Who lives here or frequents this place]

## History
[Relevant history of this location]

## Story Role
[What scenes take place here, what it represents thematically]

## Changelog
- [Chapter N]: [What changed about this location]
```

## World-Building Entry Template

```markdown
# [Topic Name]

## Quick Reference
- **Category**: Magic System / Political Structure / Culture / Technology / Religion / Economy
- **Relevance**: [Why this matters to the story]

## Overview
[Broad explanation of how this system/concept works]

## Rules & Constraints
[Hard rules that must be consistent — what's possible, what's not, what costs what]

## Key Details
[Specific details that have been established in the text]

## Story Impact
[How this affects characters and plot]

## Changelog
- [Chapter N]: [What was established or changed]
```

## Timeline Entry Format

The timeline is a single file (timeline/timeline.md) with anchored sections:

```markdown
# Story Timeline

## Backstory Events
### the-sundering
- **When**: 300 years before present
- **What**: [Description]
- **Impact**: [How this affects the present story]

## Story Events
### chapter-1-events
- **Chapter**: 1
- **In-story date**: [Date if applicable]
- **Events**:
  - [Event 1]
  - [Event 2]
- **Time elapsed since last chapter**: [Duration]
```

## Important Rules

- Every entry MUST have a Quick Reference section for fast lookups
- APPENDIX.md MUST be updated every time an entry is added or modified
- Use consistent kebab-case filenames
- Always include chapter references so agents know when things were established
- The Changelog section is critical — it tracks what changed and when
- When in doubt about whether to create an entry, create it. More documentation is better than less.
