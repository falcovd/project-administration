---
name: create-meeting-note
description: Create a new meeting note with proper naming convention and structure
---

# Create Meeting Note

Quickly capture meeting notes with the correct naming convention and basic structure.

## When to Use

- After a meeting or discussion that needs to be recorded
- When capturing quick ideas or brainstorming sessions
- When you need to document decisions, attendees, or action items

## Process

### Step 1: Gather Information

Ask the user for:
- **Meeting title** (what was discussed)
- **Date** (if not today)
- **Attendees** (optional)
- **Key discussion points** (brief notes)
- **Decisions made** (optional)
- **Action items** (optional, with owners)

### Step 2: Generate Filename

Format: `YYYYMMDD-title-of-the-note.md`

- Use today's date or the date provided
- Convert the meeting title to kebab-case (lowercase, hyphens between words)
- Keep it concise but descriptive

Example: `20260219-quarterly-planning-meeting.md`

### Step 3: Create the Note Structure

Create the file in `/notes/` with this structure:

```markdown
# [Meeting Title]

**Date:** [YYYY-MM-DD]
**Attendees:** [Name1, Name2, ...]

## Discussion Points

- Point 1
- Point 2
- Point 3

## Decisions Made

- Decision 1
- Decision 2

## Action Items

- [ ] Action 1 (@responsible-person, due: [date])
- [ ] Action 2 (@responsible-person, due: [date])

## Notes

[Additional context, quotes, or details]
```

### Step 4: Confirm Creation

- Display the created filename and path
- Ask if the user wants to add this to `tasklist/todo.md` immediately or process it later
- If action items exist, offer to create tasks from them

## Tips

- Keep action items clear with owner and due date
- Use @mentions for responsibility tracking
- If the meeting relates to a specific project, note that in the file or add a reference to the project folder
- Leave "Action Items" section empty if there are none, don't remove the section
