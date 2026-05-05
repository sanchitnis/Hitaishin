# 📋 INBOX TASKS PROCESSING GUIDE

## Folder Structure for `_tasks/`

```
_tasks/
├── emails/               # Email captures with extracted action items
├── meetings/             # Meeting minutes and summaries
├── notes/                # Ad-hoc notes and task lists
├── messages/             # Chat, Slack, message captures
├── json/                 # Processed JSON task files (auto-generated)
└── .archive/             # Processed raw files, organized by date
    └── 2026-05-xx/
```

---

## Processing Examples

### Example 1: EMAIL with Multiple Action Items

**Raw File**: `_tasks/emails/2026-05-05-project-kickoff.txt`
```
From: ramesh@company.com
Subject: Project Kickoff - Q2 Planning
Date: May 5, 2026

Hi, 

For the Q2 launch:
1. We need budget approval by May 15 - can you get this from finance?
2. Please review the technical architecture doc and share feedback by May 10
3. Schedule team kickoff meeting for May 12-13
4. Priya will handle vendor coordination

Deadline for full planning doc: May 20

Thanks,
Ramesh
```

**Processed JSON**: `_tasks/json/2026-05-05-email.json`
```json
{
  "source": "email",
  "source_file": "2026-05-05-project-kickoff.txt",
  "extracted_date": "2026-05-05",
  "sender": "ramesh@company.com",
  "subject": "Project Kickoff - Q2 Planning",
  "tasks": [
    {
      "id": 1,
      "task_title": "Get Q2 project budget approval from finance",
      "context": "Required for project kickoff",
      "priority": "high",
      "person": "ramesh@company.com",
      "deadline": "2026-05-15",
      "sphere": "professional",
      "next_action": "Email finance department with budget requirements",
      "processed": false
    },
    {
      "id": 2,
      "task_title": "Review and provide feedback on technical architecture doc",
      "context": "Q2 project planning",
      "priority": "high",
      "person": "ramesh@company.com",
      "deadline": "2026-05-10",
      "sphere": "professional",
      "next_action": "Request doc from Ramesh and review",
      "processed": false
    },
    {
      "id": 3,
      "task_title": "Schedule team kickoff meeting",
      "context": "Q2 launch planning",
      "priority": "medium",
      "person": "ramesh@company.com",
      "deadline": "2026-05-12",
      "sphere": "professional",
      "next_action": "Send calendar invites for May 12-13",
      "processed": false
    },
    {
      "id": 4,
      "task_title": "Prepare and submit full planning doc",
      "context": "Q2 project planning comprehensive document",
      "priority": "high",
      "person": "ramesh@company.com",
      "deadline": "2026-05-20",
      "sphere": "professional",
      "next_action": "Compile feedback, incorporate team input, finalize",
      "processed": false
    }
  ]
}
```

---

### Example 2: MEETING MINUTES (Extract Only Your Tasks)

**Raw File**: `_tasks/meetings/2026-05-04-team-sync.md`
```markdown
# Team Sync - May 4, 2026

**Attendees**: You, Priya, Ajay, Kavya

## Agenda

### Q2 Roadmap
- Priya: Will handle vendor negotiations and finalize contracts by May 20
- **You**: Review competitive analysis and prepare market positioning memo
- Ajay: Design mockups for new dashboard
- Kavya: Set up stakeholder interviews

### Infrastructure Updates
- **You**: Audit current server costs and recommend optimization
- Priya: Implement recommendations after your audit

### HR/Team
- Everyone: Submit availability for June offsite by May 8
- **You**: Lead discussion on team growth for next quarter

## Next Meeting
May 11, 2026
```

**Processed JSON**: `_tasks/json/2026-05-04-meeting.json`
```json
{
  "source": "meeting",
  "source_file": "2026-05-04-team-sync.md",
  "extracted_date": "2026-05-04",
  "meeting_title": "Team Sync",
  "meeting_date": "2026-05-04",
  "tasks": [
    {
      "id": 1,
      "task_title": "Review competitive analysis and prepare market positioning memo",
      "context": "Q2 Roadmap - Market positioning for new features",
      "priority": "high",
      "person": "Team meeting - direct assignment",
      "deadline": null,
      "sphere": "professional",
      "next_action": "Collect competitive data, draft memo structure, review with team",
      "processed": false
    },
    {
      "id": 2,
      "task_title": "Audit current server costs and recommend optimization",
      "context": "Infrastructure Updates - Priya will implement after audit",
      "priority": "high",
      "person": "Team meeting - direct assignment",
      "deadline": null,
      "sphere": "professional",
      "next_action": "Gather cost data, analyze trends, create recommendations doc",
      "processed": false
    },
    {
      "id": 3,
      "task_title": "Submit availability for June offsite",
      "context": "Team coordination",
      "priority": "medium",
      "person": "Team meeting - all attendees",
      "deadline": "2026-05-08",
      "sphere": "professional",
      "next_action": "Check calendar and submit dates",
      "processed": false
    },
    {
      "id": 4,
      "task_title": "Lead discussion on team growth for next quarter",
      "context": "HR/Team - Leadership responsibility",
      "priority": "medium",
      "person": "Team meeting - direct assignment",
      "deadline": null,
      "sphere": "professional",
      "next_action": "Prepare talking points on hiring needs, capacity, growth areas",
      "processed": false
    }
  ]
}
```

