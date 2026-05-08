# Google Drive Connector — Vision Document Audit
## Keeping Strategic Documents Alive and Aligned with Svadharma

---

> *"A vision that lives only in memory is a vision that is slowly dying.
> What is written and revisited becomes what is lived."*

---

## Status

**⚠️ SPECIFICATION COMPLETE — MCP CONNECTOR NOT YET WIRED**

This connector's coaching spec is fully defined below. It requires a Google Drive MCP server to be
configured in the Claude session before it can execute. See the "Connector Setup" section.

---

## Purpose

Most JP alumni have strategic documents — a 10-year vision, a career plan, an SPG proposal,
a personal mission statement — stored in Google Drive. Over time, these documents go stale while
daily life continues without reference to them.

The key insight: **a vision that is never re-read gradually loses its grip on the leader's decisions**.
The Drive Audit surfaces document staleness, cross-references current Sankalpas against written
vision statements, and flags misalignments — so that the leader's written intentions and their
lived direction stay coherent.

**Connector**: Google Drive MCP (when active in session)

---

## Recommended Folder Structure

The mentee should create this folder structure in their Google Drive before using this connector:

```
My Drive/
└── Hitaishin/
    ├── vision/        ← 10-year vision, life purpose, Svadharma articulations
    ├── spg/           ← SPG plans, charters, progress documents
    ├── annual/        ← Annual retreat outputs, one subfolder per year (e.g., 2024/, 2025/)
    └── learning/      ← Key learning documents, reading notes, quotes to live by
```

Only this folder and its subfolders are accessed. The connector does not scan the rest of Drive.

---

## Document Staleness Thresholds

| Time since last opened | Status | Coaching Action |
|------------------------|--------|----------------|
| < 30 days | 🟢 **Current** | No action needed |
| 30–90 days | 🟡 **Review needed** | Prompt: "Open this document — does it still describe the person you are becoming?" |
| > 90 days | 🔴 **Stale** | Treat as an adaptive challenge: why has this vision document not been needed? |
| > 180 days | ⚫ **Dormant** | Coaching question: "Is this vision still alive in you, or has it been quietly abandoned?" |

---

## The Vision Document Audit

When the Drive connector is active, index the `Hitaishin/` folder and produce:

```
GOOGLE DRIVE VISION AUDIT — [Date]

DOCUMENT STATUS:
Folder: Hitaishin/vision/
  [Document name]    Created: [date]    Last opened: [date]    Status: 🟢/🟡/🔴/⚫

Folder: Hitaishin/spg/
  [Document name]    Created: [date]    Last opened: [date]    Status: 🟢/🟡/🔴/⚫

Folder: Hitaishin/annual/
  [Year] retreat doc    Created: [date]    Last opened: [date]    Status: 🟢/🟡/🔴/⚫

SUMMARY:
Total documents: ___
Current (< 30 days): ___
Review needed (30–90 days): ___
Stale (> 90 days): ___
Dormant (> 180 days): ___

COACHING QUESTION:
"Is your written vision still the vision you are living toward — or has it silently changed?"
```

---

## The Sankalpa-Vision Alignment Check

The most powerful use of this connector is checking whether the mentee's *current active Sankalpas*
(from their profile) are grounded in their *written long-term vision*.

```
SANKALPA-VISION ALIGNMENT — [Date]

CURRENT ACTIVE SANKALPAS (from profile):
🔵 Atma:         [from profile]
🟡 Sangha:       [from profile]
🟠 Karma Bhoomi: [from profile]
🟢 Samaj Seva:   [from profile]
🔴 Sharira-Prana:[from profile]

10-YEAR VISION STATEMENTS (extracted from Hitaishin/vision/):
[Vision for Atma sphere from document]
[Vision for Sangha sphere from document]
[Vision for Karma Bhoomi sphere from document]
[Vision for Samaj Seva from document]
[Vision for Sharira-Prana from document]

ALIGNMENT ASSESSMENT (per sphere):
🔵 Atma:          High / Partial / Misaligned / Not in vision document
🟡 Sangha:        High / Partial / Misaligned / Not in vision document
🟠 Karma Bhoomi:  High / Partial / Misaligned / Not in vision document
🟢 Samaj Seva:    High / Partial / Misaligned / Not in vision document
🔴 Sharira-Prana: High / Partial / Misaligned / Not in vision document

COACHING QUESTION:
"Where the Sankalpa and the vision are misaligned — is the Sankalpa wrong,
or has the vision evolved and not yet been updated?"
```

---

## Year-over-Year Vision Tracking

When annual retreat documents exist in `Hitaishin/annual/`, extract and compare goal statements
across years to reveal how the mentee's vision has evolved:

