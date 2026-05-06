# `profiles/` — Mentee Living Profiles

**Primary audience: Mentees (users) and their coaches**

---

## What This Folder Contains

The `profiles/` folder is where each mentee's **personal coaching record** lives. It grows continuously throughout the coaching relationship — from the first intake interview to the last session.

Template policy:
- Keep `profiles/_mentee-profile-template.md` blank at all times.
- Store filled profile content only in person-specific files, for example `profiles/sanjay-chitnis.md`.
- For each user, create and maintain that user's own file in `profiles/`.

```
profiles/
├── _mentee-profile-template.md    ← Copy this to create your profile
├── [your-name]-intake.md          ← Created during Stage 1 intake (your raw interview)
└── [your-name]-profile.md         ← Created after synthesis — your living document
```

---

## For Mentees: Your Profile

### Creating your profile

**Step 1**: After completing the intake interview, copy the template:
```bash
cp profiles/_mentee-profile-template.md profiles/[your-first-name]-profile.md
```

**Step 2**: Fill in the identity section with your coach or with Claude:
```
Open my profile at profiles/[name]-profile.md and let's fill in the basics together
```

**Step 3**: After completing the three psychometric apps, copy the output blocks from each app into the **Psychometric Profile** section of your profile.

**Step 4**: After your synthesis session, fill in your Sankalpas, Growth Edges, and coaching rhythm.

### Keeping your profile updated

Your profile is a **living document**. Update it after:
- Every coaching session (add a session log entry)
- Every Sunday Svadhyaya (update the Five Spheres tracking table)
- Every quarter (update sphere scores, review growth edge progress)
- Any significant breakthrough (add to the Breakthrough Log)

### Privacy

Your profile file contains personal information. You control it entirely. Options:
- Keep it on your local computer only
- Store it in a private GitHub repository
- Keep it in a private folder in Google Drive or Dropbox
- Share it with your coach via a shared private folder

**Never commit your personal profile to a public repository.**

The `_mentee-profile-template.md` (with underscore prefix) is the only profile file that belongs in the public repository — it contains no personal data.

### Sharing with Claude

When you want Claude to coach you with full context, share your profile at the start of a session:

```
Here is my coaching profile: [paste the content of your profile file]

Based on this, let's do a Sunday Svadhyaya review.
```

Or if using the skill with file access:
```
Please read my profile at profiles/[name]-profile.md and then coach me on [topic]
```

---

## For Coaches: Working with Mentee Profiles

### What the profile tracks

The mentee profile (`_mentee-profile-template.md`) contains:

| Section | What It Records | Updated When |
|---------|----------------|-------------|
| Identity & Context | Basic facts, life stage | Once (intake) |
| Psychometric Profile | VIA strengths, sphere scores, Organizational Attitude profile, Saboteur | Once per quarter (retake) |
| Svadharma Profile | Calling, gap, recurring pattern | Quarterly review |
| Passions & Flow Map | What energises them | As discovered |
| Adult SPG | Their national contribution commitment | Monthly |
| Active Sankalpas | Annual + current weekly | Weekly (Sankalpas) |
| Growth Edges | Primary / Secondary / Long-arc | Quarterly |
| Session Log | Every session record | After each session |
| Breakthrough Log | Significant shifts | As they occur |
| Five Spheres Tracking | Quarterly scores over time | Quarterly |
| Coach's Working Hypothesis | Coach's private assessment | Monthly |

### The Coach's Working Hypothesis section

This is the most important section for coaches. It is where you document your **best current theory** of what this person most needs — which evolves as you know them better.

It should answer three questions:
1. What is the deepest adaptive challenge beneath the surface issues they present?
2. What pattern keeps recurring that they may not yet see?
3. What would unlock the most significant growth right now?

Update this monthly. Compare your hypothesis from three months ago with today. Note what shifted your understanding.

### The Breakthrough Log

Record breakthroughs specifically: not "had a good session" but "recognised for the first time that the Controller Saboteur drives his delegation failures — and accepted this without defensiveness." The specificity is what makes the log useful for coaching pattern analysis.

### Version control for profiles

If you are coaching multiple JP alumni in an organisation, consider keeping profiles in a private repository with access restricted to the coach and mentee. This enables:
- Git history as a coaching audit trail
- Branching for draft versions before sharing
- Issues for asynchronous reflection prompts

---

## Profile File Naming Convention

| File | Convention |
|------|-----------|
| Template | `_mentee-profile-template.md` (underscore = template, not a real person) |
| Intake record | `[firstname]-intake.md` (raw interview notes — Stage 1 output) |
| Living profile | `[firstname]-profile.md` or `[firstname-lastname].md` (the full, evolving document) |
| Historical snapshot | `[firstname]-profile-YYYY-Q[N].md` (quarterly archive copy) |

---

## `.gitignore` for Profiles

Add this to your `.gitignore` if you fork this repo for personal use:

```gitignore
# Personal profiles — never commit to public repos
profiles/*
!profiles/_mentee-profile-template.md
!profiles/README.md
```
