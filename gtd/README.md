# `gtd/` — Getting Things Done System

**Primary audience: Users (mentees) using the task system · Developers extending or automating it**

---

## What This Folder Contains

The `gtd/` folder is a complete **Getting Things Done (GTD)** implementation using only Markdown files — no app required, no subscription, no sync conflicts. It is designed specifically for the Prabodhini leader balancing commitments across five life spheres.

```
gtd/
├── GTD-GUIDE.md              ← Complete system guide — read this first
├── 00-inbox.md               ← Everything lands here first
├── 01-next-actions.md        ← Single next actions, tagged by sphere
├── 02-projects.md            ← Multi-step project index
├── 04-waiting-for.md         ← Delegated items (human + AI)
├── 05-someday.md             ← Deferred aspirations
├── 07-weekly-review.md       ← Weekly review template (copy per week)
└── projects/
    └── _project-template.md  ← Template for individual project files
```

*(Note: file numbers follow GTD's list naming convention; `03-calendar` and `06-reference` are intentionally omitted — use your calendar app and a reference folder respectively.)*

---

## For Users: Getting Started

### The one-sentence explanation of GTD

Write down everything you need to do, decide what each item actually requires, put it in the right place, and review the whole system weekly. Your mind then stays clear for thinking, not remembering.

### Reading order

1. **Read `GTD-GUIDE.md` first** — it explains the five steps and how they've been adapted for the Prabodhini context
2. **Set up your inbox** — start capturing in `00-inbox.md` immediately (don't wait to understand the whole system)
3. **Process once** — work through your Inbox and populate `01-next-actions.md` and `02-projects.md`
4. **Do your first weekly review** — use `07-weekly-review.md` on Sunday

### The three Prabodhini innovations on top of standard GTD

**1. Sphere tagging**
Every task and project carries a sphere tag. This lets you see at a glance whether your action list is sphere-balanced or dominated by one domain.

```markdown
- [ ] Call Ravi about SPG water project  #samaj @anywhere ~15min
- [ ] Write the AICTE position paper section 2  #karma @office ~3hr
- [ ] Walk with spouse this evening — no phones  #sangha @home
```

**2. Sankalpa alignment**
Projects trace upward to Sankalpas (conscious commitments) which trace to the Five-Year Vision which traces to Svadharma. If a project can't be traced, it belongs in Someday/Maybe.

**3. AI delegation**
Tasks the AI can handle get the `#ai-delegate` tag and are routed to the `ai-delegation/` folder rather than staying on your human to-do list.

### Daily workflow

**Morning (2 min)**: Scan `01-next-actions.md` — what are today's 1–3 catalytic actions?

**During the day**: Capture anything new in `00-inbox.md` — one line, don't organise yet.

**Evening (5 min)**: Move today's captures from inbox to the right list; mark completed items `[x]`.

**Sunday (45–60 min)**: Full weekly review using `07-weekly-review.md`.

### The two-minute rule

If a captured item takes less than 2 minutes to do — do it immediately, don't put it on a list.

### What to do when the system feels overwhelming

This always happens. The fix is always the same: **process your inbox**. When in doubt, start there.

If the whole system feels too heavy, run the Minimum Viable GTD:
1. Keep only `00-inbox.md` (capture) and `01-next-actions.md` (what to do)
2. Do a 20-minute Sunday triage instead of the full weekly review
3. Add complexity back gradually as the habit forms

---

## For Developers: Extending the GTD System

### The design philosophy

The GTD system is intentionally **plain Markdown** — this was a deliberate constraint. Why:

- Works with any editor (Obsidian, VS Code, Typora, vim, GitHub web editor)
- No vendor lock-in, no subscription risk
- Files are human-readable without any tooling
- Easy to version control with git
- Easy to parse and extend programmatically

### File format conventions

**Task format:**
```markdown
- [ ] [ACTION VERB] [SPECIFIC OUTCOME] [due:YYYY-MM-DD?] [~DURATION]
      #sphere #tags @context [optional note]
```

**Completed task:**
```markdown
- [x] [ACTION] — completed YYYY-MM-DD
```

**AI coach-suggested task:**
```markdown
- [ ] [AI-COACH] [ACTION] [context]  #sphere #coach-suggested
```

**AI-delegated task:**
```markdown
- [ ] [AI-DELEGATE] [TASK] — see ai-delegation/agent-[name].md
      Agent: Research Agent | Due: YYYY-MM-DD  #ai-delegate #sphere
```

### Parsing tasks programmatically

Tasks follow a consistent pattern that can be extracted with regex or a Markdown parser:

```python
import re

# Match uncompleted tasks
TASK_PATTERN = re.compile(
    r'^- \[ \] (.+?)(?:\s+due:(\d{4}-\d{2}-\d{2}))?(?:\s+~(\w+))?$',
    re.MULTILINE
)

# Extract sphere tags
SPHERE_PATTERN = re.compile(r'#(atma|sangha|karma|samaj|sharira)')

# Extract special flags
AI_DELEGATE = re.compile(r'\[AI-DELEGATE\]')
COACH_SUGGESTED = re.compile(r'#coach-suggested')
SANKALPA_LINKED = re.compile(r'#sankalpa')

# Convention: #coach-suggested indicates tasks suggested by the AI coach agent
# (Copilot/AI/Gemini), not a human coach.
```

### Potential automation scripts (good first contributions)

These scripts would be valuable additions — see the `CONTRIBUTING.md` for how to contribute:

**`scripts/gtd-inbox-process.py`**
Parse `00-inbox.md` and interactively prompt classification → automatically append to the right list file.

**`scripts/gtd-weekly-summary.py`**
Count tasks by sphere, identify stalled projects (no movement in 7+ days), generate a pre-populated weekly review file with stats already filled in.

**`scripts/gtd-sphere-balance.py`**
Read all task files, count active tasks by sphere tag, output a balance report showing sphere distribution vs. target allocation.

**`scripts/gtd-sankalpa-trace.py`**
For each active project, check whether it has a `[Sankalpa]` link. Flag orphaned projects that can't be traced to a Sankalpa.

**`scripts/gtd-ai-queue.py`**
Find all `#ai-delegate` tasks across files, format them as a delegation batch, and output the input format for the relevant agent.

**`scripts/gtd-archive.py`**
Move completed tasks from all files into a `gtd/archive/YYYY-MM.md` file at month end.

### Obsidian integration

The folder works natively with [Obsidian](https://obsidian.md/) — open the whole `hitaishin/` folder as an Obsidian vault. Useful plugins:
- **Tasks** — renders checkboxes as interactive task objects with due dates and filters
- **Dataview** — query tasks across files with SQL-like syntax (e.g., all `#samaj` tasks due this week)
- **Calendar** — visual weekly/monthly calendar view integrated with tasks

**Example Dataview query for your Obsidian dashboard:**
```dataview
TASK
FROM "gtd"
WHERE !completed AND contains(tags, "#samaj")
SORT due ASC
```

### VS Code integration

The [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) extension highlights `- [ ]` and `- [x]` items across files. Recommended workspace settings:

```json
{
  "todo-tree.general.tags": ["TODO", "[ ]", "[x]", "COACH", "AI-DELEGATE"],
  "todo-tree.highlights.customHighlight": {
    "COACH": { "foreground": "#E8720C" },
    "AI-DELEGATE": { "foreground": "#4A7C59" }
  }
}
```

### Sync options

| Option | Best for | Notes |
|--------|---------|-------|
| iCloud Drive | Apple users | Seamless, invisible |
| Dropbox | Cross-platform | Free tier sufficient |
| GitHub private repo | Developers | Git history = natural audit trail |
| Obsidian Sync | Obsidian users | Paid but purpose-built |
| Syncthing | Privacy-first | Self-hosted, no cloud |
