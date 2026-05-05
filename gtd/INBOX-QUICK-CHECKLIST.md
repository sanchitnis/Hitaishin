# ⚡ INBOX TASK PROCESSING — Quick Checklist

**Use this during daily processing of items in `_tasks/` folder**

---

## Step 1: Receive & Capture
- [ ] Save email/meeting/notes to appropriate `_tasks/[type]/` folder
- [ ] Use naming: `YYYY-MM-DD-[description].txt` or `.md`
- [ ] Include full content (sender, subject, date, attendees, etc.)

---

## Step 2: Extract Tasks (Read Raw File)
- [ ] Identify all action items
- [ ] For meetings: **extract only YOUR tasks**
- [ ] Note deadlines, dependencies, context
- [ ] Identify person/team requesting task

---

## Step 3: Create JSON File
- [ ] Copy `TEMPLATE-task.json`
- [ ] Fill in `source_file`, `extracted_date`, `sender_or_meeting`, `subject_or_title`
- [ ] For each task:
  - [ ] Clear title (action verb + object)
  - [ ] Brief context
  - [ ] Priority: high/medium/low
  - [ ] Deadline (if mentioned)
  - [ ] Sphere: professional|personal|family|spiritual|national
  - [ ] Next action (concrete first step)
  - [ ] Mark `"processed": false` initially
- [ ] Save as `_tasks/json/YYYY-MM-DD-[source-type].json`

---

## Step 4: Process Each Task to GTD List

For each task in the JSON:

```
Is it ACTIONABLE?
  └─ YES: 
      Does it need multiple steps?
      ├─ YES → Add to 01-next-actions.md (mark as Project)
      └─ NO  → Add to 01-next-actions.md (single task)
      
  └─ NO:
      Is it valuable for future?
      ├─ YES → 05-someday.md
      └─ NO  → Delete / Trash
      
Is someone else responsible?
  └─ YES → 04-waiting-for.md (with your due date)
```

- [ ] Task 1: Determined GTD location & moved
- [ ] Task 2: Determined GTD location & moved
- [ ] Task 3: Determined GTD location & moved
- [ ] (Continue for all tasks)

---

## Step 5: Update & Archive

- [ ] Update JSON: mark all tasks `"processed": true`
- [ ] Move raw file to `_tasks/.archive/YYYY-MM-DD/`
- [ ] Delete from active source folder

---

## Time Tracking

| Step | Estimated Time |
|------|----------------|
| Step 1 (Capture) | 1-2 min |
| Step 2 (Extract) | 2-5 min |
| Step 3 (JSON) | 3-8 min |
| Step 4 (GTD) | 5-10 min |
| Step 5 (Archive) | 1-2 min |
| **Total per item** | **12-27 min** |

### Tips for Speed
- Extract multiple items in one session
- Use keyboard shortcuts to copy-paste between files
- Process in batches by type (all emails, then all meetings)

---

## Processing Log Entry Template

Add this to `00-inbox.md` Processing Log:

| Date | Items Captured | Items Processed | Time Taken |
|------|---------------|-----------------|-----------|
| 2026-05-05 | 3 emails, 1 meeting, 2 notes | 8 tasks | 45 min |

---

## Common Mistakes to Avoid

| ❌ Mistake | ✅ Solution |
|-----------|-----------|
| Extracting others' tasks from meetings | Re-read minutes, filter for YOUR name/role |
| Vague task titles ("Review something") | Make specific: "Review Q2 budget spreadsheet and provide feedback" |
| Skipping deadline field | Check email/meeting for dates mentioned or implied |
| Not archiving raw files | Set reminder to move to `.archive/` weekly |
| Forgetting to mark `processed: true` | Make this the last step before archiving |
| Mixing personal & professional in one JSON | Keep sources separate even if same date |

---

*Last Updated: May 5, 2026*
