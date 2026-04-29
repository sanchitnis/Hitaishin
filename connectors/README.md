# `connectors/` — External Tool Integrations

**Primary audience: Developers · Power users with Google Workspace**

---

## What This Folder Contains

The `connectors/` folder defines how the Hitaishin integrates with external tools and services — primarily via Claude's MCP (Model Context Protocol) connector system.

```
connectors/
├── README.md              ← You are here
└── calendar-audit.md      ← Google Calendar integration: Five-Sphere time audit
```

---

## Current Connectors

### `calendar-audit.md` — Google Calendar

**What it does**: Reads your Google Calendar events for a given week, classifies each meeting by its primary life sphere, calculates a Five-Sphere time allocation report, runs a meeting quality audit (Generative / Maintenance / Consuming), and produces a Calendar Health Dashboard.

**Requires**: Google Calendar MCP connector active in your Claude session.

**How to activate in a session**:
```
Audit my calendar for this week using the Five Spheres framework
```

**Output includes**:
- Time allocated per sphere (hours and %)
- Integrity Gap (declared priorities vs. actual time)
- Meeting quality scores
- Delegation recommendations for operational meetings
- Structural changes suggested

---

## For Developers: Adding New Connectors

### What makes a good connector

A connector is valuable when it connects an *external data source* to a *coaching insight*. The best connectors:

1. **Surface data the user can't easily see themselves** — patterns across many events, emails, or documents
2. **Map to one or more of the Five Spheres** — so the data becomes coaching-relevant
3. **Require minimal user action** — set up once, runs automatically

### Connector file structure

Each connector file follows this template:

```markdown
# [Tool Name] Connector — [What it does]
## [Brief description]

---
## Purpose
[Why this integration matters for coaching]

## Connector Setup
[MCP URL, authentication requirements, permissions needed]

## Input (what to provide)
[What the user or skill needs to pass]

## Processing Logic
[What Claude does with the data]

## Output Format
[The structured report produced]

## Coaching Insights Generated
[How this feeds back into coaching conversations]

## Active Use Cases
[Table of specific coaching scenarios this enables]
```

### Connectors roadmap

These connectors would add significant value — good first contributions:

---

#### 📧 Gmail Connector
**File**: `connectors/gmail-audit.md`

**What it would do**:
- Read subject lines and senders from the past week
- Classify emails by sphere (Atma/Sangha/Karma/Samaj/Sharira)
- Identify response time patterns (reactive vs. proactive)
- Flag emails that should have been delegated
- Surface communication patterns relevant to Organizational Attitude

**MCP**: Gmail MCP (`https://gmailmcp.googleapis.com/mcp/v1`)

**Coaching insight**: "You spent 6 hours this week on email. 70% was Karma Bhoomi. Your Samaj Seva inbox has 12 unanswered messages from SPG collaborators — older than 7 days."

---

#### 📂 Google Drive Connector
**File**: `connectors/drive-audit.md`

**What it would do**:
- List recently created/modified documents by folder
- Identify documents linked to active projects in GTD
- Flag projects with no associated documents (may be under-documented)
- Surface reference material relevant to the current coaching session

**MCP**: Google Drive MCP (`https://drivemcp.googleapis.com/mcp/v1`)

**Coaching insight**: Before a session on the SPG water project, automatically surface the relevant proposal document.

---

#### 📊 Supabase Connector (for coaching practices)
**File**: `connectors/supabase-data.md`

**What it would do**:
- Store session logs, Five Spheres scores, and Sankalpa data persistently
- Enable trend analysis across months and years
- Support a coach managing multiple JP alumni mentees
- Generate aggregate insights (anonymised) for JP community research

**MCP**: Supabase MCP (`https://mcp.supabase.com/mcp`)

**Coaching insight**: "Across your last 8 sessions, your Atma sphere score has declined 3 consecutive quarters. This is a pattern worth naming directly."

---

#### 🎨 Canva Connector (for personal brand)
**File**: `connectors/canva-brand.md`

**What it would do**:
- Generate branded social media graphics for LinkedIn posts
- Create visual frameworks (the Five Spheres wheel, OA radar chart) as shareable images
- Support the personal brand / Digital Twin coaching objective

**MCP**: Canva MCP (`https://mcp.canva.com/mcp`)

---

#### 📅 Mermaid Chart Connector (for planning visualisation)
**File**: `connectors/mermaid-planning.md`

**What it would do**:
- Render GTD project timelines as Gantt charts
- Visualise the Five Spheres as a radar diagram
- Create SPG organisation charts
- Generate coaching journey roadmaps

**MCP**: Mermaid Chart MCP (`https://chatgpt.mermaid.ai/anthropic/mcp`)

---

### MCP connector integration pattern

All connectors follow the same integration pattern in `SKILL.md`:

```yaml
# In SKILL.md frontmatter
compatibility:
  connectors:
    - Google Calendar
    - Gmail
    - Google Drive
    - Supabase
```

And in the connector file itself, document the MCP URL and any required permissions:

```markdown
## Connector Setup

**MCP URL**: https://calendarmcp.googleapis.com/mcp/v1
**Required permissions**: Read-only access to calendar events
**Authentication**: OAuth 2.0 via Google account (handled by Claude's MCP system)
**Activation**: Connector must be enabled in Claude Settings → Integrations
```

### Testing a connector

Before publishing a new connector file:

1. Verify the MCP URL is correct and the connector works in a live Claude session
2. Test with minimal data first (1 week of calendar, not 1 year)
3. Verify the output format matches what the coaching workflow expects
4. Document failure modes (what happens if the calendar is empty? If the user has no Google account?)
5. Add a "Common Issues" section to the connector file

### Privacy considerations for connectors

Any connector that reads personal data (email, calendar, documents) must include:

```markdown
## Privacy Notes
- Data is read in real-time; nothing is stored by the connector itself
- Claude processes the data within the session only
- No data is sent to third parties
- Users should review Google's MCP data handling policy before connecting
```

The Prabodhini tradition's commitment to honesty (*Satyam*) extends to data handling: be transparent about what is read, processed, and retained.
