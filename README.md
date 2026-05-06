# Team Onepage — Industry Knowledge Sprint 1

> A simple responsive one-page site delivered by a 4-person team practising agile process during Noroff's Industry Knowledge course (FM2AJIK05).

This repository is the working artefact for Sprint 1 of the Industry Knowledge
module. It contains the production code for the one-page site, the Netlify CMS
admin used to edit copy without touching code, and a full evidence pack
documenting how the team actually ran the sprint (planning, daily updates,
retrospective, and reflection).

The goal of this README is to give a marker, a recruiter, or a future team
member enough context to understand what was built, how it was built, and
where to find the proof, all in under a minute of reading.

## Project links

- **GitHub repo:** https://github.com/Runeov/industry-knowledge
- **Course:** Industry Knowledge (FM2AJIK05) — Noroff Vocational College, Frontend Year 2

## Team

| Member   | Role              | GitHub                                |
|----------|-------------------|---------------------------------------|
| Rune     | Scrum Master      | [Runeov](https://github.com/Runeov)   |
| Member B | Developer         | —                                     |
| Member C | Quality Assurance | —                                     |
| Member D | Designer          | —                                     |

Members B/C/D are simulated for this 4-person practice run. The Scrum Master
role is the real student deliverable; supporting roles are documented to
demonstrate process, not to claim work done by other humans. Every card,
comment, and artefact attributed to Members B/C/D exists so the sprint can be
run end-to-end as a realistic 4-person Scrum exercise.

See [`docs/team.md`](docs/team.md) for the full roster, responsibilities, and
the explicit note on simulated roles.

## Sprint summary

- **Sprint window:** Mon Apr 27, 2026 → Fri May 1, 2026 (5 working days)
- **Sprint goal:** Deliver a responsive one-page site (hero / about / contact)
  with QA-validated accessibility and a relocated Netlify CMS admin under
  `/admin/`.
- **Outcome:** Goal achieved. All planned cards moved to Done. One mid-sprint
  blocker (mobile layout overlap < 360px) was raised same-day, fixed, and
  re-verified by QA. Two accessibility issues (CTA contrast + missing focus
  states) were flagged in QA review and fixed before sprint close.

A full narrative of how the sprint ran — including the blocker, the fixes,
and the retrospective actions for next sprint — is in
[`docs/meeting-notes/`](docs/meeting-notes/sprint-1-planning.md) and
[`docs/reflection.md`](docs/reflection.md).

## Repository layout

```
.
├── index.html              # Public one-page site (hero / about / contact)
├── css/styles.css          # Mobile-first, accessible styles
├── js/main.js              # Nav toggle + smooth scroll
├── admin/                  # Netlify CMS admin
│   ├── index.html
│   └── config.yml
├── content/                # Sample CMS content (hero / about / contact)
├── docs/                   # Sprint evidence pack (meeting notes, retro, reflection)
└── README.md
```

## Quick start

### 1. View the site locally

Open `index.html` directly in a browser for the fastest look, or serve the
folder with a small local server so relative paths and any future `fetch`
calls behave correctly:

```bash
# Node (no install required)
npx serve .

# or Python 3
python -m http.server 8000
```

Then visit `http://localhost:3000` (serve) or `http://localhost:8000`
(Python).

### 2. Edit content via the CMS

The Netlify CMS admin lives at `admin/index.html`. It is configured to use
Netlify Identity + git-gateway, which means:

- It must be deployed to Netlify (with Identity enabled) to authenticate.
- Opening `admin/index.html` from the local filesystem will load the UI but
  will not be able to log in or commit changes.
- Once deployed, editors sign in at `/admin/` and commits are pushed to the
  repo's default branch on their behalf.

### 3. Browse the evidence pack

All sprint process artefacts (meeting notes, retrospective, reflection,
evidence index) live in [`docs/`](docs/README.md) and are linked individually
in the next section.

## Documentation

- [Evidence pack overview](docs/README.md)
- [Team roster](docs/team.md)
- [Sprint 1 planning notes](docs/meeting-notes/sprint-1-planning.md)
- [Sprint 1 daily updates](docs/meeting-notes/sprint-1-daily-updates.md)
- [Sprint 1 retrospective](docs/meeting-notes/sprint-1-retrospective.md)
- [Reflection (Moodle submission)](docs/reflection.md)
- [Evidence index — what proves what](docs/evidence-index.md)

## Accessibility & quality

Accessibility was a formal acceptance criterion for this sprint, not an
afterthought. The site uses:

- Semantic HTML landmarks (`header`, `nav`, `main`, `section`, `footer`)
- Visible focus states on every interactive element
- WCAG AA contrast on the primary call-to-action
- Keyboard-reachable navigation, including the mobile menu toggle
- Responsive breakpoints verified at 320, 375, 768, and 1024 px

QA signed off on both the mobile overlap fix and the contrast/focus fixes
before sprint close; the specific tickets and evidence are cross-referenced
in [`docs/evidence-index.md`](docs/evidence-index.md).

## License / academic note

This repository is a student deliverable for Noroff's Industry Knowledge
course. Code is provided as-is for educational purposes. Third-party tooling
(Netlify CMS, Netlify Identity) retains its own upstream licensing.
