# 🔥 Hitaishin

**An open-source AI coaching system for leaders shaped by [Jnana Prabodhini](https://www.jnanaprabodhini.org/)**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange)](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills)
[![Platform](https://img.shields.io/badge/Platform-Claude.ai%20%7C%20Claude%20Code-blue)](https://claude.ai)

---

## What This Is

The **Hitaishin** is a Claude AI *skill* — a structured coaching system that turns Claude into a deeply grounded personal coach for graduates of Jnana Prabodhini (JP), the Pune-based gifted-education institution founded in 1962 on the philosophy of Swami Vivekananda.

JP alumni are unusually formed individuals: high-IQ, trained from school age in leadership, steeped in Advaita Vedanta, the Bhagavad Gita, the teachings of Sri Aurobindo, Samarth Ramdas, and Maharshi Dayananda — and carrying a deep conviction that their education was given in service of India's renewal. They are now navigating demanding professional lives, family responsibilities, and national contribution.

This coaching system serves them at the intersection of all three.

---

## Who This Is For

| Audience | What You'll Find Here |
|----------|----------------------|
| 👤 **JP alumni / users** | A personal AI coach available any time — for daily planning, weekly review, purpose-finding, and life balance |
| 🎓 **Domain experts** (coaches, educators, philosophers) | A structured coaching curriculum to review, validate, and enrich with deeper wisdom |
| 💻 **Developers / engineers** | An open skill framework to extend with scripts, integrations, and automation |

> **Not a JP alumnus but curious?** The underlying frameworks — Five Spheres, GTD with Sankalpa-alignment, AI delegation architecture — are broadly applicable to any purpose-driven leader. The philosophical grounding is Indian and specific; the structure is universal.

---

## What It Does

The skill activates a **six-agent coaching system** inside Claude:

```
┌─────────────────────────────────────────────────────────┐
│                  Hitaishin                  │
├──────────────────┬──────────────────────────────────────┤
│  🔍 Svadharma    │ Purpose, calling, life mission        │
│     Navigator    │                                       │
├──────────────────┼──────────────────────────────────────┤
│  ⚖️  Integral    │ Five-sphere balance: Self · Family ·  │
│     Life Coach   │ Career · Nation · Body               │
├──────────────────┼──────────────────────────────────────┤
│  🏛️  OA Builder  │ Vivekananda's Organizational         │
│                  │ Attitude — team & institution building│
├──────────────────┼──────────────────────────────────────┤
│  🧘 Inner Mastery│ Sthitaprajna development, resilience, │
│     Coach        │ Saboteur awareness                    │
├──────────────────┼──────────────────────────────────────┤
│  🗺️  Paristhiti  │ Situational reading, adaptive         │
│     Analyst      │ leadership, systemic thinking         │
├──────────────────┼──────────────────────────────────────┤
│  ✅ Accountability│ GTD workflow, Sankalpas, commitments  │
│     Partner      │                                       │
└──────────────────┴──────────────────────────────────────┘
```

It also includes:

- **3 psychometric web apps** (run in any browser, no backend) — Character Strengths, Five Spheres Balance Wheel, OA Leadership Profile
- **Full GTD task management** in Markdown files — with sphere-tagging, Sankalpa alignment, and AI delegation
- **AI delegation architecture** — 5 specialised AI agents (Research, Drafting, Planning, Inbox, Review) that handle work the human shouldn't be doing
- **Complete onboarding lifecycle** — intake interview protocol → psychometrics → synthesis → living mentee profile

---

## Quick Start (5 minutes)

### Step 1 — Download the skill

```bash
git clone https://github.com/sanjay.chitnis/hitaishin.git
```

Or download the [latest release ZIP](../../releases).

### Step 2 — Install in Claude

1. Open [claude.ai](https://claude.ai) → click your profile icon → **Settings**
2. Go to **Features** → **Skills**
3. Click **+** → **Create Skill** → **Upload ZIP**
4. Zip the `hitaishin` folder and upload it

> see [Alternative Usage](#alternative-usage-without-skills) below.

### Step 3 — Start your first session

In any Claude conversation, just say:

```
Coach me using the Hitaishin
```

Or try:
```
I want to start my coaching intake — I'm a JP alumnus ready to onboard
```
```
Help me plan my day using the Five Spheres
```
```
Run a Sunday Svadhyaya review with me
```
```
Apply the Purushartha filter to this task: [describe a decision]
```

---

## Alternative Usage (Without Skills)

If you don't have a plan that supports Skills:

1. Open the file `SKILL.md` in this repository
2. Copy its entire contents
3. Paste it as the first message in a new Claude conversation
4. Attach any reference files you want Claude to know about
5. Then proceed with your coaching session

This works but requires manual setup each conversation. The Skills feature automates this.

---

## Repository Structure

```
hitaishin/
│
├── SKILL.md                    ← The master intelligence layer
│                                 (Claude reads this to understand the system)
│
├── references/                 ← Philosophical and framework foundations
│   ├── jp-philosophical-foundation.md
│   ├── five-spheres-framework.md
│   ├── daily-thread.md
│   ├── weekly-rhythm.md
│   ├── yearly-strategy.md
│   ├── modern-coaching-frameworks.md
│   └── spg-contribution-tracker.md
│
├── agents/                     ← Six specialist coaching agents
│   ├── svadharma-navigator.md
│   ├── integral-life-coach.md
│   ├── organizational-attitude-builder.md
│   ├── inner-mastery-coach.md
│   ├── paristhiti-jnana-analyst.md
│   └── accountability-partner.md
│
├── intake/                     ← Onboarding system (new mentee)
│   ├── intake-protocol.md
│   └── apps/
│       ├── 01-character-strengths.html
│       ├── 02-spheres-assessment.html
│       └── 03-leadership-oa-profile.html
│
├── profiles/                   ← Per-mentee living documents
│   └── _mentee-profile-template.md
│
├── gtd/                        ← Getting Things Done system (Markdown-native)
│   ├── GTD-GUIDE.md
│   ├── 00-inbox.md
│   ├── 01-next-actions.md
│   ├── 02-projects.md
│   ├── 04-waiting-for.md
│   ├── 05-someday.md
│   ├── 07-weekly-review.md
│   └── projects/
│       └── _project-template.md
│
├── ai-delegation/              ← AI agent specifications and task queues
│   ├── AI-DELEGATION-GUIDE.md
│   ├── agent-research.md
│   ├── agent-drafting.md
│   ├── agent-planning.md
│   └── agent-inbox-review.md
│
└── connectors/                 ← External tool integrations
    └── calendar-audit.md
```

---

## The Philosophical Foundation

The coaching system is grounded in four wisdom traditions JP synthesises:

| Tradition | Core Contribution |
|-----------|------------------|
| **Advaita Vedanta** (Upanishads) | Non-dual identity — you are not only your roles |
| **Bhagavad Gita** | Svadharma, Nishkama Karma, Sthitaprajna |
| **Swami Vivekananda** | Man-Making Education, Organizational Attitude |
| **Sri Aurobindo** | Integral Yoga — all life as transformative practice |
| **Samarth Ramdas** | Practical activism; Dasabodha wisdom |
| **Maharshi Dayananda** | Scientific temper within Vedic tradition |

Layered with Western coaching science: ICF competencies, Positive Psychology (Seligman), Adaptive Leadership (Heifetz), Logotherapy (Frankl), Immunity to Change (Kegan), and Positive Intelligence (Chamine).

---

## Contributing

We welcome contributions from:

- **JP alumni** with lived experience of the formation
- **Coaching professionals** who can strengthen the methodology
- **Philosophers and educators** who can deepen the philosophical grounding
- **Developers** who can add automation, integrations, and tooling

Please read the [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a PR.

---

## Folder-Specific Documentation

Each folder has its own README tailored to the most likely person working in it:

| Folder | README audience |
|--------|----------------|
| [`references/`](references/README.md) | Domain experts — philosophers, coaches, educators |
| [`agents/`](agents/README.md) | Domain experts — coaching methodology reviewers |
| [`intake/`](intake/README.md) | Domain experts + developers |
| [`gtd/`](gtd/README.md) | Users + developers |
| [`ai-delegation/`](ai-delegation/README.md) | Developers + innovators |
| [`profiles/`](profiles/README.md) | Users (mentees and coaches) |
| [`connectors/`](connectors/README.md) | Developers |

---

## Roadmap

- [ ] Voice-first coaching session support (audio intake)
- [ ] Google Calendar auto-audit integration via MCP
- [ ] Automated weekly review pre-processing script
- [ ] Multi-language support (Marathi, Hindi) for broader JP community reach
- [ ] Companion mobile-friendly web app for GTD + Sankalpa tracking
- [ ] Anonymised aggregate insights dashboard for JP community

---

## License

MIT License — see [LICENSE](LICENSE).

*The psychometric questions and philosophical frameworks are drawn from public domain and adapted traditions. VIA Character Strengths are inspired by the work of Peterson & Seligman. GTD framework principles are from David Allen's published work.*

---

## Acknowledgements

Built in the spirit of Jnana Prabodhini's founding vision:
*"Motivated intelligence, organised for social change, grounded in Advaita."*

With deep respect to Dr. V.V. (Appa) Pendse and the entire JP community whose formation made this worth building.

---

*"Arise, Awake, and stop not until the goal is reached."* — Swami Vivekananda
