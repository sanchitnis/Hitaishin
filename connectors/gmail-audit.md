# Gmail Connector — Communication Quality Audit
## Aligning Email Patterns with the Five Spheres and Svadharma

---

> *"Communication is the nervous system of any organization. The quality of a leader's correspondence
> reveals the quality of their attention."*

---

## Status

**⚠️ SPECIFICATION COMPLETE — MCP CONNECTOR NOT YET WIRED**

This connector's coaching spec is fully defined below. It requires a Gmail MCP server to be
configured in the Claude session before it can execute. See the "Connector Setup" section.

---

## Purpose

The Gmail Audit converts email patterns into coaching-relevant data. Most leaders spend
significant time in email without ever auditing whether that time is sphere-aligned or
Svadharma-advancing.

The key insight: **how you respond to email reveals what you actually prioritize**, not what you
say you prioritize. Response latency to family vs. work, the ratio of servant correspondence to
command correspondence, and the volume of emails that exist only because of poor delegation — all
of these are coaching data.

**Connector**: Gmail MCP (when active in session)

---

## Sphere Classification Criteria for Email

Classify each thread by its primary correspondence relationship:

| Sphere | Classification Criteria |
|--------|------------------------|
| 🔵 **Atma** | Study groups, Svadhyaya correspondence, philosophical inquiry threads, spiritual community communications |
| 🟡 **Sangha** | Spouse/partner, children, parents, close friends — personal relationship correspondence |
| 🟠 **Karma Bhoomi** | Professional role emails, team coordination, institutional work, client or employer correspondence |
| 🟢 **Samaj Seva** | SPG, alumni network, social purpose projects, mentees (when in non-professional context), community coordination |
| ⚫ **Admin/Residual** | Scheduling, receipts, newsletters, automated notifications, CC'd without requiring response |

---

## The Five-Sphere Correspondence Audit

When the Gmail connector is active, pull the past 7 or 30 days of inbox + sent folder and classify:

```
GMAIL CORRESPONDENCE AUDIT — [Date range]

VOLUME BY SPHERE (threads initiated or replied to):
🔵 Atma-related:       ___ threads (___ %)
🟡 Sangha:             ___ threads (___ %)
🟠 Karma Bhoomi:       ___ threads (___ %)
🟢 Samaj Seva:         ___ threads (___ %)
⚫ Admin/Residual:     ___ threads (___ %)

TOTAL ACTIVE THREADS: ___

DECLARED PRIORITY RANKING (ask mentee first):  1. ___ / 2. ___ / 3. ___ / 4. ___ / 5. ___
ACTUAL CORRESPONDENCE RANKING (from data):     1. ___ / 2. ___ / 3. ___ / 4. ___ / 5. ___

INTEGRITY GAP: Largest gap between declared and actual correspondence priority: [Sphere]

COACHING QUESTION:
"If someone read your sent folder without knowing you, what would they conclude you care most about?"
```

---

## The Response Latency Audit

Response time is one of the most honest signals of priority. Compute average response time
by sphere for the last 30 days:

```
RESPONSE LATENCY BY RELATIONSHIP TYPE

Sangha (family/close friends):     avg ___ hours   [Target: <4 hours for close family]
Samaj Seva (SPG/community):        avg ___ hours   [Target: <24 hours]
Mentees (coaching relationships):  avg ___ hours   [Target: <48 hours]
Karma Bhoomi (professional):       avg ___ hours   [no target — depends on context]
Strangers/new contacts:            avg ___ hours
```

**Latency Integrity Check**: Does response time to family and community match the mentee's declared
priority for Sangha and Samaj Seva — or do institutional contacts consistently receive faster responses?

---

## Communication Tone Assessment

Beyond volume and latency, assess the *quality* of communication in Samaj Seva and Karma Bhoomi threads:

| Pattern | What to Look For | Seva Bhava Indicator |
|---------|-----------------|---------------------|
| **Directive vs. Inviting** | How many emails begin with "I need..." vs. "Could you help me understand..." | High directives = Controller Saboteur; High inviting = Sahakar |
| **CC Inflation** | Is the CC list inflated beyond what is needed? | CC inflation = status performance, not communication |
| **Email as Substitute for Conversation** | Complex relational issues resolved over email instead of in person/call | Avoidance pattern — "the email is there to protect me" |
| **Emotional Acknowledgment** | Does the leader ever acknowledge the human in the exchange, or only the task? | Pure task focus = Karma Bhoomi/Sahakar gap |
| **Appreciation sent** | How many emails express appreciation vs. requests or instructions? | Appreciation ratio: target >10% of sent |

---

## Delegation Identification

Emails that should not require the leader's direct attention:

