# Prabodhini GTD System — Getting Things Done
## A Markdown-Native, Sphere-Aligned, AI-Augmented Productivity Framework

---

> *"Your mind is for having ideas, not holding them."* — David Allen
>
> *"Anushasan begins with knowing exactly what you have committed to."* — JP tradition

---

## PHILOSOPHY: Why GTD for a Prabodhini Leader?

The Prabodhini formation created leaders who carry large commitments: professional excellence,
family responsibility, national contribution (SPG), and inner development. This creates a 
significant cognitive load — open loops across five spheres, multiple time horizons, and
commitments to many people.

GTD's core insight: **capture everything external to your mind**, so your mind is free for
the quality of thinking your formation prepared you for.

The Prabodhini adaptation adds three layers:
1. **Sphere tagging** — every task is anchored to one of the Five Spheres
2. **Horizon alignment** — tasks connect upward to Sankalpas and Svadharma
3. **AI delegation** — a new meta-layer where AI agents handle entire task classes

---

## THE FIVE GTD STEPS — Prabodhini Style

### Step 1: CAPTURE — Empty the Mind
*Collect everything that has your attention into a trusted external system.*

**The JP frame**: Unresolved open loops create exactly what Gita calls *Chinta* (worry-thought) —
the mental noise that prevents both Sadhana and Flow. Capture is an act of mental hygiene.

**How to capture**:
- Everything goes into `gtd/00-inbox.md` immediately
- Voice memo, quick note, forward an email — all land in the Inbox
- The only rule: capture it now, process it later
- **AI capture**: Use the AI Inbox/Review Agent workflow (see `ai-delegation/agent-inbox-review.md`) to forward emails,
  voice notes, and messages for auto-processing

### Step 2: CLARIFY — What Is This, and What Do I Do About It?

For each item in the Inbox, ask:

```
Is it actionable?
  └── NO → 
      ├── Trash (delete it)
        ├── Reference (store in your project notes or external reference system)
      └── Someday/Maybe (→ gtd/05-someday.md)
  └── YES →
      ├── Can it be done in < 2 minutes? → DO IT NOW
      ├── Should someone else do it? → DELEGATE (→ gtd/04-waiting-for.md)
      └── Will it take multiple steps? → PROJECT (→ gtd/02-projects.md)
      └── Single next action? → NEXT ACTIONS (→ gtd/01-next-actions.md)
```

**The AI Inbox/Review Agent** (`ai-delegation/agent-inbox-review.md`) can process your Inbox
items automatically, suggest classification, and draft project breakdowns.

### Step 3: ORGANISE — Put Things Where They Belong

**The Prabodhini GTD file structure:**

```
gtd/
├── 00-inbox.md          ← Everything lands here first
├── 01-next-actions.md   ← Single actions, tagged by sphere + context
├── 02-projects.md       ← Multi-step outcomes (index file)
├── projects/            ← One file per project
├── 04-waiting-for.md    ← Delegated items, awaiting response
├── 05-someday.md        ← Not now, but someday/maybe
└── 07-weekly-review.md  ← Weekly review template + history
```

Date-specific items should live in your calendar app. Reference material can live in project files
or your external notes system.

**Tagging system:**

| Tag | Meaning |
|-----|---------|
| `#atma` `#sangha` `#karma` `#samaj` `#sharira` | Five Sphere |
| `#quick` `#deep` `#meeting` `#call` | Energy/time required |
| `#ai-delegate` | Can be handled by an AI agent |
| `#coach-suggested` | Added by the AI coaching process |
| `#sankalpa` | Directly advances an active Sankalpa |
| `@home` `@office` `@anywhere` `@travel` | Context |

### Step 4: REFLECT — The Weekly Review

*The most important habit in the GTD system.*

Every Sunday (integrated into the Svadhyaya Review):
1. Process the Inbox to zero
2. Review all projects — does each have a Next Action?
3. Review Waiting For — follow up where needed
4. Review Someday — anything ready to activate?
5. Review calendar — what's coming in the next 2 weeks?
6. Set 3 Catalytic Priorities for the week

See `gtd/07-weekly-review.md` for the full template.

**The AI Inbox/Review Agent** (`ai-delegation/agent-inbox-review.md`) can pre-process the weekly
review, surface stalled projects, and suggest re-prioritisation.

### Step 5: ENGAGE — Do the Work with Full Presence

