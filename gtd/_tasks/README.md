# 📁 _TASKS — Raw Item Processing Center

This folder captures and processes raw items (emails, meeting minutes, notes, messages) into structured tasks for your GTD system.

## Folder Organization

| Folder | Purpose |
|--------|---------|
| `emails/` | Email captures with action items |
| `meetings/` | Meeting minutes and summaries |
| `notes/` | Ad-hoc notes, checklists, task lists |
| `messages/` | Chat, Slack, or message captures |
| `coach/` | Hitaishin AI coach-suggested tasks accepted by the leader |
| `json/` | **AUTO**: Processed task files in JSON format |
| `.archive/` | **AUTO**: Raw files moved here after processing |

## Quick Start

### 1. Save Raw Files
```
For an email:     _tasks/emails/2026-05-05-subject.txt
For a meeting:    _tasks/meetings/2026-05-05-meeting-title.md
For notes:        _tasks/notes/2026-05-05-title.md
For messages:     _tasks/messages/2026-05-05-person.txt
For coach tasks:  _tasks/coach/00-coach-accepted.md (rolling accepted queue)
```

### 2. Process & Extract
- Review the raw file
- Extract **only your actionable items**
- For meetings: extract **only tasks assigned to you**
- Create a JSON file in `json/` folder with extracted tasks

### 3. Use Template
See `TEMPLATE-task.json` for the JSON structure. Copy this format for each extraction.

### 4. Process Tasks
Each extracted task goes to GTD list:
- **Actionable?** → `01-next-actions.md`
- **Multi-step?** → `02-projects.md`
- **Delegated?** → `04-waiting-for.md`
- **Someday?** → `05-someday.md`
- **Reference only?** → `references/`

For coach tasks, process only **leader-accepted AI coach** items from `coach/00-coach-accepted.md`.
If needed, also write a structured JSON capture into `json/` with `source: "ai-coach"`.

### 5. Archive Raw File
After processing all tasks from a file:
1. Update the JSON: mark `"processed": true`
2. Move raw file to `.archive/YYYY-MM-DD/` folder
3. Keep JSON file in `json/` for reference

## Detailed Processing Guide

👉 See [INBOX-TASKS-PROCESSING.md](INBOX-TASKS-PROCESSING.md) for:
- Detailed examples for each file type
- Rules for different sources
- Meeting minutes extraction best practices
- Processing workflow checklist

## Key Rules

### ✅ DO Extract
- All explicit action items
- Implied commitments you made
- Deadlines and context
- **Your tasks only** (from meetings)

### ❌ DON'T Extract
- Tasks assigned to others
- FYI-only information
- Completed items
- Vague or non-actionable statements

---

*Last Updated: May 5, 2026*
