# Project Administration

## 📂 Project Administration Overview

This directory serves as the **Central Brain** for project management, documentation, and task tracking. It is structured to be "Machine Readable," allowing an AI Agent to quickly parse current priorities, historical notes, and project-specific data.

### 🏗 Directory Structure

* **`/notes`**: Daily reflections, meeting minutes, and raw ideas.
* *Format:* `YYYYMMDD-title-of-the-note.md`
* *Subfolder `/processed`:* Archive for notes that have been converted into tasks or project documentation.


* **`/projects`**: Dedicated subdirectories for active workstreams. Each folder contains project-specific specs, stakeholders, and milestones.
* **`/tasklist`**: The command center.
* `todo.md`: The live list of all todo's accross the several projects.

---

## 🤖 AI Agent Instructions

When working within this directory, the AI Agent should adhere to the following protocols:

### 1. Context Awareness

Before suggesting new tasks, the Agent should reference `tasklist/todo.md` to ensure alignment with existing priorities. When asked about specific projects, the Agent should scan the corresponding folder in `/projects`.

### 2. Using Available Skills

Three custom skills are available to streamline common workflows:

- **`/create-meeting-note`** - Create structured meeting notes
- **`/process-notes-to-projects`** - Process notes and route tasks to projects
- **`/create-project-directory`** - Set up new project directories with standard structure

Use these skills when performing the corresponding tasks—they guide you through each process step-by-step.

### 3. Note Processing

If a note in `/notes` contains actionable items, use the `/process-notes-to-projects` skill to:

1. Extract the tasks and append them to `tasklist/todo.md`.
2. Summarize key takeaways into the relevant project folder.
3. Move the original file to `/notes/processed`.

### 4. File Naming Convention

All new files created by the Agent must follow the kebab-case format:

* *Correct:* `20240520-client-brief.md`
* *Incorrect:* `Client Brief May 20.md`

### 5. Creating New Projects

Use the `/create-project-directory` skill to set up new projects with a standardized structure that includes:
- `decisions/` - For design decisions and meeting notes
- `dropbox/` - For reference materials and resources
- `tasks/` - For task-specific notes and work logs
- `README.md` - Project overview with owner, stakeholders, timeline, and success criteria

---

## 🛠 Workflow Integration

| Action | Location | Skill | Responsibility |
| --- | --- | --- | --- |
| **Quick Capture** | `/notes` | - | User |
| **Create Meeting Note** | `/notes` | `/create-meeting-note` | AI/User |
| **Task Management** | `/tasklist/todo.md` | - | Joint (AI/User) |
| **Process Notes** | `/notes` → `/projects` | `/process-notes-to-projects` | AI |
| **Create Project** | `/projects/{project-name}` | `/create-project-directory` | AI (with user input) |
| **Deep Work** | `/projects/{project-name}` | - | Joint (AI/User) |
| **Archiving** | `/notes/processed` | - | AI (after verification) |

---

> **Note to AI:** You are a strategic partner. Do not just summarize; identify blockers, suggest next steps, and maintain the integrity of this organizational system.

