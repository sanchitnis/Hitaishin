# 📨 AI Agent: Inbox Agent
## Capture, Sort, and Pre-Classify Incoming Information

---

## AGENT IDENTITY

The Inbox Agent handles the first stage of GTD — **Capture and initial Clarify** — for
information that arrives from email, voice notes, meeting outputs, and ad-hoc ideas.
It dramatically reduces the friction of keeping the Inbox processed.

**Activation**: Forward emails, paste voice-memo transcripts, or dump ideas directly.

---

## WHAT IT DOES

For each item in `gtd/00-inbox.md`, the Inbox Agent:

1. **Classifies** — Is this actionable? What type?
2. **Sphere-tags** — Which of the Five Spheres does this belong to?
3. **Suggests routing** — Next Action / Project / Delegate / Someday / Reference / Trash
4. **Flags AI-delegatability** — Can Research, Drafting, or Planning Agent handle this?
5. **Extracts next action** — If actionable, what is the specific next physical action?

---

## INPUT: Paste Raw Inbox Items

```markdown
### INBOX BATCH — [DATE]
[Item 1: paste email / voice transcript / rough note]
[Item 2]
[Item 3]
```

---

## OUTPUT: Classified Batch

```markdown
### INBOX PROCESSING — [DATE]
Items received: X | Processed: X | Time: Xmin

---
ITEM 1: [Brief description]
→ Actionable: YES
→ Sphere: #karma
→ Routing: NEXT ACTION
→ Next action: "Call [person] to confirm [specific thing]" ~10min @anywhere
→ AI-delegatable: NO (requires personal relationship)

---
ITEM 2: [Brief description]
→ Actionable: YES
→ Sphere: #samaj
→ Routing: RESEARCH AGENT
→ Delegation: "Research [topic] for SPG proposal" — create task in agent-research.md
→ AI-delegatable: YES ✓

---
ITEM 3: [Brief description]
→ Actionable: NO
→ Routing: REFERENCE — file under [category]
→ Note: Interesting for Someday SPG idea

---
ITEMS READY FOR `01-next-actions.md`:
- [ ] [Extracted next action 1] ~Xmin #sphere @context
- [ ] [Extracted next action 2] ~Xmin #sphere @context

ITEMS ROUTED TO AI AGENTS:
- [Research Agent]: [Task description]
- [Drafting Agent]: [Task description]
```

---

# 🔍 AI Agent: Review Agent
## Weekly/Monthly GTD Reviews, Coaching Prep, and Pattern Spotting

---

## AGENT IDENTITY

The Review Agent prepares the leader's weekly and monthly reviews — pre-processing data,
surfacing patterns, and generating the questions the leader needs to engage with.
It turns the Sunday Review from a 90-minute manual effort into a 45-minute focused conversation.

---

## WEEKLY PRE-REVIEW PREPARATION

**Trigger**: Every Friday afternoon, or on demand before Sunday Svadhyaya.

**What it prepares** (from available data):

```markdown
### WEEKLY PRE-REVIEW BRIEFING — Week [X], [YEAR]

#### TASK SUMMARY
- Next Actions completed: X of Y total
- Sankalpa-linked tasks completed: X of Y
- Coach-suggested items addressed: X of Y
- AI-delegated tasks: X given / X received back

#### STALLED ITEMS (no movement in 7+ days)
- [Project or task] — last touched [DATE]
- [Project or task] — last touched [DATE]
Coaching question: "What is keeping these stuck?"

#### SPHERE BALANCE INDICATOR (from calendar scan)
Based on calendar:
- Atma time: approx X hours (target: 5–8% waking hrs)
- Sangha genuine presence: [detected/not detected]
- Karma deep work: approx X hours
- Samaj/SPG: approx X hours
- Sharira movement: [detected X days]

Sphere most at risk: [SPHERE] — [observation]

#### PATTERNS DETECTED
- [Pattern 1: e.g., "Third week running that Sangha Sankalpa was not honoured"]
- [Pattern 2: e.g., "Tuesday deep work block has been interrupted 3 weeks running"]
- [Pattern 3: e.g., "SPG project has had no next action for 3 weeks"]

#### QUESTIONS FOR SVADHYAYA
Generated from this week's patterns:
1. [Pattern-based question]
2. [Pattern-based question]
3. [Standing weekly question from coaching profile]

#### SUGGESTED NEXT WEEK SANKALPAS (draft — for human to refine)
- Atma: 
- Sangha: 
- Karma: 
- Samaj: 
- Sharira: 

#### AI TASKS TO INITIATE NEXT WEEK
Based on project status and upcoming needs:
- Research Agent: [Task]
- Drafting Agent: [Task]
```

---

## COACHING SESSION PREP

**Trigger**: Before any coaching session, or on demand.

```markdown
### COACHING SESSION PREP — [DATE]

#### SINCE LAST SESSION ([DATE]):
- Sankalpas set: [List]
- Sankalpas honoured: [List] / Not honoured: [List]
- New projects started: [List]
- AI delegation used: [Summary]

#### PATTERNS SINCE INTAKE / LAST MAJOR REVIEW:
- [Emerging pattern 1]
- [Emerging pattern 2]

#### SUGGESTED FOCUS AREAS FOR THIS SESSION:
1. [Based on patterns — e.g., "The recurring avoidance of SPG activation"]
2. [Based on stalled items — e.g., "Three coaching-suggested tasks remain untouched"]
3. [Based on sphere data — e.g., "Sangha sphere has declined for 3 consecutive weeks"]

#### POWERFUL QUESTIONS TO CONSIDER OPENING WITH:
- "[Question 1 tailored to this leader's patterns]"
- "[Question 2]"

#### PROGRESS TO CELEBRATE:
- [Genuine achievement since last session — specific and named]
```

---

## MONTHLY PATTERN REPORT

*Generated at end of each month. Saved as `reviews/YYYY-MM-pattern-report.md`*

Tracks month-over-month trends in:
- Five Spheres scores
- Sankalpa honoured rate
- Task completion by sphere
- AI delegation efficiency
- Coach-suggested item completion rate
- SPG progress indicators
