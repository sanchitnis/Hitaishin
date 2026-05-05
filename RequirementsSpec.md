# High-Level Requirements Specification: Hitaishin

## 1. System Overview

**Hitaishin** is an AI-powered coaching operating system implemented as a Claude AI *Skill* (a structured prompt-and-knowledge package). It transforms Claude into a deeply contextual, philosophically grounded personal coach for graduates of Jnana Prabodhini (JP), a Pune-based gifted-education institution. The system integrates Indian philosophical traditions with modern evidence-based coaching science to serve leaders navigating professional achievement, family responsibility, and national contribution simultaneously.

---

## 2. Stakeholders and Target Users

| Stakeholder | Role | Primary Needs |
|---|---|---|
| **JP Alumni (Mentees)** | End users / coached individuals | Daily planning, purpose alignment, multi-sphere life balance, accountability |
| **Coaches / Facilitators** | Operators of the system | Onboarding new mentees, running sessions, tracking progress |
| **Domain Experts** (philosophers, coaches, educators) | Content reviewers | Validate and enrich coaching methodology and philosophical grounding |
| **Developers / Engineers** | System extenders | Add automation, tool integrations, and AI agent capabilities |
| **JP Community / Organisation** | Beneficiary institution | Community-wide application and aggregate insights |

---

## 3. Functional Requirements

### FR-1: Coaching Agent System

The system shall activate a **six-agent coaching architecture**, with each agent specialised for a distinct coaching domain:

| Agent | Domain |
|---|---|
| **Svadharma Navigator** | Life purpose, calling, values, career-mission tension, identity |
| **Integral Life Coach** | Five-sphere balance across Self, Family, Career, Nation, Body |
| **Organizational Attitude Builder** | Team leadership, institution building, social impact |
| **Inner Mastery Coach** | Emotional regulation, resilience, Sthitaprajna development, Saboteur awareness |
| **Paristhiti Jnana Analyst** | Situational reading, systems thinking, adaptive leadership |
| **Accountability Partner** | Goal-setting (Sankalpas), weekly review, commitment tracking |

Multiple agents may collaborate in a single session. Agent selection is context-driven and automatic based on conversation triggers.

### FR-2: Session Type Routing

The system shall recognise and correctly route at least **eleven defined session types**:

1. Morning Ignition (daily check-in)
2. Weekly Svadhyaya Review (Sunday reflection)
3. Svadharma Deep Dive (purpose exploration)
4. Multi-Sphere Balance Audit
5. Leadership & Organisational Challenge
6. Inner State Emergency (burnout / crisis)
7. Quarterly/Annual Vision Review
8. Intake & Onboarding (new mentee)
9. GTD Processing Session (task system management)
10. AI Delegation Session (task classification and handoff)
11. Coach-Initiated Task Injection (post-session action capture)

### FR-3: Mentee Onboarding & Psychometric Assessment

The system shall support a **three-stage onboarding lifecycle**:

- **Stage 1 — Deep Intake Interview**: A structured 60–90 minute guided conversation across six modules (Identity, Current Life, Vision, Passions, Patterns/Shadow, Coaching Expectations), producing a `[name]-intake.md` profile.
- **Stage 2 — Psychometric Suite**: Three standalone browser-based HTML assessments (no backend required):
  - *VIA Character Strengths* (30 questions, ~20 min) — maps natural disposition (Svabhava) and Gunavikas
  - *Five Spheres Balance Wheel* (50 questions, ~15 min) — current-state audit across all five life spheres
  - *Organizational Attitude & Leadership Profile* (40 questions, ~20 min) — OA component strength, leadership style, and Saboteur profile
- **Stage 3 — Synthesis Session**: A 45-minute coach-mentee session synthesising all data into growth edges, Sankalpas, and a living profile document (`[name]-profile.md`).

### FR-4: Five Spheres Framework

The system shall structure all coaching, planning, and self-assessment around five life spheres:

| Sphere | Domain |
|---|---|
| **Atma** | Inner Self — Sadhana, Svadhyaya, spiritual depth, Svadharma alignment |
| **Sangha** | Family & Close Relationships — Grihastha Dharma, relational presence |
| **Karma Bhoomi** | Professional & Creative Contribution — mastery, Karma Yoga, economic foundation |
| **Samaj Seva** | National & Community Contribution — Adult SPG, Dharma-Sansthapana |
| **Sharira-Prana** | Physical & Vital Energy — bio-integrity, sleep, movement, Prana management |

All coaching, task tracking, time audits, and reviews shall be tagged and filtered by sphere. No sphere should fall below 5/10 for more than one quarter without active coaching intervention.