**Note**: Tasks assigned to others (Priya, Ajay, Kavya) are NOT extracted. Only your tasks are included.

---

### Example 3: NOTES/CHECKLIST

**Raw File**: `_tasks/notes/2026-05-05-strategic-planning.md`
```markdown
# Strategic Planning - Personal Development

- [ ] Schedule quarterly review with mentor (related to Svadharma Navigator work)
- [ ] Finalize next quarter's learning goals - focus on systems thinking
- [ ] Review Paristhiti Jnana assessment results
- [ ] Write reflection on last quarter's performance
- [ ] Update 5-year plan with new insights
- [ ] Research and sign up for leadership coaching program
```

**Processed JSON**: `_tasks/json/2026-05-05-notes.json`
```json
{
  "source": "notes",
  "source_file": "2026-05-05-strategic-planning.md",
  "extracted_date": "2026-05-05",
  "tasks": [
    {
      "id": 1,
      "task_title": "Schedule quarterly review with mentor",
      "context": "Personal development and Svadharma alignment",
      "priority": "high",
      "person": "Self-assigned",
      "deadline": null,
      "sphere": "spiritual",
      "next_action": "Contact mentor and propose 3 meeting times",
      "processed": false
    },
    {
      "id": 2,
      "task_title": "Finalize next quarter's learning goals",
      "context": "Focus on systems thinking and Paristhiti Jnana",
      "priority": "high",
      "person": "Self-assigned",
      "deadline": null,
      "sphere": "spiritual",
      "next_action": "Review current skills, identify gaps, set 3-4 concrete goals",
      "processed": false
    },
    {
      "id": 3,
      "task_title": "Review Paristhiti Jnana assessment results",
      "context": "Personal development assessment",
      "priority": "medium",
      "person": "Self-assigned",
      "deadline": null,
      "sphere": "spiritual",
      "next_action": "Request results and analyze findings",
      "processed": false
    },
    {
      "id": 4,
      "task_title": "Write reflection on last quarter's performance",
      "context": "Self-study and accountability",
      "priority": "medium",
      "person": "Self-assigned",
      "deadline": null,
      "sphere": "personal",
      "next_action": "Schedule 2-hour block, write comprehensive reflection",
      "processed": false
    },
    {
      "id": 5,
      "task_title": "Update 5-year plan with new insights",
      "context": "Long-term Svadharma planning",
      "priority": "medium",
      "person": "Self-assigned",
      "deadline": null,
      "sphere": "spiritual",
      "next_action": "Review current plan, incorporate new learnings, revise goals",
      "processed": false
    },
    {
      "id": 6,
      "task_title": "Research and sign up for leadership coaching program",
      "context": "Professional development",
      "priority": "high",
      "person": "Self-assigned",
      "deadline": null,
      "sphere": "professional",
      "next_action": "Search programs, compare options, check costs and availability",
      "processed": false
    }
  ]
}
```

---

## Quick Reference: Critical Rules

### ✅ DO
- ✅ Capture **verbatim** from source
- ✅ Extract **only your tasks** from meetings
- ✅ Include **context** and **deadline** if mentioned
- ✅ Use **clear, actionable** language
- ✅ Categorize by **sphere** (professional, personal, family, spiritual, national)
- ✅ Mark **priority** based on deadline and importance
- ✅ Archive raw files after processing

### ❌ DON'T
- ❌ Extract tasks assigned to others (except FYI or dependency)
- ❌ Leave ambiguous task descriptions
- ❌ Add your own interpretation—stick to source
- ❌ Forget to update `processed: true` after completing
- ❌ Leave raw files in active folders after extraction

---

## Workflow Steps (Checklist)

1. **Save** raw file to appropriate folder (`emails/`, `meetings/`, `notes/`, `messages/`)
2. **Create** JSON file in `_tasks/json/` with extracted tasks
3. **Review** each task:
   - [ ] Clear description?
   - [ ] Correct sphere?
   - [ ] Deadline noted?
   - [ ] Is it actionable?
4. **Process** each task to GTD list:
   - [ ] Actionable → `01-next-actions.md`
   - [ ] Multi-step → `02-projects.md`
   - [ ] Waiting → `04-waiting-for.md`
   - [ ] Someday → `05-someday.md`
   - [ ] Reference → `references/`
5. **Update** JSON: `"processed": true`
6. **Archive** raw file to `_tasks/.archive/YYYY-MM-DD/`

---

*Last updated: May 5, 2026*
