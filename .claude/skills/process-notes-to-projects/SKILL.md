---
name: process-notes-to-projects
description: Process files from /notes directory and route actionable items to projects and tasklist
---

# Process Notes to Projects

Convert raw notes into structured project work and tasks. This skill ensures that meeting notes, ideas, and raw captures are processed into the project administration system.

## When to Use

- After notes have been captured in `/notes/`
- When you need to extract tasks and consolidate information
- When organizing notes into project-specific documentation
- As part of your workflow review (scan `/notes/` for unprocessed items)

## Prerequisites

- Note files exist in `/notes/` (not in `/notes/processed`)
- Corresponding `/projects/{project-name}` directories exist (or need to be created)
- Read access to `tasklist/todo.md`

## Process

### Step 1: Scan Unprocessed Notes

List all files in `/notes/` that are NOT in `/notes/processed/`:

```
/notes/20260219-*.md
/notes/20260220-*.md
etc.
```

Ask the user which notes they want to process, or process all if they confirm.

### Step 2: Parse Each Note

For each note file, extract:
- **Meeting/session title**
- **Date**
- **Attendees** (if any)
- **Action items** with owners and due dates
- **Key decisions**
- **Discussion points relevant to projects**
- **Which project(s) this relates to** (ask user if not clear)

### Step 3: Route to Projects

For each note:

1. **Identify the related project(s)** - Ask user if unclear
   - Look for project names in the note content
   - Check if attendees are associated with specific projects

2. **Create a summary in the project folder:**
   - File: `/projects/{project-name}/{YYYYMMDD}-meeting-summary.md`
   - Content should include:
     - Meeting title and date
     - Key decisions relevant to this project
     - Action items owned by this project
     - Links back to the original note if useful
   - Keep it concise - focus on what this project needs to know

3. **Extract task items** - For each action item:
   - Add to `tasklist/todo.md` with:
     - Task description
     - Owner (from @mention if available)
     - Due date
     - Project reference (if applicable)
     - Link to original note (optional but recommended)

### Step 4: Verify and Archive

Before marking as complete:

- ✅ All action items have been added to `tasklist/todo.md`
- ✅ Project-relevant information has been documented in `/projects/{project}`
- ✅ No critical decisions were missed
- ✅ Task assignments are clear

Then:

- Move the processed note to `/notes/processed/{filename}`
- Display summary of what was processed

## Example

**Input:** `/notes/20260219-client-kickoff.md` containing:
- Attendees: Alice (Client PM), Bob (Our Project Lead)
- Project: Website Redesign
- Decisions: Approved new color palette, extended timeline to March
- Action items:
  - [ ] Bob: Create design spec by Feb 26
  - [ ] Alice: Share brand guidelines by Feb 25

**Output:**
1. Create `/projects/website-redesign/20260219-client-kickoff-summary.md`
2. Add to `tasklist/todo.md`:
   - "Create design spec for website redesign (Bob, due: 2026-02-26)"
   - "Review brand guidelines from client (Team, due: 2026-02-25)"
3. Move original to `/notes/processed/20260219-client-kickoff.md`

## Tips

- Ask for clarification if project assignment is ambiguous
- Preserve due dates - they're critical
- If a note doesn't relate to any project, ask if it should be added to general `tasklist/todo.md` anyway
- Group related action items together in tasks when possible
- Document decisions prominently in project folders - they provide valuable context
