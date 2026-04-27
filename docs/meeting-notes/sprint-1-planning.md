# Sprint 1 — Planning Meeting

- **Date:** Mon Apr 27, 2026
- **Time:** 09:00 (~30 minutes)
- **Format:** Online kickoff
- **Attendees:** Rune (Scrum Master), Member B (Developer),
  Member C (QA), Member D (Designer)
- **Facilitator:** Rune

> Member B, C, and D are simulated for this 4-person practice run.
> See [team.md](../team.md).

## Agenda

1. Confirm team roles and GitHub access
2. Review repository and starting backlog
3. Define the sprint goal
4. Select tasks for the sprint and assign owners
5. Agree on communication channels and working norms

## Discussion + decisions

### 1. Roles and GitHub access

- Roles confirmed as listed in [team.md](../team.md).
- Rune had already accepted the GitHub invitation to the
  `Runeov/industry-knowledge` repository. The other members confirmed
  (in the simulation) that they would do the same before the next
  standup.

### 2. Repository and backlog

- Repo reviewed: it already contains a starter `index.html`,
  `config.yml` for Netlify CMS, and a root `README.md`.
- Trello board reviewed. The board uses four columns:
  **To Do → In Progress → Review → Done**.

### 3. Sprint goal

> **Deliver a responsive one-page site with hero, about, and contact
> sections, with QA-validated accessibility and responsiveness, and
> the Netlify CMS admin relocated under `/admin/` for content editors.**

### 4. Task selection (4 cards)

The team agreed on a small, realistic commitment of **4 cards** for a
one-week sprint with a small team:

| # | Card                       | Owner    | Acceptance criteria |
|---|----------------------------|----------|---------------------|
| 1 | Design — wireframe + style direction | Member D | Team approves a low-fi wireframe and colour/typography direction before development starts. |
| 2 | Development — build site + relocate CMS admin | Member B | Semantic HTML, mobile-first responsive CSS. Page works at 320 / 375 / 768 / 1024+ widths. CMS admin reachable at `/admin/`. |
| 3 | QA — manual test checklist | Member C | Checklist covers layout, links, responsiveness, and accessibility basics (contrast, focus states, keyboard navigation, semantic landmarks). Defects logged on Trello and re-tested after fix. |
| 4 | Scrum Master — facilitation | Rune     | Run planning, mid-sprint check-in, and retrospective. Maintain Trello board. Post key updates on GitHub Discussions. Escalate any blocker on the same day it appears. |

### 5. Communication and working norms

- Primary task tracking: **Trello board** (link above).
- Async written updates and important communications:
  **GitHub Discussions** on the repo.
- Daily async standup post per member (Yesterday / Today / Blockers).
- One short live mid-sprint check-in: **Wed Apr 29, 13:00 (~15 min)**.
- Retrospective: **Fri May 1, 15:00 (~20 min)**.
- **Blocker rule:** any blocker is reported the same day it is
  discovered, both on Trello (card) and GitHub Discussions
  (visibility), and the Scrum Master reprioritises immediately.

## Action items

- [x] Rune — create the four Trello cards with acceptance criteria.
- [x] Rune — open a GitHub Discussion thread for the sprint kickoff.
- [x] Member D — start wireframe and style direction (Mon–Tue).
- [x] Member B — wait for wireframe approval, then begin build.
- [x] Member C — draft the QA checklist in parallel with development.

## Sign-off

Sprint 1 plan agreed by all attendees. Sprint started Mon Apr 27.
