# 📥 UPDATED INBOX SYSTEM — Architecture Overview

**Last Updated**: May 5, 2026

---

## 🎯 What Changed

Your inbox system now supports **structured processing of raw items** (emails, meeting minutes, notes, messages) into your GTD workflow.

### Before
- Raw items captured as one-liners in `00-inbox.md`
- Manual processing without structure
- Hard to track complex tasks from multiple sources

### After
- Raw files organized in `_tasks/` subfolder by type
- Automated JSON extraction with required fields
- Clear processing pipeline to GTD lists
- Complete audit trail with archiving

---

## 📁 New Folder Structure

```
gtd/
├── 00-inbox.md                           # ← Updated with new _tasks workflow
├── INBOX-TASKS-PROCESSING.md             # ← NEW: Detailed processing guide with examples
├── INBOX-QUICK-CHECKLIST.md              # ← NEW: Quick reference checklist
├── 01-next-actions.md
├── 02-projects.md
├── 04-waiting-for.md
├── 05-someday.md
├── GTD-GUIDE.md
├── README.md
├── _tasks/                               # ← NEW: Raw item processing center
│   ├── README.md                         # ← NEW: Quick start guide
│   ├── TEMPLATE-task.json                # ← NEW: JSON template
│   ├── emails/                           # Email captures
│   ├── meetings/                          # Meeting minutes
│   ├── notes/                             # Ad-hoc notes and checklists
│   ├── messages/                          # Chat, Slack, messages
│   ├── json/                              # Processed JSON task files
│   │   └── 2026-05-05-email.json          # Example
│   └── .archive/                          # Archived raw files
│       └── 2026-05-xx/
└── projects/
    └── _project-template.md
```

---

## 🔄 Processing Workflow

```
Raw Input
    ↓
Save to _tasks/[type]/
    ↓
Read & Extract Tasks (only YOUR tasks from meetings)
    ↓
Create JSON file in _tasks/json/
    ↓
Process Each Task
    ├─ Actionable? → 01-next-actions.md or 02-projects.md
    ├─ Waiting? → 04-waiting-for.md
    ├─ Someday? → 05-someday.md
    └─ Reference? → references/
    ↓
Mark JSON "processed": true
    ↓
Archive raw file to _tasks/.archive/YYYY-MM-DD/
```

---

## 📋 JSON Task Format

Every extracted task is stored with this structure:

```json
{
  "source": "email|meeting|notes|message",
  "source_file": "[original-filename]",
  "extracted_date": "YYYY-MM-DD",
  "sender_or_meeting": "Contact or meeting name",
  "subject_or_title": "Subject line or meeting title",
  "tasks": [
    {
      "id": 1,
      "task_title": "Clear, actionable description",
      "context": "Why this matters, background",
      "priority": "high|medium|low",
      "person": "Who is asking / assigning",
      "deadline": "YYYY-MM-DD or null",
      "sphere": "professional|personal|family|spiritual|national",
      "next_action": "First concrete step",
      "processed": false  // ← Change to true after handling
    }
  ]
}
```

---

## 🚀 Getting Started

### Today (5 min setup)
1. ✅ Review the new `_tasks/` folder structure
2. ✅ Read `_tasks/README.md` for quick start
3. ✅ Save `_tasks/TEMPLATE-task.json` as your reference

### This Week (processing)
1. Capture raw items: emails, meeting minutes, notes → `_tasks/[type]/`
2. Extract tasks → Create JSON in `_tasks/json/`
3. Process each task to GTD list
4. Archive raw files

### Key Resources
- 📖 **Detailed Guide**: `INBOX-TASKS-PROCESSING.md` (examples, rules, best practices)
- ⚡ **Quick Ref**: `INBOX-QUICK-CHECKLIST.md` (step-by-step checklist)
- 📁 **Quick Start**: `_tasks/README.md` (folder purpose, workflow)
- 📄 **Main Inbox**: `00-inbox.md` (updated with new sections)

---

## 🎓 Example Workflow

### Scenario: You receive an email + attend meeting + have notes

**Friday May 5, 10 AM**

1. **Email arrives** from project lead
   - Save to: `_tasks/emails/2026-05-05-project-update.txt`

2. **Meeting happens** 2pm
   - Take minutes: `_tasks/meetings/2026-05-05-team-sync.md`