| Category | Delegation Criteria | Route To |
|----------|-------------------|---------|
| **Scheduling requests** | Any email whose sole purpose is finding a meeting time | AI Drafting Agent (`ai-delegation/agent-drafting.md`) or assistant |
| **Information requests** | Questions answerable from existing documents or FAQs | AI Research Agent or documented FAQ |
| **Routine coordination** | Status updates, forwarded information, "FYI" threads | Acknowledge receipt only; no response needed |
| **CC'd informational** | CC'd as courtesy; no action required | Archive without response |
| **Escalation by others** | Emails where someone else should have been the primary | Coach the sender to the right contact; don't absorb others' responsibilities |

```
DELEGATION CANDIDATES (top 5 threads):
1. [Thread subject] — Reason: ___
2. [Thread subject] — Reason: ___
3. [Thread subject] — Reason: ___
4. [Thread subject] — Reason: ___
5. [Thread subject] — Reason: ___

ESTIMATED TIME RECOVERABLE BY DELEGATION: ___ hours/week
```

---

## Communication Health Dashboard

```
EMAIL HEALTH DASHBOARD — [Date range]

VOLUME METRICS:
Total threads (inbox):       ___
Total sent:                  ___
Sent-to-received ratio:      ___   [<0.3 = reactive mode; >0.5 = proactive/initiating]

INTEGRITY METRICS:
Sphere alignment gap:        [Sphere with largest declared-vs-actual gap]
Response latency gap:        [Relationship type receiving slowest responses relative to declared priority]

TONE METRICS:
Appreciation ratio:          ___% of sent [target >10%]
CC inflation instances:      ___

DELEGATION OPPORTUNITY:
Estimated delegatable volume: ___% of inbox

BIGGEST EMAIL INTEGRITY ISSUE:
_______________________________________________

STRUCTURAL CHANGE RECOMMENDED:
_______________________________________________
```

---

## Common Email Patterns in JP Alumni

| Pattern | What It Reveals | Coaching Response |
|---------|----------------|-------------------|
| **Family emails receive slowest responses** | The phone and inbox have inverted the priority stack | Set a rule: Sangha messages handled before end of day, no exceptions |
| **SPG/community email volume near zero** | Samaj Seva is aspiration, not operation | SPG work is only real when it shows up in the calendar and inbox |
| **Inbox >500 unread** | Overwhelm has been externalized; the inbox owns the leader | Triage system needed; inbox = trusted processing system, not dumping ground |
| **Most sent emails are directives** | Leader is operating as Manager, not as Coach or Servant | Experiment: for one week, respond to team emails with a question rather than an instruction |
| **No emails to mentees in 2+ weeks** | Mentoring relationships are not being maintained | Mentoring is Samaj Seva — it belongs in the calendar and in the sent folder |
| **All-day CC chain participation** | The leader is a bottleneck in others' workflows | Delegation and trust-building work needed; see OA Sahakar component |

---

## Connector Setup

To activate this connector in a Claude session:

1. **MCP server**: A Gmail MCP server must be installed and configured in Claude Desktop or the Claude API environment. Compatible servers include [MCP Gmail](https://modelcontextprotocol.io) or equivalent.
2. **Permissions needed**: Read access to inbox and sent folder — not delete, not compose. Minimum scopes: `gmail.readonly`.
3. **Scope**: Default to last 30 days. For deeper patterns, use 90 days.
4. **Privacy note**: Email content should be summarized/classified by the AI — do not paste raw email content into the coaching conversation or profile without the mentee's explicit consent.

---

## Session Integration

### When to Run the Gmail Audit

| Session | When to invoke | What to pull |
|---------|---------------|-------------|
| **Session 2.2** (Five Spheres Balance) | After sphere self-scoring — validate with email correspondence data | 30-day sphere allocation + latency |
| **Session 3.1** (Weekly Svadhyaya Review) | Quick check: who did I write to vs. who I said I'd prioritize | 7-day latency audit only |
| **Session 4.1** (Leadership Challenge) | When the challenge involves communication patterns or team trust | 30-day tone assessment + delegation audit |

### How to Invoke in a Session

```
GMAIL AUDIT COMMAND:
"Pull the past [7 / 30] days from Gmail inbox and sent folder.
Classify each thread by sphere using the classification criteria in connectors/gmail-audit.md.
Compute volume by sphere, response latency by relationship type, and top 5 delegation candidates.
Produce the Communication Health Dashboard."
```

### How to Close the Audit Loop

1. **Share the sphere allocation and latency data first** — before interpretation
2. **Ask the grounding question**: "If someone read your sent folder without knowing you, what would they conclude you care most about?"
3. **Identify the latency integrity gap**: Which relationship type is receiving the slowest responses relative to declared priority?
4. **One structural change** → GTD next action (e.g., "Inbox zero routine every Sunday"; "All Sangha messages replied to same day")

