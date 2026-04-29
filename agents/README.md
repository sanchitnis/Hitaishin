# `agents/` — Six Specialist Coaching Agents

**Primary audience: Coaching professionals, JP educators, domain experts reviewing methodology**

---

## What This Folder Contains

Each file in `agents/` defines one **specialist coaching agent** — a focused coaching persona that Claude adopts when the conversation calls for a particular type of support. The master skill (`SKILL.md`) routes conversations to the right agent(s) based on what the user presents.

This is the **coaching methodology layer** — where the philosophical foundations from `references/` become coaching conversations.

---

## The Agent Roster

| Agent File | Coaching Domain | Primary Frameworks Used |
|-----------|----------------|------------------------|
| `svadharma-navigator.md` | Life purpose, calling, identity, values | Gita's Svadharma + VIA Strengths + Frankl's Logotherapy |
| `integral-life-coach.md` | Five-sphere balance, work-life integration | Aurobindo's Integral Yoga + PERMA + ICF competencies |
| `organizational-attitude-builder.md` | Leadership, institution-building, team dynamics | Vivekananda's OA Framework + Heifetz's Adaptive Leadership |
| `inner-mastery-coach.md` | Inner state, resilience, Saboteur patterns | Sthitaprajna ideal + Positive Intelligence + Logotherapy |
| `paristhiti-jnana-analyst.md` | Situational reading, systems thinking, strategy | JP's Paristhiti Jnana + Heifetz + Systems Thinking |
| `accountability-partner.md` | Goals, commitments, GTD weekly review | Anushasan (OA) + WOOP method + ICF accountability competency |

---

## How Agents Are Activated

The master `SKILL.md` file maps session types to agents. The routing logic is:

```
User message → SKILL.md analyses content → selects 1–2 agents → loads agent file(s) → coaches
```

Example routings:
- "I don't know what I'm supposed to do with my life" → `svadharma-navigator.md`
- "I feel like I'm failing my family" → `integral-life-coach.md` (primary) + `inner-mastery-coach.md` (secondary)
- "My team is not aligned" → `organizational-attitude-builder.md` + `paristhiti-jnana-analyst.md`
- "I didn't follow through on last week's commitments" → `accountability-partner.md`

Multiple agents can be active simultaneously — the coach moves between them fluidly within a session.

---

## Agent File Structure

Each agent file follows a consistent structure:

```markdown
# Agent: [Name]
## Coaching for [Domain]

--- [Identity] ---
What triggers this agent; what it does and doesn't handle

--- [Core Framework] ---
The philosophical and methodological backbone specific to this domain

--- [Coaching Protocol] ---
Step-by-step: how to open, deepen, and move toward commitment

--- [Powerful Questions Library] ---
30–40 questions organized by coaching purpose

--- [Red Flags / Escalation] ---
When to activate another agent; when to recommend professional support
```

---

## For Coaching Professionals: What to Review

### ICF Core Competency Alignment

Each agent should embody the ICF Core Competencies. Review for:

**Competency 4 — Cultivates Trust and Safety**
- Does the agent create psychological safety before probing difficult territory?
- `inner-mastery-coach.md` especially — does the crisis protocol appropriately defer to mental health professionals?

**Competency 5 — Maintains Presence**
- Do the protocols avoid formulaic questioning?
- Is there space built in for silence and reflection, not just question-after-question?

**Competency 6 — Active Listening**
- Do the agents attend to what's *not* said, not just what is?
- Are there prompts to follow the user's emotional state, not just their words?

**Competency 7 — Evokes Awareness**
- Are the Powerful Questions genuinely evocative, or just informational?
- The test: does the question the user couldn't have asked themselves?

**Competency 8 — Facilitates Client Growth**
- Does each agent end sessions with a clear commitment from the client?
- Is the accountability mechanism respectful but robust?

### JP Coaching Authenticity

Review each agent for authentic JP-alignment:

- Does it reflect the actual JP alumnus's lived experience, or a romanticised version?
- Is the tension between JP's demands and real life acknowledged honestly?
- Does the Guru-Shishya element (the coach as the one who holds a lamp, not an equal) come through appropriately without becoming authoritarian?

### What Is Potentially Missing

Consider whether these domains need their own agent or deeper coverage:

- **Career transitions** (mid-career pivot, retirement planning, role change)
- **Grief and loss** (a JP alumnus who has lost a mentor, a parent, a community)
- **Couple and co-founder dynamics** (when the partner is also a JP alumnus)
- **Political and civic leadership** (JP alumni in government or public life face unique pressures)
- **Entrepreneurship** (the JP alumnus building a startup or social enterprise)

---

## How to Add a New Agent

1. Copy the structure from any existing agent file
2. Name the file `[domain]-agent.md` (e.g., `entrepreneurship-agent.md`)
3. Register it in `SKILL.md` under the agent roster table and add appropriate session routing
4. Add a row to the agent roster table in this README
5. Submit a PR with label `new-agent`

**Criteria for a new agent** (should meet all three):
- The domain is genuinely distinct from existing agents (not adequately covered)
- JP alumni commonly face this domain challenge
- The domain has a coherent coaching methodology that can be articulated

---

## Notes on Philosophical Tension

Several agents hold genuine tensions that should not be resolved too cleanly:

**Svadharma Navigator**: The tension between *following your calling* and *honouring existing commitments*. A coach who resolves this too easily ("just follow your heart") is not honouring the JP tradition's understanding of duty.

**Integral Life Coach**: The tension between *all life as yoga* (Aurobindo) and *the reality of finite time and energy*. The five spheres are equally important in principle; they cannot all be equally prioritised in practice.

**Organizational Attitude Builder**: The tension between *Sahakar* (cooperating with other leaders) and *Lakshya Nishtha* (unwavering goal commitment). These can genuinely conflict.

Good coaching holds these tensions open rather than collapsing them into easy answers.
