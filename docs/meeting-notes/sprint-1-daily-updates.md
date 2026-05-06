# Sprint 1 — Daily Updates

Sprint dates: **Mon Apr 27, 2026 → Fri May 1, 2026**.
Updates were posted asynchronously each day, with one live
mid-sprint check-in on Wednesday and a retrospective on Friday.

> Member B, C, and D are simulated for this 4-person practice run.
> See [team.md](../team.md).

---

## Mon Apr 27, 2026 — Day 1 (Sprint kickoff)

**Live planning meeting at 09:00.** See
[sprint-1-planning.md](sprint-1-planning.md) for the full notes.

### Standups

- **Rune (Scrum Master)**
  - Yesterday: prepared the project board and sprint goal draft.
  - Today: facilitated planning, created the 4 cards on the board,
    posted kickoff message to GitHub Discussions.
  - Blockers: none.
- **Member B (Dev)**
  - Yesterday: reviewed repo and existing `index.html` / `config.yml`.
  - Today: setting up local dev, waiting for the wireframe before
    starting the build.
  - Blockers: none — wireframe needed by end of Tuesday.
- **Member C (QA)**
  - Yesterday: skimmed accessibility checklist references.
  - Today: drafting the manual test checklist (layout, links,
    responsiveness, contrast, focus, keyboard nav, landmarks).
  - Blockers: none.
- **Member D (Design)**
  - Yesterday: collected references for hero / about / contact layouts.
  - Today: low-fi wireframe + colour/typography direction.
  - Blockers: none.

### Scrum Master notes / board changes

- 4 project-board cards created in **To Do**.
- Wireframe card moved to **In Progress** by Member D.
- Kickoff message posted on GitHub Discussions.

---

## Tue Apr 28, 2026 — Day 2

### Standups

- **Rune** — Today: check-in with Member D on wireframe; review board.
  Blockers: none.
- **Member B** — Today: scaffolded HTML structure (semantic
  landmarks: `header`, `main`, `section`, `footer`). Waiting for
  wireframe sign-off before styling.
  Blockers: none.
- **Member C** — Today: QA checklist v1 drafted, shared on
  Discussions for feedback.
  Blockers: none.
- **Member D** — Today: wireframe + colour/typography direction
  finished and shared. Approved by team late afternoon.
  Blockers: none.

### Scrum Master notes / board changes

- Design card moved **In Progress → Review → Done** by EOD.
- Development card moved to **In Progress** for Member B.

---

## Wed Apr 29, 2026 — Day 3 (Mid-sprint check-in + blocker)

**Live mid-sprint check-in at 13:00 (~15 min).**

### Standups

- **Rune** — Today: ran mid-sprint check-in. Logged blocker (see
  below). Reprioritised polish work.
- **Member B** — Today: implemented mobile-first CSS for hero / about
  / contact. **Reported a blocker:** the mobile layout breaks at
  narrow widths — the CTA button overlaps the hero text below
  ~360px viewport width.
- **Member C** — Today: started running the QA checklist against the
  in-progress build.
- **Member D** — Today: available to support spacing/typography
  adjustments to fix the layout issue.

### Blocker — mobile layout overlap

- **Reported by:** Member B at the 13:00 check-in.
- **Symptom:** CTA button overlaps the hero text below ~360px
  viewport width.
- **Same-day actions by Scrum Master (Rune):**
  - Logged the blocker as a comment on the Development card
    and posted a visibility note on GitHub Discussions.
  - Reprioritised the Development card to focus on the fix before
    any visual polish.
  - Asked Member D for a quick spacing / type-scale recommendation.
  - Asked Member C to add explicit checks at **320 / 375 / 768 /
    1024** viewport widths to the QA checklist.
- **Resolution timeline:**
  - Wed afternoon — Member D suggested tighter spacing and a
    smaller heading scale below 400px.
  - Thu morning — Member B applied the CSS fix.
  - Thu afternoon — Member C re-verified at all four target widths.
    Pass.

### Scrum Master notes / board changes

- Development card stayed in **In Progress**; comment added with the
  blocker and resolution plan.
- QA card moved to **In Progress**.

---

## Thu Apr 30, 2026 — Day 4

### Standups

- **Rune** — Today: monitored fix loop, kept the board current,
  posted a status update on GitHub Discussions.
- **Member B** — Today: applied the mobile spacing fix; later in the
  day fixed two further QA findings (see below).
- **Member C** — Today: re-verified the mobile widths. **Two new
  findings:** (1) primary CTA button fails WCAG AA contrast
  (below 4.5:1); (2) nav links have no visible focus state. Both
  logged on the project board and re-verified after the fix.