### FR-5: GTD Productivity System

The system shall include a **Markdown-native GTD (Getting Things Done) system** adapted for the five-sphere model:

- **Capture** — universal inbox (`00-inbox.md`); everything lands here first
- **Clarify** — decision tree for actionability, delegation, project status, and timelines
- **Organise** — structured file hierarchy (Inbox, Next Actions, Projects, Waiting For, Someday/Maybe, Reference, Weekly Review)
- **Reflect** — weekly Sunday Svadhyaya review covering all projects, Waiting For, Someday, calendar, and weekly Sankalpa-setting
- **Engage** — task selection by sphere, context, energy level, and Sankalpa alignment
- **Tagging system** covering Five Spheres (`#atma`, `#sangha`, etc.), energy type (`#quick`, `#deep`), context (`@home`, `@office`), and source (`#coach-suggested`, `#sankalpa`, `#ai-delegate`)
- **Six horizons of focus** mapped from ground-level next actions up to Svadharma / life purpose

### FR-6: AI Delegation Architecture

The system shall define a **structured human-AI division of labour** across five AI agent roles:

| AI Agent | Function |
|---|---|
| **Research Agent** | Deep research synthesis and knowledge preparation |
| **Drafting Agent** | First-draft production across writing contexts |
| **Planning Agent** | Project decomposition and milestone scheduling |
| **Inbox/Review Agent** | Inbox triage, GTD pre-processing, and pattern-spotting |
| **Coaching Agent** | The meta-agent — Prabodhini Catalyst Coach itself |

AI-delegated tasks shall follow a structured syntax with agent, priority, deadline, output format, and context. All AI outputs shall pass a four-step quality assurance review (factual, values, purpose, human touch) before being considered final.

### FR-7: Daily, Weekly, and Annual Rhythms

The system shall provide **structured temporal operating rhythms**:

- **Daily** — Five-zone operating model: Sacred Opening (Atma), Deep Work Window (Karma Bhoomi), Engagement Block (Meetings/SPG), Regeneration Window (Physical/Sangha), Evening Closure (Sangha/Atma reflection). Minimum Viable Day protocol for disrupted days.
- **Weekly** — Sunday Svadhyaya Review cycle: sphere audit, Sankalpa review, project review, calendar review, weekly Sankalpa-setting
- **Monthly** — Three Commitments Review and AI delegation audit
- **Quarterly/Annual** — Full sphere scoring, vision review, multi-year Sankalpa design via `yearly-strategy.md`

### FR-8: Calendar Integration

The system shall support a **Google Calendar connector** for automated Five-Sphere Time Audit:

- Classify each calendar event by sphere
- Produce an Integrity Gap Report comparing declared priorities against actual time allocation
- Generate a Meeting Quality Audit (Generative / Maintenance / Consuming / Unclear)
- Produce a weekly Calendar Health Dashboard with scores for Atma protection, Sangha presence, deep work, SPG advance, and physical health

### FR-9: Living Mentee Profile

The system shall maintain a **living profile document per mentee** capturing:

- Identity, JP batch, professional context
- Five Spheres current reality with scores
- Core values, passions, flow activators
- 10-year vision narrative and Svadharma calling
- Recurring behavioural patterns and growth edges
- Active Sankalpas (1-year, 5-year, SPG)
- Coaching preferences and accountability style
- Psychometric results from all three assessments
- Session breakthroughs and coach notes (updated continuously)

### FR-10: Philosophical Grounding

All coaching interactions shall be grounded in a defined hierarchy of wisdom traditions integrated with Western coaching science:

**Indian Traditions**: Advaita Vedanta (Upanishads / Shankaracharya), Bhagavad Gita (Chapters 2–3, 18), Swami Vivekananda (Man-Making Education, Organizational Attitude), Sri Aurobindo (Integral Yoga), Samarth Ramdas (Dasabodha), Maharshi Dayananda (Vedic rationalism), JP Pedagogy (Gunavikas, SPG, Paristhiti Jnana)

**Western Frameworks**: ICF coaching competencies, PERMA Model (Seligman), VIA Character Strengths (Peterson & Seligman), Adaptive Leadership (Heifetz), Logotherapy (Frankl), Immunity to Change (Kegan), Positive Intelligence / Saboteurs (Chamine), WOOP (Oettingen), GTD (David Allen)

---

## 4. Non-Functional Requirements

