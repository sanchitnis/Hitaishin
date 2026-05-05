# 📥 INBOX — Capture Everything Here First
*Last processed: [DATE] | Items: 0*

> **Rule**: Don't organise — just capture. Process during daily scan or weekly review.
> **AI Inbox Agent**: Forward emails/voice notes to auto-capture. See `ai-delegation/agent-inbox.md`
> **New**: Raw tasks from emails/meetings/notes → process in `_tasks/` subfolder → extract to JSON

---

## 🆕 UNPROCESSED ITEMS

*Add new items here. One line each. Process → move to right list.*

- 

---

## 📁 RAW TASKS PROCESSING — `_tasks/` Subfolder

Process raw items (emails, meeting minutes, notes) by moving them to the `_tasks/` folder, extracting tasks, and converting to structured JSON format.

### How It Works

1. **Capture**: Save raw files in `_tasks/` (emails, PDFs, meeting notes, text files, etc.)
2. **Extract**: Pull actionable tasks from each file
3. **Standardize**: Convert to JSON format with required fields
4. **Process**: Move JSON files to `01-next-actions.md` or other lists

### Supported File Types

| Type | Location | Action | Output |
|------|----------|--------|--------|
| **Email** | `_tasks/emails/[date]-[subject].txt` | Extract all action items | `_tasks/json/[date]-email.json` |
| **Meeting Minutes** | `_tasks/meetings/[date]-[title].md` | Extract **ONLY YOUR TASKS** | `_tasks/json/[date]-meeting.json` |
| **Notes/Lists** | `_tasks/notes/[date]-[title].md` | Extract all tasks | `_tasks/json/[date]-notes.json` |
| **Chat/Message** | `_tasks/messages/[date]-[person].txt` | Extract action items | `_tasks/json/[date]-message.json` |
| **AI-Coach-Accepted** | `_tasks/coach/00-coach-accepted.md` | Extract only leader-accepted AI coach tasks | `_tasks/json/[date]-ai-coach.json` |

### JSON Task Format

Each extracted task becomes a JSON file with this structure:

```json
{
  "source": "email|meeting|notes|message|ai-coach",
  "source_file": "[original-filename]",
  "extracted_date": "YYYY-MM-DD",
  "tasks": [
    {
      "id": 1,
      "task_title": "Clear, actionable task description",
      "context": "Brief context from original",
      "priority": "high|medium|low",
      "person": "Name if from meeting/email",
      "deadline": "YYYY-MM-DD or null",
      "sphere": "professional|personal|family|spiritual|national",
      "next_action": "Next concrete step",
      "processed": false
    }
  ]
}
```

### Processing Rules

#### For Emails
- Capture sender, subject, date
- Extract all action items (explicit or implied)
- Note any deadlines mentioned
- Categorize by sphere

#### For Meeting Minutes
- **Only extract YOUR tasks** (tasks assigned to you, commitments you made)
- Ignore tasks for other participants
- Capture: owner, deadline, dependencies
- Include context if dependent on someone else's task

#### For Notes/Lists
- Convert list items to structured tasks
- Identify priority and deadlines
- Link to projects if applicable
- Categorize by sphere

#### For Messages/Chat
- Extract explicit action requests
- Note sender and context
- Include timestamp
- Mark urgency based on tone/context

#### For AI-Coach-Accepted Tasks
- Add only tasks explicitly accepted by the leader
- Include profile-completion tasks if they advance coaching readiness
- Tag for coaching traceability (`#coach-suggested` when moved to next actions; AI coach source)
- Prefer one clear next action per accepted commitment

### Processing Workflow

1. **Save raw file** in appropriate `_tasks/[type]/` subfolder
2. **Review content** and identify tasks
3. **Create JSON** with extracted tasks using format above
4. **Save JSON** in `_tasks/json/` with pattern: `YYYY-MM-DD-[source-type].json`
5. **Process each task**:
   - Is it actionable? → Move to `01-next-actions.md` (mark source)
   - Is it a project? → Move to `02-projects.md`
   - Should delegate? → Move to `04-waiting-for.md`
   - Is it someday? → Move to `05-someday.md`
   - Reference only? → Move to `references/` (with link)
6. **Mark processed**: Update `processed: true` in JSON
7. **Archive raw file**: Move to `_tasks/.archive/[YYYY-MM-DD]/` after processing

---

## 📌 PROCESSING LOG

| Date | Items Captured | Items Processed | Time Taken |
|------|---------------|-----------------|-----------|
| | | | |

---

*When processing, ask:*
*Actionable? → Next Action / Project / Delegate*
*Not actionable? → Reference / Someday / Trash*
