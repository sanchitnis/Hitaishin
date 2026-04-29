# `ai-delegation/` — AI Agent Architecture

**Primary audience: Developers · Researchers · Innovation-minded users**

---

## What This Folder Contains

The `ai-delegation/` folder contains the **specifications, protocols, and task queues** for five AI agents that handle work on behalf of the Prabodhini leader. This is the innovation layer — the feature that makes this coaching system genuinely novel.

```
ai-delegation/
├── AI-DELEGATION-GUIDE.md    ← Master guide: philosophy, roster, decision matrix
├── agent-research.md         ← Research Agent: deep research and synthesis
├── agent-drafting.md         ← Drafting Agent: first-draft production
├── agent-planning.md         ← Planning Agent: project decomposition + scheduling
└── agent-inbox-review.md     ← Inbox Agent + Review Agent (combined file)
```

---

## The Core Idea

**Traditional GTD**: Delegate to humans what humans can do better than you.

**Prabodhini AI-Augmented GTD**: Delegate to AI agents what AI can do competently — so the leader's finite human energy is reserved for what only *this particular human* can uniquely do.

The human's irreplaceable domain:
- Svadharma decisions (only you know your deepest calling)
- Genuine relational presence (mentoring, family, community)
- The difficult conversation (requires your full humanity)
- Original wisdom and philosophical insight
- Strategic judgement that requires values and context

The AI agent's appropriate domain:
- Background research and synthesis
- First-draft production
- Project decomposition and scheduling
- Inbox processing and pattern detection
- Pre-processing weekly reviews

---

## For Users: How to Use the Agents

### Step 1: Identify a delegatable task

In your GTD Next Actions list, when you have a task that is primarily information-gathering, synthesis, or drafting, tag it `#ai-delegate`.

### Step 2: Fill in the agent input format

Open the relevant agent file and copy the **INPUT FORMAT** template. Fill it in — this is the brief you're giving the agent.

**Example for Research Agent:**
```markdown
### RESEARCH REQUEST
Date: 2026-05-01
Sphere: #samaj
Project: SPG Water Initiative Proposal

Research Question: 
What are the most effective models for community-led water management 
in rural India, with evidence of sustainable outcomes?

Scope: Deep dive | Recency: Last 5 years | Geography: India focus
Expected Output: 3-page synthesis with table of models
Deadline: 2026-05-10 | Priority: M
```

### Step 3: Give the brief to Claude

In a Claude conversation (with the skill active):
```
Please act as the Research Agent and complete this research request:
[paste the filled input format]
```

### Step 4: Review the output

The agent produces output in a structured format. You review it, apply your judgement, and either use it directly (with your edits) or redirect with more specificity.

### Step 5: Record in Waiting For

Add a row to `gtd/04-waiting-for.md`:
```markdown
| [Task] | Research Agent | [DATE] | [DATE] | — | — |
```

Check back when the output is ready, mark received, and record quality score.

---

## For Developers: Architecture and Extension

### Current agent architecture

Each agent is currently a **specification document** — a structured Markdown file that defines the agent's mandate, input format, output template, and task queue. The *execution* happens when a human pastes the input format into a Claude conversation and Claude acts as that agent.

This is a **human-in-the-loop agentic system** — deliberately so, for the current version.

### Moving toward autonomous agents

The specifications in this folder are designed to be promotable to **autonomous Claude agents** as the technology matures. Here is the roadmap:

#### Phase 1 (current): Specification-as-prompt
The agent file is the system prompt. A human manually triggers each agent conversation.

#### Phase 2: Claude Code integration
Using Claude Code, agents can be run as slash commands:
```bash
/research "What are the best models for gifted education in India?"
/draft --type=linkedin --topic="AI and ancient wisdom"
/plan --sankalpa="Publish AI ethics framework by Q3"
```

Each command maps to an agent spec file as the system prompt.

#### Phase 3: Scheduled autonomous runs
Using Claude's API with cron-like scheduling:
- **Inbox Agent**: Runs every morning, processes new email captures, outputs to `00-inbox.md`
- **Review Agent**: Runs every Sunday afternoon, pre-processes the weekly review
- **Research Agent**: Runs on queued research briefs overnight

#### Phase 4: Full agentic workflow
Agents call each other. The Inbox Agent identifies a research need, queues a Research Agent task, which generates output that the Drafting Agent uses to produce a first draft — all without human intervention in between.

### Claude API integration example