```
ANNUAL VISION EVOLUTION — [Current year] vs. [Prior year]

SVADHARMA STATEMENT:
[Year-1]: "My Svadharma is to ___..."
[Year]:   "My Svadharma is to ___..."
Change: Evolved / Refined / Significant shift / Same

KARMA BHOOMI 10-YEAR GOAL:
[Year-1]: [statement]
[Year]:   [statement]
Change: Evolved / Refined / Significant shift / Same

SPG COMMITMENT:
[Year-1]: [statement]
[Year]:   [statement]
Change: More specific / Less specific / New direction / Same

PATTERN OBSERVATION:
Is the vision becoming more precise and embodied over time — or more vague and aspirational?
```

---

## SPG Document Health Check

For mentees with active SPG work, assess the currency and coherence of their SPG documents:

```
SPG DOCUMENT HEALTH — [Date]

PLAN DOCUMENT: [filename]    Last updated: [date]
PROGRESS DOCUMENT: [filename]    Last updated: [date]

SPG THEORY OF CHANGE: [extract from document]
Current with lived reality: Y / N / Partially

OPEN COMMITMENTS in SPG document (last session's stated next actions):
1. [commitment]    Status: [resolved in doc / not yet reflected]
2. [commitment]    Status: [resolved in doc / not yet reflected]

COACHING QUESTION:
"Is this SPG plan a living document guiding your action — or a record of a previous chapter?"
```

---

## Common Drive Patterns in JP Alumni

| Pattern | What It Reveals | Coaching Response |
|---------|----------------|-------------------|
| **Vision doc last opened 6+ months ago** | Strategy is running on memory, not on written intention | Annual retreat or Session 4.2 (Purpose Recalibration) triggered |
| **Multiple unfinished vision drafts** | The leader is in a period of transition — no settled vision yet | This is valuable data: sit with the incompletion rather than forcing resolution |
| **SPG plan not updated in 3+ months** | SPG work is either stalled or not being documented | Surface in next Session 3.1 or 3.4 — is the SPG alive? |
| **Annual docs stop at a particular year** | That year may have been a turning point — documents as archaeology | Use in Session 3.5 or 4.2: what happened that year? |
| **No Hitaishin folder at all** | Strategic documents are scattered or non-existent | Assign as a next action: create the folder structure; consolidate existing vision docs |
| **Sankalpa and vision well-aligned across all spheres** | Coherence achieved — coach can zoom out and work at a deeper level | Transition to Phase 4 work: depth, not breadth |

---

## Connector Setup

To activate this connector in a Claude session:

1. **MCP server**: A Google Drive MCP server must be installed and configured in Claude Desktop or the Claude API environment. Compatible servers include [MCP Drive](https://modelcontextprotocol.io) or equivalent.
2. **Permissions needed**: Read access to the `Hitaishin/` folder only — not all of Drive. Scope: `drive.file` or folder-scoped read.
3. **First-time setup with mentee**: Ask the mentee to create the `Hitaishin/` folder structure (above) and populate it with their existing strategic documents before the connector is used.
4. **Privacy note**: Document content is used only for alignment checks. Do not reproduce lengthy document excerpts in the coaching conversation without the mentee's consent — extract key intent statements only.

---

## Session Integration

### When to Run the Drive Audit

| Session | When to invoke | What to pull |
|---------|---------------|-------------|
| **Session 2.3** (Svadharma Clarity) | At the start — does a written vision exist? What does it say? | Full document status + Svadharma statement extract |
| **Session 3.4** (Quarterly Review) | Cross-reference quarterly intentions against written vision | Alignment check only |
| **Session 3.5** (Annual Retreat) | Full audit — all folders, year-over-year comparison | Complete audit + evolution tracking |
| **Session 4.2** (Purpose Recalibration) | Triggered by stale or conflicting vision documents | Full audit + year-over-year |

### How to Invoke in a Session

```
DRIVE AUDIT COMMAND:
"Index the Hitaishin/ folder in Google Drive.
For each document, report name, creation date, last-opened date, and staleness status.
For the most recent vision document, extract the Svadharma statement and Karma Bhoomi 10-year goal.
Cross-reference against the current Active Sankalpas in the mentee's profile.
Produce the Vision Document Audit and Sankalpa-Vision Alignment Check."
```

### How to Close the Audit Loop

1. **Share the document status table first** — let the leader see which documents are stale before any interpretation
2. **Ask the grounding question**: "Is your written vision still the vision you are living toward — or has it silently changed?"
3. **Run the alignment check** for any sphere where Sankalpa and vision seem disconnected
4. **Determine the cause of misalignment**: Is the Sankalpa too tactical? Has the vision evolved? Was the vision never grounded?
5. **One structural change** → GTD (e.g., "Update 10-year vision document by end of this quarter")

