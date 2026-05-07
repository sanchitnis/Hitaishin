# Feedback Inbox — Hitaishin Improvement Loop

Rolling queue for user feedback, suggestions, bug reports, and improvement ideas.

## How To Use

1. Add new entries at the top under "Open Items".
2. Triage each item with one status: `accepted`, `deferred`, `rejected`, `needs-data`.
3. For `accepted`, create a linked action in `../coach/00-coach-accepted.md` and route through GTD.
4. Close the feedback item with decision date and rationale.

## Triage Rules

- `accepted`: Clear value, aligned with mission, feasible now.
- `deferred`: Valuable but not now; add revisit date.
- `rejected`: Misaligned, unsafe, duplicate, or low-value; include rationale.
- `needs-data`: Good direction but evidence is insufficient.

## Open Items

- [ ] [FB-YYYYMMDD-001] Title: 
  - Source: user/domain expert/developer
  - Date:
  - Context (session/file/feature):
  - Observed issue:
  - Suggested improvement:
  - Evidence/examples:
  - Impact (low/medium/high):
  - Scope (coaching-methodology/content/process/app):
  - Owner:
  - Triage status: needs-data
  - Decision notes:
  - Linked action(s):
  - Target release/review date:

## Closed Items

- [x] [FB-20260507-003] Add beginner interactive orientation so users can understand and use the system without reading markdown files
  - Decision: accepted -> implemented
  - Rationale: Added beginner interactive orientation script and SKILL routing for no-doc onboarding flow
  - Linked action(s): references/beginner-interactive-orientation.md; SKILL.md (Session Type 13); COACHING-SESSION-WORKFLOW.md (Session 0.0)
  - Closed date: 2026-05-07

- [x] [FB-20260507-001] Use Bhagavad Gita management materials to strengthen leadership coaching
  - Decision: accepted -> implemented
  - Rationale: Added dedicated management wisdom playbook and integrated it into leadership and review protocols
  - Linked action(s): references/management-wisdom-playbook.md; SKILL.md (Sessions 5 and 7); COACHING-SESSION-WORKFLOW.md (Sessions 2.4 and 4.1)
  - Closed date: 2026-05-07

- [x] [FB-20260507-002] Add curated Indian wisdom lines and modern self-development quotations to coaching prompts
  - Decision: accepted -> implemented
  - Rationale: Added curated Subhashita, Gita, Upanishad, idiom, and modern leadership insight sections with usage rules
  - Linked action(s): references/management-wisdom-playbook.md
  - Closed date: 2026-05-07

- [x] [FB-EXAMPLE-000] Example closed item
  - Decision: accepted
  - Rationale: Demonstrates format only
  - Linked action(s): gtd/_tasks/coach/00-coach-accepted.md
  - Closed date: 2026-05-07

---

Last updated: 2026-05-07