| Category | Requirement |
|---|---|
| **Deployment** | Deployable as a Claude AI Skill (ZIP upload to claude.ai) or as a manual paste-in for clients without the Skills feature |
| **Browser Apps** | All three psychometric apps shall run in any modern browser with no backend server, no authentication, and no data transmission |
| **File Format** | All coaching data, task lists, and profiles shall be stored in plain Markdown files — human-readable, portable, and version-controllable |
| **Offline Capability** | The GTD system and profile files shall function fully offline without AI assistance |
| **Tone** | Coaching voice shall be warm, honest, and demanding — philosophically fluent in Sanskrit terms and Indian tradition, scientifically grounded, concise |
| **Privacy / Ethics** | AI-drafted content shall not be presented without disclosure; the human remains fully accountable for all outputs; AI shall not create an appearance of work not genuinely thought through |
| **Scalability** | The profile structure shall support any number of mentees via per-mentee profile files; no shared state between mentees |
| **Licence** | MIT — fully open source |
| **Language** | English (primary); Marathi and Hindi support identified as a roadmap item |

---

## 5. System Architecture

```
┌────────────────────────────────────────────────────────────────┐
│                     SKILL.md (Master Layer)                    │
│     Philosophical grounding · Session routing · Agent index    │
└──────────────────────┬─────────────────────────────────────────┘
                       │ activates
       ┌───────────────┼───────────────────────┐
       ▼               ▼                       ▼
 ┌───────────┐  ┌─────────────┐        ┌─────────────┐
 │  Coaching │  │ GTD System  │        │ AI Delegat. │
 │  Agents   │  │ (Markdown)  │        │ Architecture│
 │ (6 agents)│  │(7 core files│        │ (5 AI agents│
 └─────┬─────┘  │+ projects/) │        │ + guide)    │
       │        └──────┬──────┘        └──────┬──────┘
       │               │                      │
       ▼               ▼                      ▼
 ┌─────────────────────────────────────────────────┐
 │               References Layer                  │
 │  Philosophy · Five Spheres · Daily/Weekly/Annual│
 │  Rhythms · Modern Coaching Frameworks · SPG     │
 └─────────────────────────────────────────────────┘
       │
       ▼
 ┌─────────────────────────────────────────────────┐
 │          Intake & Profile System                 │
 │  Intake Protocol · 3x Psychometric HTML Apps    │
 │  Mentee Profile Template (living document)      │
 └─────────────────────────────────────────────────┘
       │
       ▼
 ┌─────────────────────────────────────────────────┐
 │             Connectors Layer                     │
 │  Google Calendar (time audit) · Gmail (planned) │
 │  Google Drive (planned)                         │
 └─────────────────────────────────────────────────┘
```

---

## 6. Roadmap (Identified Future Requirements)

| Feature | Priority Indicator |
|---|---|
| Voice-first coaching session support (audio intake) | Listed in README roadmap |
| Google Calendar auto-audit integration via MCP connector | Listed; partial spec in `connectors/calendar-audit.md` |
| Automated weekly review pre-processing script | Listed in README roadmap |
| Multi-language support (Marathi, Hindi) | Listed for broader JP community reach |
| Companion mobile-friendly web app for GTD + Sankalpa tracking | Listed in README roadmap |
| Anonymised aggregate community insights dashboard | Listed in README roadmap |
| Gmail and Google Drive connectors | Referenced in `SKILL.md` compatibility section |
| SPG stakeholder outreach templates | Noted in `AI-DELEGATION-GUIDE.md` future section |
| Automated calendar health scoring | Noted in `AI-DELEGATION-GUIDE.md` future section |
| Mentee progress tracking and session note-taking automation | Noted in `AI-DELEGATION-GUIDE.md` future section |

---

## 7. Key Constraints and Assumptions

- **Platform Dependency**: The system is designed specifically for Claude (Anthropic). It relies on Claude's ability to load and reason across multiple large Markdown files in a single context window. Portability to other LLMs would require re-evaluation.
- **No Persistent Backend**: The current architecture has no database or server. All state lives in local Markdown files and user-managed profile documents. Collaboration or sync across devices requires a separate file-sync solution (e.g., Git, Dropbox, Google Drive).
- **User Literacy**: Users are assumed to be technically comfortable editing Markdown files and operating a file system. Non-technical end users would require a UI layer.
- **JP Cultural Context**: The system's philosophical grounding is specifically tailored to JP alumni. Non-JP users can benefit from the structural frameworks but will find many references culturally specific to JP's tradition.
- **AI Quality Responsibility**: The system makes no claim that AI-generated coaching outputs are equivalent to trained human coaching. The human remains accountable for all outcomes and must apply their own judgment to AI outputs.
