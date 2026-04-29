# `intake/` — Coaching Onboarding System

**Primary audience: Users beginning coaching · Domain experts reviewing methodology · Developers extending the apps**

---

## What This Folder Contains

The `intake/` folder contains everything needed to **onboard a new mentee** into the Prabodhini Catalyst OS. It is the entry point — the place where a new coaching relationship begins and a rich mentee profile is established.

```
intake/
├── intake-protocol.md          ← The 3-stage onboarding guide (for the coach)
└── apps/
    ├── 01-character-strengths.html   ← VIA-adapted psychometric (30 questions)
    ├── 02-spheres-assessment.html    ← Five Spheres balance wheel (50 questions)
    └── 03-leadership-oa-profile.html ← OA + Saboteur profile (40 questions)
```

---

## For Users: Getting Started with Your Coaching Intake

### What the intake process involves

The intake is a **3-stage journey** that typically takes 1–2 weeks to complete:

**Stage 1: The Deep Interview** (~60–90 minutes)
A structured conversation between you and your coach (or with Claude directly) covering who you are, how your life is going across all five spheres, what your vision is, and what you hope to get from coaching.

**Stage 2: Three Psychometric Assessments** (~45–60 minutes total)
Three interactive web applications that you complete in a browser — no login, no data stored on any server. All results stay on your device until you copy them to your profile file.

**Stage 3: Synthesis Session** (~45 minutes)
The coach reflects back what they've heard, identifies key patterns and growth edges, and co-creates your coaching sankalpas and rhythm.

### Running the psychometric apps

The three HTML files work in any modern browser:

1. Open `apps/01-character-strengths.html` — answer 30 questions about yourself
2. Open `apps/02-spheres-assessment.html` — rate 50 statements across the Five Spheres
3. Open `apps/03-leadership-oa-profile.html` — answer 40 questions on OA and leadership

Each app ends with a **"Copy to Clipboard"** button that generates a formatted Markdown block. Copy this and paste it into your `profiles/[your-name]-intake.md` file.

### Starting your intake with Claude

If you want Claude to conduct Stage 1 interactively, say:

```
I want to begin my Prabodhini Catalyst OS coaching intake. I'm a JP alumnus.
Please guide me through the intake interview.
```

Claude will work through the six modules of the deep interview with you.

### What happens to your data

**Nothing leaves your device unless you share it.** The psychometric apps are static HTML files — they run entirely in your browser with no network calls. Your results are only stored when you copy them to your Markdown profile file. That file lives wherever you keep it (your computer, a private GitHub repo, Google Drive).

---

## For Domain Experts: Reviewing the Intake Protocol and Assessments

### The intake protocol (`intake-protocol.md`)

This file structures the 60–90 minute opening conversation. Review for:

**Module A (Identity Foundations)**
- Does the line of inquiry surface the key formation elements of a JP alumnus without being prescriptive?
- Is there appropriate space for people who had a more ambivalent relationship with JP (not all alumni are uniformly positive)?

**Module B (Five Spheres — Current Reality)**
- Is the framing of each sphere sensitive to life stage? (A 28-year-old's Sangha sphere looks very different from a 55-year-old's)
- Is the Samaj Seva sphere framed ambitiously enough without making people who don't yet have an active SPG feel inadequate?

**Module C (Vision)**
- Is the 10-year visualisation exercise appropriately guided — evocative without being leading?
- Are the vision questions genuinely open, or do they subtly steer toward a particular type of "JP-approved" life?

**Module E (Patterns, Shadow, Growth Edges)**
- Is the "shadow work" framing appropriate for a first intake session, or is it too deep too soon?
- The inner critic questions — do they risk opening something the coach may not be equipped to hold in this context?

### The psychometric apps

**App 01 — Character Strengths**

This is a 30-question VIA-adapted assessment. The original VIA Survey has 240 questions; this is a deliberately short version for coaching context, not clinical diagnosis. Review for:
- Are the 30 questions a representative sample of the 24 strengths?
- Are the JP-alignment notes for each strength accurate and non-reductive?
- Does the scoring algorithm (raw sum per strength) produce meaningfully ordered results with 30 items?

**App 02 — Five Spheres Assessment**