```python
import anthropic
from pathlib import Path

def run_research_agent(research_brief: str) -> str:
    """Run the Research Agent with a given brief."""
    
    # Load agent spec as system prompt
    agent_spec = Path("ai-delegation/agent-research.md").read_text()
    
    client = anthropic.Anthropic()
    
    message = client.messages.create(
        model="claude-sonnet-4-6",
        max_tokens=4096,
        system=f"""You are the Prabodhini Catalyst OS Research Agent.
        
Your full specification:
{agent_spec}

Follow the OUTPUT TEMPLATE exactly. Always end with LIMITATIONS & CAVEATS.""",
        messages=[
            {
                "role": "user",
                "content": f"Please complete this research request:\n\n{research_brief}"
            }
        ]
    )
    
    return message.content[0].text


def run_inbox_agent(inbox_items: list[str]) -> str:
    """Process a batch of inbox items."""
    agent_spec = Path("ai-delegation/agent-inbox-review.md").read_text()
    inbox_text = "\n".join([f"- {item}" for item in inbox_items])
    
    client = anthropic.Anthropic()
    message = client.messages.create(
        model="claude-sonnet-4-6",
        max_tokens=2048,
        system=agent_spec,
        messages=[{
            "role": "user", 
            "content": f"### INBOX BATCH\n{inbox_text}"
        }]
    )
    return message.content[0].text
```

### Adding a new agent

1. Create `agent-[name].md` following the structure of existing agents:
   - Agent Identity (mandate, what it handles and doesn't)
   - Input Format (the brief template)
   - Output Template (the structured output format)
   - Active Tasks table (the queue)
   - Quality Log (for tracking improvement)

2. Add it to the roster table in `AI-DELEGATION-GUIDE.md`

3. Add trigger recognition in `SKILL.md` so Claude routes to it appropriately

4. Update this README

**Good candidates for new agents:**
- **Meeting Prep Agent**: Given a meeting attendee list and agenda, research participants and prepare talking points
- **Mentee Progress Agent**: Given session logs, track commitment patterns and surface coaching insights
- **Content Calendar Agent**: Given personal brand themes, generate a monthly LinkedIn content calendar
- **SPG Monitor Agent**: Given an SPG domain, monitor news and research for weekly briefing

### MCP (Model Context Protocol) integration

For advanced users, agents can be connected to external services via MCP:

```yaml
# In SKILL.md frontmatter
compatibility:
  connectors:
    - Google Calendar     # for Review Agent calendar analysis
    - Gmail               # for Inbox Agent email processing  
    - Google Drive        # for Research Agent document access
    - Supabase            # for persistent task queue storage
```

**Example MCP workflow:**
1. Gmail MCP → Inbox Agent receives and classifies emails → appends to `00-inbox.md`
2. Calendar MCP → Review Agent reads week's calendar → produces sphere balance report
3. Drive MCP → Research Agent reads background documents → produces synthesis

### Data persistence (beyond Markdown files)

For teams or coaching practices serving multiple JP alumni, consider:

**Supabase schema (PostgreSQL)**:
```sql
-- Mentee profiles
CREATE TABLE mentees (
  id UUID PRIMARY KEY,
  name TEXT,
  jp_batch TEXT,
  created_at TIMESTAMP,
  profile_data JSONB  -- stores psychometric results
);

-- Session logs
CREATE TABLE sessions (
  id UUID PRIMARY KEY,
  mentee_id UUID REFERENCES mentees(id),
  date DATE,
  primary_agent TEXT,
  key_insight TEXT,
  commitments JSONB,
  sphere_scores JSONB
);

-- GTD tasks with sphere tagging
CREATE TABLE tasks (
  id UUID PRIMARY KEY,
  mentee_id UUID REFERENCES mentees(id),
  sphere TEXT CHECK (sphere IN ('atma','sangha','karma','samaj','sharira')),
  status TEXT CHECK (status IN ('inbox','next','waiting','someday','done')),
  content TEXT,
  sankalpa_id UUID,
  ai_delegated BOOLEAN DEFAULT FALSE,
  created_at TIMESTAMP,
  completed_at TIMESTAMP
);
```

### Testing agents

Before deploying automated agent workflows, test manually:

1. Fill in an input format completely
2. Paste into Claude with just the agent spec file as context (no other skill files)
3. Evaluate output against the quality criteria in the agent file
4. Score 1–5 on: accuracy, completeness, usability, format adherence
5. Document any systematic weaknesses in the Quality Log section

---

## Ethical Architecture

The `AI-DELEGATION-GUIDE.md` contains five ethical principles governing agent use. They are not advisory — they are architectural constraints:

1. **Transparency** — AI-assisted outputs are identified as such where relevant
2. **Accountability** — The human is fully responsible for every output bearing their name
3. **Integrity** — AI is not used to fake the appearance of work not actually thought through
4. **Depth** — The wisdom must come from the human; AI handles the surface
5. **Non-attachment** — If AI produces something better than the human would have, celebrate it

These principles are grounded in the Prabodhini tradition's commitment to honesty (*Satyam*) and the Advaita recognition that ego-protection is the enemy of growth.
