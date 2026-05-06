# Project Guidelines

## Code Style
- Prefer minimal, readable edits and preserve existing file structure and tone.
- Default to Markdown-first changes; most of this repository is specification and workflow docs, not executable code.
- For `intake/apps/*.html`, keep the apps dependency-free and offline-capable (no network calls, inline CSS/JS in the same HTML file).
- When adding scripts, follow the standards in `CONTRIBUTING.md` (Python 3.10+ preferred, stdlib-first, safe defaults, idempotent behavior).

## Architecture
- `SKILL.md` is the master orchestration layer for coaching behavior and routing.
- `agents/` contains the six core coaching agent specifications.
- `references/` contains philosophical and framework foundations used by agents.
- `gtd/` contains the Markdown-native GTD operating system and task lists.
- `ai-delegation/` contains AI delegation specs and task queue templates.
- `intake/` and `profiles/` contain onboarding and mentee profile workflows.
- `connectors/` contains integration specifications (for example calendar audit).

## Build and Test
- There is no global build step for the core repository (content is primarily Markdown).
- For local app testing in this repo:
  - `cd intake/apps && python3 -m http.server 8080`
- Validate `SKILL.md` frontmatter before submitting structural changes:
  - `python3 -c "import yaml; c=open('SKILL.md').read(); yaml.safe_load(c.split('---')[1]); print('SKILL.md frontmatter: valid')"`

## Conventions
- Keep guidance JP-specific and philosophically accurate; do not generalize away core domain intent.
- Prefer small, additive updates over broad rewrites.
- Use "link, don’t embed": point to existing docs instead of duplicating long guidance.
- High-value references for context:
  - Root overview: `README.md`
  - Contribution and developer workflow: `CONTRIBUTING.md`
  - GTD details: `gtd/GTD-GUIDE.md` and `gtd/README.md`
  - AI delegation details: `ai-delegation/AI-DELEGATION-GUIDE.md` and `ai-delegation/README.md`
  - Folder-specific conventions: each folder `README.md`