3. **Late Friday** - Processing time (30 min)
   - Extract email tasks → `_tasks/json/2026-05-05-email.json` (4 tasks)
   - Extract meeting tasks → `_tasks/json/2026-05-05-meeting.json` (3 tasks)
   - Move personal notes → `_tasks/notes/2026-05-05-personal.md`
   - Extract personal tasks → `_tasks/json/2026-05-05-notes.json` (2 tasks)

4. **Process each task** (15-20 min)
   ```
   9 total tasks extracted
   - 5 tasks → 01-next-actions.md
   - 2 tasks → 02-projects.md (multi-step)
   - 1 task → 04-waiting-for.md (waiting on approval)
   - 1 task → 05-someday.md
   ```

5. **Archive**
   - Update JSON files: mark `processed: true`
   - Move raw files: email, meeting notes → `_tasks/.archive/2026-05-05/`

**Result**: Raw items → Structured JSON → Integrated into GTD → Archived

---

## 🔍 Key Differences by Source Type

| Type | What to Extract | Key Rule |
|------|-----------------|----------|
| **Email** | All action items mentioned | Include sender, deadline, context |
| **Meeting** | **Only YOUR tasks** | Ignore tasks for others |
| **Notes** | All checklist items, to-dos | Include priority and category |
| **Messages** | Explicit action requests | Note urgency and sender |

---

## ⏰ Time Estimates

- **Capturing raw item**: 1-2 min
- **Extracting tasks**: 2-5 min
- **Creating JSON**: 3-8 min
- **Processing to GTD**: 5-10 min
- **Archiving**: 1-2 min
- **Total per item**: ~12-27 minutes

### Efficient Batching
Process in batches: all emails together, all meetings together. Saves context switching time.

---

## 💡 Pro Tips

1. **Meeting minutes**: Use a consistent template (see INBOX-TASKS-PROCESSING.md)
2. **Deadlines**: Always check for dates mentioned (explicit or implied)
3. **Sphere mapping**: Use professional/personal/family/spiritual/national consistently
4. **Batch processing**: Set aside 2-3 hours weekly for full processing cycle
5. **Archive weekly**: Don't let `_tasks/` get cluttered—move processed files out
6. **JSON backup**: Keep JSON files as searchable record of what was extracted

---

## 🔗 Connected Files

- **Main Inbox**: [00-inbox.md](00-inbox.md)
- **Processing Guide**: [INBOX-TASKS-PROCESSING.md](INBOX-TASKS-PROCESSING.md)
- **Quick Checklist**: [INBOX-QUICK-CHECKLIST.md](INBOX-QUICK-CHECKLIST.md)
- **Next Actions**: [01-next-actions.md](01-next-actions.md)
- **Projects**: [02-projects.md](02-projects.md)
- **Waiting For**: [04-waiting-for.md](04-waiting-for.md)
- **AI Delegation**: [../ai-delegation/agent-inbox-review.md](../ai-delegation/agent-inbox-review.md)

---

## ❓ FAQ

**Q: Where do quick one-liners go?**
A: Still in `00-inbox.md` → UNPROCESSED ITEMS section. The `_tasks/` folder is for complex items requiring extraction.

**Q: What if a task comes from multiple sources?**
A: Create separate entries in separate JSON files (one per source). Link them in the GTD list if interdependent.

**Q: How long should I keep raw files in archive?**
A: At least 1 month. After that, delete and keep only the JSON in `json/` folder for reference.

**Q: Can I skip the JSON step?**
A: For very simple items, yes. JSON is valuable when you need structured extraction, tracking, or when tasks are complex.

**Q: Who processes the tasks?**
A: You during daily scan (quick processing) or weekly review (deep dive). AI agents can assist with email filtering/routing.

---

## 📊 Processing Metrics (for Weekly Review)

Track these in your `00-inbox.md` Processing Log:
- **Items captured** (by type: emails, meetings, notes, messages)
- **Tasks extracted** (total count)
- **Time spent** (minutes)
- **Distribution** to GTD lists (% next-actions, projects, waiting, someday)
- **Sphere distribution** (how many professional vs personal vs spiritual tasks)

---

*System Updated: May 5, 2026*
*Created by: Hitaishin AI Coaching OS*
