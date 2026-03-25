# Fiction Forge

A comprehensive fiction writing studio that guides you from initial spark to finished manuscript, following the structural principles of Robert McKee's *Story*.

## What It Does

Fiction Forge treats you as the creative director working with an expert writing team. It walks you through every phase of fiction writing:

1. **Ideation** — Collaborative brainstorming with imagination exercises to discover your story
2. **Broad Outline** — Select a story structure (three-act, five-act, hero's journey, etc.) and map your plot
3. **Detailed Outline** — Expand into a scene-by-scene treatment with character arcs and subtext
4. **Writing Plan** — Break the outline into chapters with POV assignments and pacing
5. **Writing** — Draft chapters with built-in consistency checking and prose quality assurance
6. **Revision** — Polish with targeted edits or full rewrites, guided by authenticity analysis

Throughout the process, Fiction Forge maintains a **story appendix** — a living bible of characters, locations, world rules, and timeline that keeps everything consistent from start to finish.

## Commands

| Command | Description |
|---------|-------------|
| `/write-story` | Start a new fiction writing project |
| `/continue-story` | Resume an existing project |
| `/story-status` | Check current progress |
| `/export-story [format]` | Export manuscript to .docx, .epub, .pdf, .html, or .md |

## Skills

| Skill | Purpose |
|-------|---------|
| Story Orchestrator | Master controller — reads project state and routes to the right phase |
| Story Ideation | Interviews you about your story through guided exercises |
| Story Outline (Broad) | Structure selection and high-level plot mapping |
| Story Outline (Detailed) | Scene-by-scene expansion with subtext and value shifts |
| Story Writing Plan | Chapter breakdown with POV, pacing, and structural tracking |
| Story Writer | Chapter drafting with voice calibration and craft principles |
| Story Consistency | Verifies content against the appendix, timeline, and outline |
| Prose Authenticator | Ensures prose sounds human — catches AI tells, improves craft (6-layer system) |
| Humanizer | Detects and removes 25 distinct AI-writing patterns from prose and project documents |
| Appendix Manager | Maintains the story bible (characters, locations, world, timeline) |

## Agents

| Agent | Model | Purpose |
|-------|-------|---------|
| Consistency Checker | Sonnet | Spawned after each chapter to verify against story facts |
| Prose Refiner | Sonnet | Spawned to polish prose authenticity and literary quality |

## How It Works

Every project gets a `PROJECT.md` file that tracks where you are in the process. When you start a new session, Fiction Forge reads this file and picks up exactly where you left off — even if it's been days or weeks.

A `SCRATCHPAD.md` file provides quick context for new agents joining the project mid-stream.

The **appendix directory** contains indexed entries for every character, location, world-building element, and timeline event. Any skill can quickly look up established facts to maintain consistency.

## Supported Formats

Fiction Forge supports writing: novels, novellas, short stories, and screenplays.

It includes structural templates for: three-act archplot, five-act structure, hero's journey, kishōtenketsu, seven-point story structure, fichtean curve, and miniplot.

Genre conventions are included for: fantasy, science fiction, mystery/crime, thriller/suspense, romance, horror, literary fiction, and historical fiction.

## Getting Started

Just say "I want to write a story" or use `/write-story` to begin.

## Acknowledgments

- **Humanizer skill** adapted from [blader/humanizer](https://github.com/blader/humanizer) by Siqi Chen (MIT license). Based on [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup.
- **Story structure principles** derived from Robert McKee's *Story: Substance, Structure, Style, and the Principles of Screenwriting*.