With a clean, trusted system, choosing what to do next becomes simple:
1. What sphere/context am I in? (filter by tag)
2. How much time do I have? (filter by duration)
3. What is my energy level? (high = deep work, low = quick tasks)
4. What will create the most significant impact? (Sankalpa alignment)

---

## THE SIX HORIZONS OF FOCUS

GTD works across six levels. The Prabodhini system maps these to its frameworks:

| GTD Horizon | GTD Term | Prabodhini Equivalent |
|------------|----------|----------------------|
| **Horizon 5** | Life Purpose | Svadharma + Vishwa Guru Vision |
| **Horizon 4** | Long-term Vision (3–5 years) | Five-year chapter title |
| **Horizon 3** | Goals (1–2 years) | Annual Sankalpas |
| **Horizon 2** | Areas of Focus | Five Spheres |
| **Horizon 1** | Projects | Active projects in each sphere |
| **Ground** | Next Actions | Today's and this week's specific tasks |

**The Prabodhini Alignment Rule**: Every project should trace upward to a Sphere,
which traces to an Annual Sankalpa, which traces to a Five-Year vision, which traces
to Svadharma. If a project can't be traced, it is a candidate for the Someday/Maybe list.

---

## AI COACH-INITIATED TASKS

> **Boundary rule**: The coaching queue (`gtd/_tasks/coach/00-coach-accepted.md`) holds **commitments the human mentee will act on**, proposed during coaching sessions. The delegation queue (`ai-delegation/`) holds **work the AI operational agents will perform autonomously**. A task like "Draft the SPG proposal intro section" belongs in delegation; "Review the draft and decide on the opening argument" belongs in the coaching queue.

The AI coaching process generates two types of tasks in the GTD system:

### Type 1: AI Coach-Suggested Actions
When the AI coach identifies something actionable from a session, it is entered directly into
the Inbox with the `#coach-suggested` tag and a note about context:

```markdown
- [ ] [AI-COACH] Have the difficult conversation with [person] about [topic]  
      #sangha #coach-suggested @office [From coaching session 2026-04-28]
```

### Type 2: Sankalpa-Linked Projects
Each Sankalpa becomes a Project in `gtd/02-projects.md` with a dedicated project file.
These are reviewed at every Weekly Review and in every coaching session.

---

## TASK ANATOMY

Every task in the Prabodhini GTD system follows this format:

```markdown
- [ ] [ACTION VERB + SPECIFIC OUTCOME] [due:DATE?] [~DURATION]
      #sphere #tags @context [source/note]
```

**Examples:**

```markdown
- [ ] Call Ravi to discuss Karnataka SPG water initiative  ~15min
      #samaj #call @anywhere [SPG: Clean Water Project]

- [ ] Write first draft of AI Ethics position paper for AICTE submission  due:2026-05-15 ~3hr
      #karma #deep #sankalpa @office [Annual Sankalpa: Thought Leadership]

- [ ] Schedule evening walk with spouse this week  ~immediate
      #sangha #quick @anywhere [Weekly Sankalpa: Sangha presence]

- [ ] [AI-DELEGATE] Research current AICTE AI policy landscape and summarise  #ai-delegate
      #karma @anywhere [Delegated to: Research Agent]
```

---

## INBOX PROCESSING CADENCE

| Frequency | What |
|-----------|------|
| **Daily** (morning) | Quick scan — anything urgent or date-specific? |
| **Daily** (evening) | Add anything captured during the day |
| **Weekly** (Sunday) | Full process to zero |
| **Monthly** | Project review + Someday review |

**The Inbox Zero principle**: The Inbox is a landing zone, not a storage system.
Processing it to zero is an act of respect for your commitments.

---

## MORNING IGNITION -> GTD ROUTING (COACH-ACCEPTED ITEMS)

Use this when a coaching conversation generates accepted commitments in the morning.

1. Convert accepted commitments from Morning Ignition into actionable lines.
2. Add them to `gtd/_tasks/coach/00-coach-accepted.md` (only leader-accepted AI coach items).
3. Split each item into one of two types:
      - Profile-completion task
      - Coaching-forward action
4. Process each accepted item into the right GTD list:
      - Single next step -> `gtd/01-next-actions.md` with `#coach-suggested`
      - Multi-step -> `gtd/02-projects.md`
      - Delegated -> `gtd/04-waiting-for.md`
      - Deferred -> `gtd/05-someday.md`
5. During the weekly review, clear or consciously re-commit any unprocessed coach-accepted items.
