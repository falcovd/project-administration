---
name: create-project-directory
description: Create a new project directory with standard structure and README
---

# Create Project Directory

Set up a new project folder with a standardized structure and documentation. This ensures all projects have consistent organization.

## When to Use

- When starting a new project
- When formalizing an initiative that was previously untracked
- When the `/projects/` directory needs a new workstream

## Standard Structure

```
/projects/{project-name}/
├── README.md          # Project overview and key info
├── decisions/         # Design decisions, meeting notes
├── dropbox/          # Reference materials, resources, external docs
└── tasks/            # Task-specific notes, subtasks, work logs
```

## Process

### Step 1: Gather Project Information

Ask the user for:

- **Project name** (will be converted to kebab-case for folder)
- **Project description** (1-2 sentences: what is it, why does it exist?)
- **Owner/Lead** (who's responsible?)
- **Key stakeholders** (who needs to be informed?)
- **Timeline/milestones** (start date, key dates, end date if known)
- **Related projects** (does this connect to other projects?)
- **Success criteria** (how will we know it's done?)

### Step 2: Create Folder Structure

Create the directory in `/projects/{project-name}/` with subdirectories:
- `decisions/` - For design decisions, meeting minutes, strategic notes
- `dropbox/` - For reference materials, resources, external documentation
- `tasks/` - For task-specific notes, subtasks, and work logs

Use kebab-case for the project folder name (e.g., `website-redesign`, not `Website Redesign`)

### Step 3: Create README.md

Create `/projects/{project-name}/README.md` with this structure:

```markdown
# [Project Name]

## Overview

[1-2 sentence description of what the project is and why it exists]

## Details

| Field | Value |
|-------|-------|
| **Owner** | [Name] |
| **Stakeholders** | [Name1, Name2, ...] |
| **Start Date** | YYYY-MM-DD |
| **Key Milestone Dates** | [List key dates] |
| **End Date** (if known) | YYYY-MM-DD |
| **Related Projects** | [Links to other projects if any] |

## Success Criteria

- Criterion 1
- Criterion 2
- Criterion 3

## Current Status

[TBD - will be updated as project progresses]

## Quick Links

- [Decisions & Meeting Notes](./decisions/)
- [Reference Materials](./dropbox/)
- [Task Tracking](./tasks/)
- [Master Task List](../../tasklist/todo.md) - Filter by this project

---

*Last Updated: YYYY-MM-DD*
```

### Step 4: Confirm Creation

- Display the created folder structure and paths
- Show the README.md content
- Ask if the user wants to create initial task entries in `tasklist/todo.md` for project setup
- Offer to create the first decision/task notes if they have initial items

## Tips

- Keep project names descriptive but concise
- The README is the project's entry point - keep it current
- Update the "Current Status" section regularly
- Use the `decisions/` folder heavily - it provides valuable context for future work
- `dropbox/` can contain anything useful: client briefs, competitor research, design assets, etc.
- `tasks/` is for detailed work tracking; high-level tasks go in `tasklist/todo.md`

## Example

**Input:** New project "Website Redesign"
- Owner: Jane Smith
- Stakeholders: Client (Alice), Design Lead (Bob)
- Timeline: Feb 19 - May 30, 2026
- Milestones: Design approval (Mar 15), Dev start (Mar 22)
- Success: "New site launched with improved conversion by 20%"

**Output:**
```
/projects/website-redesign/
├── README.md (with all details filled in)
├── decisions/
├── dropbox/
└── tasks/
```

Ready to start adding meeting notes and task tracking!
