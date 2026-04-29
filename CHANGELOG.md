# Changelog

All notable changes to the Hitaishin are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html):
- **Major** (x.0.0): Significant philosophical or architectural changes
- **Minor** (0.x.0): New agents, new connectors, new reference files
- **Patch** (0.0.x): Corrections, clarifications, small improvements

---

## [2.0.0] — 2026-04

### Added — Coaching Lifecycle (Intake System)
- `intake/intake-protocol.md` — Complete 3-stage onboarding: Deep Interview (6 modules) → Psychometrics → Synthesis session
- `intake/apps/01-character-strengths.html` — 30-question VIA-adapted Character Strengths assessment with JP-aligned interpretations and Markdown export
- `intake/apps/02-spheres-assessment.html` — 50-question Five Spheres Balance Wheel with radar chart visualisation and Integral Balance Score
- `intake/apps/03-leadership-oa-profile.html` — 40-question Organizational Attitude profile with Saboteur identification and Prabodhini-specific antidotes
- `profiles/_mentee-profile-template.md` — Comprehensive living mentee document: psychometrics → sessions → breakthroughs → coaching hypothesis

### Added — GTD Task Management System
- `gtd/GTD-GUIDE.md` — Complete GTD framework adapted for Prabodhini context with Five Sphere tagging, Sankalpa alignment, and AI delegation layer
- `gtd/00-inbox.md` — Capture inbox template
- `gtd/01-next-actions.md` — Sphere-organised next actions with full tag system
- `gtd/02-projects.md` — Multi-step project index with Sankalpa traceability
- `gtd/04-waiting-for.md` — Delegated items tracker including AI agent queue
- `gtd/05-someday.md` — Deferred aspirations organised by sphere
- `gtd/07-weekly-review.md` — Integrated GTD + Svadhyaya weekly review template
- `gtd/projects/_project-template.md` — Full project file template with phase planning, AI delegation, and reflection log

### Added — AI Delegation Architecture
- `ai-delegation/AI-DELEGATION-GUIDE.md` — Master guide: philosophy, Human-AI division of labour, decision matrix, ethical principles
- `ai-delegation/agent-research.md` — Research Agent: structured brief format, output template, quality log, active task queue
- `ai-delegation/agent-drafting.md` — Drafting Agent: five content templates, voice calibration notes, active task queue
- `ai-delegation/agent-planning.md` — Planning Agent: project plan + weekly time-block output templates
- `ai-delegation/agent-inbox-review.md` — Inbox Agent + Review Agent: batch processing, pattern detection, coaching session prep

### Added — Documentation (GitHub Open Source)
- `README.md` — Project landing page with Quick Start for all three audiences, repository map, philosophical foundation, roadmap
- `references/README.md` — Domain expert guide: what to review, contribution style guide, glossary of 20 key terms
- `agents/README.md` — Coaching methodology guide: ICF alignment check, JP authenticity review, how to add new agents
- `intake/README.md` — Three-audience guide: users (getting started), domain experts (reviewing), developers (extending apps)
- `profiles/README.md` — User and coach guide: creating profiles, privacy, version control, `.gitignore` setup
- `gtd/README.md` — User and developer guide: GTD basics, Prabodhini innovations, Obsidian integration, programmatic parsing
- `ai-delegation/README.md` — Developer guide: current architecture, Phase 1–4 roadmap, Claude API integration examples, Supabase schema, ethical architecture
- `connectors/README.md` — Developer guide: connector file structure, 5 connectors roadmap with MCP details, privacy considerations
- `CONTRIBUTING.md` — Contribution guide for all three audiences with PR checklists, branch naming, script template
- `LICENSE` — MIT with frameworks attribution and psychometric disclaimer
- `.gitignore` — Personal data protection for profiles and GTD personal files
- `CHANGELOG.md` — This file

### Updated — SKILL.md
- Added 4 new session types: Intake & Onboarding, GTD Processing Session, AI Delegation Session, Coach-Initiated Task Injection
- Added Complete File Index table covering all 33 files across all folders

---

## [1.0.0] — 2026-04

### Added — Initial Release
- `SKILL.md` — Master intelligence layer with 7 session types and 6-agent routing
- `references/jp-philosophical-foundation.md` — JP wisdom architecture: Advaita, Gita, Vivekananda, Ramdas, Dayananda, Aurobindo, JP pedagogy
- `references/five-spheres-framework.md` — Five Spheres model (Atma, Sangha, Karma Bhoomi, Samaj Seva, Sharira-Prana) with Purusharthas mapping
- `references/daily-thread.md` — Five-zone 24-hour rhythm with Brahma Muhurta protocol and Minimum Viable Day
- `references/weekly-rhythm.md` — Seven-day Svadhyaya architecture with full Sunday review protocol
- `references/yearly-strategy.md` — Two-day Annual Vision Retreat template
- `references/modern-coaching-frameworks.md` — ICF, PERMA, VIA, Heifetz, Frankl, Kegan, Chamine with JP alignment notes
- `references/spg-contribution-tracker.md` — Adult SPG: selection framework, health assessment, India's priority domains
- `agents/svadharma-navigator.md` — Purpose, calling, VIA strengths integration, three-phase coaching protocol
- `agents/integral-life-coach.md` — Five-sphere balance, time audit, Aurobindo's Integral Yoga applied
- `agents/organizational-attitude-builder.md` — Vivekananda's five OA components, Heifetz adaptive leadership overlay
- `agents/inner-mastery-coach.md` — Mood diagnosis, Saboteur scan, Frankl meaning scan, five inner mastery practices
- `agents/paristhiti-jnana-analyst.md` — Four-layer situational reading, India's macro context, strategic response protocol
- `agents/accountability-partner.md` — Weekly check-in protocol, Sankalpa honoured rate, WOOP framework, CLEAR delegation
- `connectors/calendar-audit.md` — Google Calendar Five-Sphere time audit, meeting quality classification, OA meeting check

---

## Versioning Notes

**What triggers a Major version bump:**
- Fundamental change to the Five Spheres model
- New primary philosophical tradition added to the foundation
- Complete redesign of the agent architecture
- Breaking changes to GTD file formats (requiring migration)

**What triggers a Minor version bump:**
- New coaching agent added
- New psychometric app added
- New connector added
- Significant new reference file
- New folder/area of functionality

**What triggers a Patch version bump:**
- Corrections to philosophical claims
- Improved coaching questions
- Clarifications in any file
- Bug fixes in HTML apps
- Documentation improvements