50 questions, 10 per sphere. The questions are designed to measure actual quality and engagement in each sphere, not just time spent. Review for:
- Do the 10 questions per sphere adequately cover the key dimensions of that sphere?
- Is the Integral Balance Score (average of five sphere percentages) a meaningful single number?
- Are the sphere-specific coaching insights (generated based on score ranges) accurate and useful?

**App 03 — OA + Leadership Profile**

Maps to Vivekananda's five OA components plus Saboteur profiling adapted from Shirzad Chamine's Positive Intelligence framework. Review for:
- Are the OA component questions a valid operationalisation of Vivekananda's framework?
- Are the five Saboteur profiles (Judge, Hyper-Achiever, Controller, Avoider, Rationalist) the most relevant for a JP alumnus population?
- Are the "Prabodhini Antidotes" for each Saboteur philosophically sound and practically useful?

### Suggested additions

Consider whether the intake should include:
- A **relational genogram** (mapping key family and mentoring relationships)
- A **values clarification exercise** (rank-ordering values under constraint)
- A **fear inventory** (what is the person most afraid of in their current life situation)
- A **JP inheritance audit** (explicitly naming which JP teachings are alive vs. dormant vs. contested)

---

## For Developers: Extending the Psychometric Apps

### Technology stack

All three apps are **single-file vanilla HTML/CSS/JavaScript** — no frameworks, no build tools, no npm, no server. Open in browser, works immediately.

This was a deliberate design choice: maximum accessibility, zero infrastructure dependency, completely self-contained.

### Architecture of each app

```
HTML file
├── <style>         ← All CSS (CSS variables, responsive, animations)
├── <body>          ← Semantic HTML structure  
└── <script>        ← All JS (questions data, state, rendering, scoring, export)
    ├── DATA        ← Questions and scoring metadata (top of script)
    ├── STATE       ← Current answers, current page/section
    ├── RENDER      ← Functions that rebuild the UI from state
    ├── NAVIGATION  ← prev/next handlers with validation
    ├── SCORING     ← Calculates results from raw answers
    └── EXPORT      ← Generates the Markdown clipboard output
```

### How to add questions

In `01-character-strengths.html`, questions are in the `QUESTIONS` array:

```javascript
const QUESTIONS = [
  { strength: 'creativity', text: 'I often think of new ways...' },
  // add more here
];
```

In `02-spheres-assessment.html`, questions are nested in the `SPHERES` array:

```javascript
const SPHERES = [
  {
    id: 'atma',
    questions: [
      'I have a consistent daily Sadhana practice...',
      // add more here (keep it to 10 per sphere for balance)
    ]
  }
];
```

### How to change the scoring algorithm

Scoring functions are clearly labelled in each app. For example, in App 01:

```javascript
function showResults() {
  // Aggregate raw scores per strength from QUESTIONS array
  // Normalise to 100% by dividing by (question_count × max_score)
  // Sort descending — top 5 are "signature strengths"
}
```

### How to add a new psychometric app

1. Copy `01-character-strengths.html` as your starting template
2. Replace the DATA section with your questions and scoring dimensions
3. Update the SCORING section to match your instrument's logic
4. Update the EXPORT section to generate the right Markdown output block
5. Name the file `04-[instrument-name].html`
6. Add it to `intake-protocol.md` in Stage 2
7. Update this README

### Potential enhancements

- **Persistent local storage**: Save partial progress if the user closes the browser mid-assessment
- **PDF export**: Generate a formatted PDF report from the results (use the `pdf` skill as reference)
- **Comparison over time**: Allow re-taking and displaying delta from previous results
- **Accessibility**: Add ARIA labels, keyboard navigation, screen reader support
- **Multi-language**: Add Marathi/Hindi translation layer for broader JP community reach
- **Integration**: POST results directly to a Google Sheet or Supabase row with user's consent

### Running locally

```bash
# No build step needed — just open in browser
open intake/apps/01-character-strengths.html

# Or serve locally if you need to test fetch-based features
python3 -m http.server 8080
# Then open http://localhost:8080/intake/apps/
```

### Browser compatibility

Tested and working in:
- Chrome 120+
- Firefox 120+
- Safari 17+
- Edge 120+

Uses: CSS Grid, CSS Custom Properties, `navigator.clipboard.writeText()`, `<canvas>` (App 02 only). No polyfills needed for modern browsers.
