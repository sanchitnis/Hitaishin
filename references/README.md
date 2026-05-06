# `references/` — Philosophical & Framework Foundations

**Primary audience: Domain experts — philosophers, JP educators, coaching professionals**

---

## What This Folder Contains

The `references/` folder is the **philosophical and methodological backbone** of the entire coaching system. Every coaching agent and session type draws from one or more of these files. They are the wisdom layer that Claude loads to inform its coaching responses.

Think of these files as the "curriculum" — the body of knowledge the coach must hold before any meaningful conversation can happen.

### Boundary: No Personal Logs in `references/`

`references/` files are framework-level guidance only.
Do not store personal metrics, coaching dialogue captures, or weekly/daily logs in this folder.

- Put personal tracking in `profiles/`.
- Put task and weekly workflow execution in `gtd/`.

---

## Files at a Glance

| File | What It Does | Who Should Review |
|------|-------------|-------------------|
| `jp-philosophical-foundation.md` | Comprehensive synthesis of JP's intellectual roots: Vivekananda, Advaita, Gita, Ramdas, Dayananda, Aurobindo | JP scholars, philosophy professors, senior JP alumni |
| `five-spheres-framework.md` | The integral life model — 5 dimensions every JP leader must balance simultaneously | Life coaches, positive psychologists, JP community elders |
| `daily-thread.md` | 24-hour operating rhythm integrating Ayurvedic/yogic wisdom with modern performance neuroscience | Health professionals, yoga practitioners, chronobiology-aware coaches |
| `weekly-rhythm.md` | Seven-day Svadhyaya architecture — the weekly cycle of self-study and renewal | Coaching practitioners, OBE-aligned educators |
| `yearly-strategy.md` | The Annual Vision Retreat — a 2-day structured deep review | Leadership retreat facilitators, life coaches |
| `modern-coaching-frameworks.md` | Western coaching science: ICF, PERMA, VIA, Heifetz, Frankl, Kegan, Chamine | Credentialed coaches (ICF-PCC or above), positive psychologists |
| `spg-contribution-tracker.md` | The adult SPG — JP's Special Purpose Group concept extended into adult organized contribution | JP faculty, social sector leaders, community organizers |

---

## How These Files Work in the Skill

When a user begins a coaching session, Claude reads `SKILL.md` first — which tells it *which* reference files to load for *which* type of session. For example:

- A morning planning session → loads `daily-thread.md`
- A purpose/calling conversation → loads `jp-philosophical-foundation.md` + `five-spheres-framework.md`
- A Sunday review → loads `weekly-rhythm.md` + `five-spheres-framework.md`

Claude does not load all references simultaneously — it selects contextually, keeping the coaching sharp and focused.

---

## For Domain Experts: What to Review

### Priority 1 — Philosophical Accuracy
**File**: `jp-philosophical-foundation.md`

This is the most important file for philosophical review. Check:
- Is the characterisation of Advaita Vedanta's role in JP accurate?
- Are the four historical figures (Ramdas, Dayananda, Vivekananda, Aurobindo) represented faithfully?
- Is the Organizational Attitude framework correctly attributed and described?
- Are any JP-specific pedagogical concepts (Gunavikas, Paristhiti Jnana, SPG) accurately described?
- Does anything misrepresent the JP tradition in ways that could mislead a user?

### Priority 2 — Coaching Framework Integration
**File**: `modern-coaching-frameworks.md`

Check:
- Is each Western framework accurately summarised without distortion?
- Do the "JP alignment" mappings between Eastern and Western concepts hold up under scrutiny?
- Are any frameworks presented with inappropriate claims of equivalence?
- Are the limitations of each framework acknowledged where relevant?

### Priority 3 — The Five Spheres Model
**File**: `five-spheres-framework.md`

This is the structural organising model for all of the coaching. Check:
- Does the Five Spheres model adequately represent the full range of a JP alumnus's life?
- Is the Grihastha Dharma (householder stage) framed accurately and with appropriate depth?
- Is the Samaj Seva sphere ambitious enough for a JP alumnus's national contribution calling?
- Are the sphere interaction dynamics described accurately?

### Priority 4 — Practical Wisdom
**Files**: `daily-thread.md`, `weekly-rhythm.md`, `yearly-strategy.md`

Check:
- Are the practical protocols realistic for busy professionals (not just ideals)?
- Is the integration of Ayurvedic/yogic wisdom with modern science balanced — neither dismissive of tradition nor pseudoscientific?
- Do the journaling and reflection prompts reflect genuine JP Svadhyaya practice?

---

## How to Contribute Improvements

1. **Fork the repository** on GitHub
2. **Edit the relevant file** in `references/`
3. **Add a comment at the top** of your change explaining the rationale
4. **Submit a Pull Request** with the label `domain-review`

For significant philosophical disagreements, please open a **GitHub Issue** first with the label `philosophy-debate` so the community can discuss before changes are merged.

---

## Style Guide for Reference Files

If you add content to these files, follow these conventions:

- **Language**: Clear English with Sanskrit/Marathi terms used naturally and explained on first use
- **Citations**: Quote specific texts (Gita verse numbers, Dasabodha chapter references) where possible
- **Structure**: H2 for major sections, H3 for subsections; tables for comparisons
- **Length**: Prefer depth over breadth — one concept thoroughly explored is more useful than five touched superficially
- **Tone**: Scholarly warmth — rigorous but not cold; grounded but not preachy

---

## Glossary of Key Terms

*(For reviewers unfamiliar with some of the terminology used in these files)*

| Term | Meaning |
|------|---------|
| **Advaita** | Non-dualism — the philosophical position that individual consciousness and universal consciousness are not ultimately separate |
| **Anushasan** | Self-discipline; specifically self-governance, not externally imposed rule |
| **Dasabodha** | Samarth Ramdas's 17th-century text of practical wisdom and leadership |
| **Grihastha** | The householder stage of life (married, family, worldly engagement) in the four-ashrama model |
| **Gunavikas** | JP's programme for developing qualities/character beyond academic excellence |
| **Nishkama Karma** | Action without attachment to the fruit — the Gita's central ethical teaching |
| **Paristhiti Jnana** | Knowledge of one's situation and environment; a JP curriculum subject |
| **Prajna** | Discriminative wisdom; the intelligence that sees clearly |
| **Sahakar** | Cooperative spirit; genuine collaboration rather than competitive alliance |
| **Sanghatan** | The capacity to build and sustain organisations |
| **Sankalpa** | A conscious, will-backed intention; stronger than a goal |
| **Seva Bhava** | Service orientation; the attitude of serving others as an expression of non-dual recognition |
| **SPG** | Special Purpose Group — a JP Prashala feature where students choose a problem to work on over years |
| **Sthitaprajna** | One of steady wisdom — the Gita's ideal of equanimity under all conditions |
| **Svadhyaya** | Self-study; rigorous self-examination as a practice |
| **Svadharma** | One's own unique duty/calling — distinct from generic dharma |
| **Svabhava** | One's natural disposition or character |
| **Vishwa Guru** | World teacher/guide — the aspiration for India as a source of civilizational wisdom |