- **Member D** — Today: provided a darker accessible colour for the
  CTA and a focus-state style suggestion.

### Fix loop (same day)

- Contrast: CTA colour darkened to meet 4.5:1.
- Focus state: visible outline / focus ring added to nav links and
  the CTA.
- Member B pushed the fixes Thursday afternoon.
- Member C re-tested late Thursday — both pass.

### Scrum Master notes / board changes

- Development card moved to **Review** after the accessibility
  fixes.
- QA card stayed in **In Progress** for the final pass.

---

## Fri May 1, 2026 — Day 5 (Final QA + retrospective)

### Standups

- **Rune** — Today: confirmed final QA pass, moved cards to
  **Done**, ran the retrospective at 15:00.
- **Member B** — Today: relocated the Netlify CMS admin under
  `/admin/` and verified it loads. No new defects.
- **Member C** — Today: full final pass of the QA checklist.
  All checks green: layout, links, responsiveness at 320 / 375 /
  768 / 1024+, contrast, focus states, keyboard navigation,
  semantic landmarks.
- **Member D** — Today: visual sign-off on the final build.

### Sprint summary

- Sprint goal **achieved**.
- All 4 cards now in **Done**.
- Site delivered: responsive hero / about / contact, accessibility
  issues resolved, CMS admin cleanly relocated to `/admin/`.

### Retrospective

Held at 15:00 (~20 min). Notes in
[sprint-1-retrospective.md](sprint-1-retrospective.md).

---

## Communication log — GitHub Discussions snippets

These are the messages used as the "important communications
recorded on GitHub Team Discussion Boards" required by the marking
guide. All five Discussion threads are live on GitHub: #1
(kickoff), #2 (blocker), #3 (review handoff), #4 (sprint
completion), and #5 (retro summary). Each snippet below is
reproduced verbatim so the wording is preserved alongside its
public URL.

### 1. Sprint kickoff (Mon Apr 27)

**Posted:** <https://github.com/Runeov/industry-knowledge/discussions/1>

> **Sprint 1 kickoff — Team Onepage**
> Sprint dates: Apr 27 → May 1.
> Goal: deliver a responsive one-page site (hero / about / contact)
> with QA-validated accessibility and the Netlify CMS admin
> relocated under `/admin/`.
> 4 cards on the project board, owners assigned. Mid-sprint check-in
> Wed 13:00, retro Fri 15:00. Blockers go on the project board + here the same
> day. — Rune (SM)

### 2. Blocker raised (Wed Apr 29)

**Posted:** <https://github.com/Runeov/industry-knowledge/discussions/2>

> **Blocker — mobile layout overlap (<360px)**
> Reported by Member B at today's check-in: CTA button overlaps the
> hero text below ~360px. I've reprioritised the Development card
> to fix this first. Member D is sharing a spacing/type-scale
> suggestion; Member C is adding 320 / 375 / 768 / 1024 viewport
> checks to the QA checklist. Target: fix and re-verify by EOD
> Thursday. — Rune (SM)

### 3. Review handoff (Thu Apr 30)

**Posted:** <https://github.com/Runeov/industry-knowledge/discussions/3>

> **Review handoff — accessibility fixes pushed**
> Mobile overlap fix is in. QA also flagged low CTA contrast
> (failed WCAG AA 4.5:1) and missing focus states on nav links —
> both fixed this afternoon. Card moved to Review. Final QA pass
> first thing tomorrow. — Rune (SM)

### 4. Sprint completion (Fri May 1)

**Posted:** <https://github.com/Runeov/industry-knowledge/discussions/4>

> **Sprint 1 complete — goal achieved**
> All 4 cards in Done. Final QA green across 320 / 375 / 768 /
> 1024+ for layout, contrast, focus, keyboard nav, and landmarks.
> CMS admin live under `/admin/`. Retro at 15:00; notes will be in
> `docs/meeting-notes/sprint-1-retrospective.md`. — Rune (SM)

### 5. Retro summary (Fri May 1, after retro)

**Posted:** <https://github.com/Runeov/industry-knowledge/discussions/5>

> **Retro summary — Sprint 1**
> Top takeaways: same-day blocker rule worked; we underestimated
> CSS responsiveness and caught accessibility late. Sprint 2: bring
> QA in earlier, run an accessibility pass before "Review", keep
> commitment small. Full notes:
> `docs/meeting-notes/sprint-1-retrospective.md`. — Rune (SM)
