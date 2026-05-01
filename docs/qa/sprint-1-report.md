# Sprint 1 — QA Report & Retest

- **Author:** Member C (QA, simulated)
- **Date:** Fri May 1, 2026, 12:00
- **Sprint:** Sprint 1 (Mon Apr 27 → Fri May 1, 2026)
- **Repository:** <https://github.com/Runeov/industry-knowledge>
- **Companion document:** [`checklist.md`](checklist.md)

> Member C is a simulated team member for this practice run. The
> defects, retests, and sign-off below mirror the real QA pass that
> Rune ran against the deliverable while wearing the QA hat.

## Summary

The manual QA checklist (see [`checklist.md`](checklist.md)) was
run against the public one-page site and the `/admin/` CMS shell
across **Tue Apr 28 → Fri May 1**. Three defects surfaced
mid-sprint — one blocker (mobile layout overlap) and two majors
(CTA contrast, missing focus states). All three were fixed by the
Developer (Member B, simulated) on **Thu Apr 30** and **retested
green** the same afternoon. A final full pass was completed on
**Fri May 1 (morning)** with every checklist section green at all
four target viewport widths (320 / 375 / 768 / 1024+).

## Defects found and resolved

| ID | Title | Severity | Found | Owner | Resolution | Retest |
|----|-------|----------|-------|-------|------------|--------|
| D-01 | Mobile layout overlap | **Blocker** | Wed Apr 29 | Member B (Developer, simulated) | Spacing / type-scale fix in `css/styles.css` (small-breakpoint media query, then refactored to `clamp()` heading sizes). | **Pass** at 320 / 375 / 768 / 1024+ on Thu Apr 30 (afternoon) |
| D-02 | Primary CTA contrast below WCAG AA | Major | Thu Apr 30 (morning) | Member B (Developer, simulated) | `--cta-bg` token darkened from `#5a8dee` to `#1f3a5f` against `#ffffff`. New ratio ~9.7:1 (was < 4.5:1). | **Pass** on Thu Apr 30 (afternoon) |
| D-03 | Missing visible focus state on nav links | Major (a11y) | Thu Apr 30 (morning) | Member B (Developer, simulated) | Added an explicit `:focus-visible` outline rule (3px solid `--color-focus`) covering all interactive elements. | **Pass** on Thu Apr 30 (afternoon) |

### D-01 — Mobile layout overlap (blocker)

- **Found:** Wed Apr 29 during the mid-sprint check-in.
- **Symptom:** Below ~360 px viewport width, the hero "Get in
  touch" CTA button visually overlapped the hero tagline / intro
  text. Affected real-world devices in the smallest-phone bucket.
- **Owner:** Member B (Developer, simulated).
- **Resolution:** spacing tokens and a small-breakpoint media
  query were added; the heading scale at very small widths was
  reduced. The change later evolved into a `clamp()`-based
  heading scale that smoothly handles 320 → 1024+.
- **Retest:** Thu Apr 30 afternoon. Re-ran the **Layout
  integrity** and **Responsiveness** sections of the checklist at
  **320 / 375 / 768 / 1024+** in the responsive devtools view.
  All four widths passed. Card moved In Progress → Review → Done.

### D-02 — CTA contrast below WCAG AA (major)

- **Found:** Thu Apr 30 morning, during the contrast pass.
- **Symptom:** The provisional CTA colour (`#5a8dee` on white)
  measured below 4.5:1 contrast — failing WCAG AA for normal text.
- **Owner:** Member B (Developer, simulated).
- **Resolution:** the `--cta-bg` token was changed to a deep navy
  `#1f3a5f`. Verified ratio against white (`#ffffff`) at
  approximately **9.7:1** — comfortably AA and AAA for both
  normal and large text.
- **Retest:** Thu Apr 30 afternoon. Re-checked the CTA in both
  default and dark colour-scheme modes; the navy/white CTA stays
  AA in both.

### D-03 — Missing visible focus on nav links (major, a11y)

- **Found:** Thu Apr 30 morning, during the keyboard-only pass.
- **Symptom:** Tabbing through the header nav produced no visible
  focus ring, breaking the keyboard-only flow.
- **Owner:** Member B (Developer, simulated).
- **Resolution:** added a single global `:focus-visible` rule
  (3 px outline in the `--color-focus` high-vis amber, with
  offset and rounded corners) so every interactive element shows
  the same clear focus state. Skip-link focus rule already
  present.
- **Retest:** Thu Apr 30 afternoon. Tabbed through the entire
  page from the URL bar: skip-link → brand → nav links → CTA →
  form fields → submit → footer links. All elements showed a
  clearly perceivable focus ring.

## Final pass — Fri May 1

A complete re-run of the checklist on **Fri May 1, morning**:

- [x] Layout integrity — no overlap, no overflow, all sections
      render correctly.
- [x] Navigation links — header nav, brand, and footer links all
      navigate correctly.
- [x] In-page anchor scroll — smooth scroll under default
      preference, instant under reduced-motion.
- [x] Contact form — labels, required fields, tab order, focus
      states all good. (Submission is intentionally a no-op for
      Sprint 1.)
- [x] Responsiveness — clean at **320 / 375 / 768 / 1024+**.
- [x] Contrast — CTA ~9.7:1 against white; body text and form
      fields all pass AA.
- [x] Visible focus on every interactive element via
      `:focus-visible`.
- [x] Keyboard-only navigation works end-to-end without the
      mouse.
- [x] Semantic landmarks — single header, single main, single
      footer, named nav, sections labelled by their headings.
- [x] Skip-to-content link visible on first Tab and lands on the
      hero.
- [x] Mobile nav toggle — `aria-expanded` flips correctly,
      `aria-controls` points at the nav, opening/closing works,
      tapping a link closes the panel.
- [x] CMS admin reachable at `/admin/`, no console errors,
      footer link works.

## Recommendations for Sprint 2

- **Lock the viewport targets** (320 / 375 / 768 / 1024+) into
  the QA checklist template so every sprint tests the same set.
- **Require an accessibility pass before any card moves to
  Review.** Two of three defects this sprint were a11y issues
  caught late; bringing the a11y check forward will catch them
  on Tue / Wed instead of Thu morning.
- **Bring QA in earlier in the week.** The first full QA pass
  happened on Tue, but the responsiveness sweep was Wed; pulling
  the responsiveness sweep into Tue would have caught D-01 a day
  earlier.
- Add a lightweight automated contrast check (e.g. a Stylelint or
  axe-core run in CI) so D-02-style regressions are caught
  before manual QA.

## Sign-off

- **QA name:** ___________________________
- **Date:** Fri May 1, 2026
- **Sprint 1 deliverable accepted:** [x] yes  [ ] no
