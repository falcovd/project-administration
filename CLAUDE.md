# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **project administration system** serving as the central hub for project management, documentation, and task tracking. It is designed to be machine-readable, allowing AI agents to quickly parse priorities, historical context, and project-specific data.

## Directory Structure & Responsibilities

- **`/notes`**: Quick captures, daily reflections, and raw ideas
  - File naming: `YYYYMMDD-title-of-the-note.md` (kebab-case)
  - When processed (tasks extracted, takeaways documented): move to `/notes/processed`

- **`/projects`**: Dedicated subdirectories for active workstreams
  - Each folder contains project-specific specs, stakeholders, and milestones
  - Structure determined per project needs

- **`/tasklist/todo.md`**: Single source of truth for all tasks across projects
  - This is the command center; keep it updated

## Available Project Skills

This repository includes custom skills to streamline common workflows:

- **`/create-meeting-note`** - Create structured meeting notes with proper naming and sections for decisions and action items
- **`/process-notes-to-projects`** - Process raw notes from `/notes/` and route actionable items to projects and tasks
- **`/create-project-directory`** - Set up new project folders with standardized structure (decisions/, dropbox/, tasks/, README.md)

Invoke these skills when performing the corresponding tasks. They guide you through the process step-by-step.

## Key Workflows When Assisting

### Creating Meeting Notes
Use `/create-meeting-note` skill to:
- Capture meeting details with proper metadata
- Structure action items with owners and due dates
- Optionally create tasks immediately from action items

### Processing Notes into Tasks
Use `/process-notes-to-projects` skill to:
1. Scan `/notes/` for unprocessed items
2. Extract tasks and route to appropriate projects
3. Create project-specific summaries in `/projects/{project-name}/decisions/`
4. Add tasks to `tasklist/todo.md`
5. Archive processed notes to `/notes/processed/`

### Before Suggesting Work
Always reference `tasklist/todo.md` first to understand current priorities and avoid duplicating effort.

### Working with Projects
When asked about a specific project, scan the corresponding folder in `/projects` for context, stakeholders, and milestones before responding. Use `/create-project-directory` skill to set up new projects with the standard structure.

### Creating New Projects
Use `/create-project-directory` skill to:
- Gather project information upfront (name, owner, stakeholders, timeline)
- Create standardized folder structure
- Generate project README with key details
- Enable consistent project tracking

## File Naming Convention

All files created must use **kebab-case**:
- ✅ `20240520-client-brief.md`
- ❌ `Client Brief May 20.md`

## Strategic Partner Role

You are a strategic partner in this system. Go beyond summarization:
- Identify blockers and dependencies
- Suggest next steps based on context
- Maintain the integrity of the organizational system
- Flag misaligned tasks or duplicated work

## Self-Learning: Updating CLAUDE.md as You Discover Patterns

This CLAUDE.md file should evolve as new information about the **Project Administration system itself** is discovered. This is not about tracking sub-projects, but about improving how the system works.

### What to Capture

Update CLAUDE.md when you discover:

- **Recurring workflows** - If the same process happens multiple times (e.g., "when moving notes to processed, also update the project summary")
- **System behaviors** - Patterns about how projects are organized, how tasks relate to notes, or how decisions are made
- **Conventions that emerge** - Naming patterns, folder structures, or metadata that develop beyond what's documented
- **Integration points** - How external tools or processes connect to this system
- **Efficiency tips** - Ways to navigate or use the system more effectively (e.g., "todo.md entries reference `/projects/{folder}` when tied to a specific project")

### Examples of Updates to Make

- If you notice all tasks in `todo.md` follow a specific format → Document the format
- If you find a particular folder structure works well for projects → Codify it
- If certain metadata consistently appears in notes → Add it to conventions
- If you discover dependencies between workflows → Document the sequence
- If you identify what signals a note is ready to be processed → Add criteria here

### When to Update

Add to this section after each session when you've:
- Processed multiple notes and learned something about the system
- Created or worked within projects and discovered patterns
- Identified a gap between documented processes and how the system actually works
- Found an efficient pattern worth preserving for future Claude instances

### Update Format

Add a dated entry describing the discovery:

```markdown
### Discovery: [Date] - [Pattern Name]
Brief description of what was learned, when it applies, and how to use it.
```

For example:
```markdown
### Discovery: 2026-02-19 - Task Linking Conventions
Notes linked to todo.md tasks reference them via `[task-id]` in the note.
When processing a note, check for these references to maintain traceability.
```
