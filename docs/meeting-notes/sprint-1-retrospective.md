# Sprint 1 — Retrospective

- **Date:** Fri May 1, 2026
- **Time:** 15:00 (~20 minutes)
- **Format:** Online retrospective
- **Attendees:** Rune (Scrum Master), Member B (Developer),
  Member C (QA), Member D (Designer)
- **Facilitator:** Rune

> Member B, C, and D are simulated for this 4-person practice run.
> See [team.md](../team.md).

## Sprint goal — outcome

> Deliver a responsive one-page site with hero, about, and contact
> sections, with QA-validated accessibility and responsiveness, and
> the Netlify CMS admin relocated under `/admin/`.

**Outcome: achieved.** All four Trello cards are in **Done**. Final
QA pass on Friday morning was green across 320 / 375 / 768 / 1024+
for layout, links, contrast, focus states, keyboard navigation, and
semantic landmarks. The Netlify CMS admin is reachable at `/admin/`.

## What went well

- The sprint goal was specific and testable, which made it easy to
  decide when a card was actually "Done".
- Keeping the commitment small (4 cards for a 5-day sprint with a
  small team) was realistic and left slack for the mid-sprint
  blocker.
- The **same-day blocker rule** worked. The mobile overlap was
  reported at the Wednesday check-in, logged on Trello and GitHub
  Discussions the same day, and resolved by Thursday afternoon
  without slipping the sprint goal.
- Cross-role collaboration on the blocker was good: Member D
  contributed a spacing / type-scale suggestion, Member C added
  320 / 375 / 768 / 1024 viewport checks to the QA checklist, and
  Member B applied the CSS fix.
- Trello columns (**To Do → In Progress → Review → Done**) gave a
  clean, shared view of state.

## What was challenging

- **CSS responsiveness was underestimated.** The CTA-overlapping-hero
  bug below ~360px wasn't caught until mid-sprint and forced
  reprioritisation of polish work.
- **Accessibility issues were found late.** The CTA contrast (failed
  WCAG AA 4.5:1) and missing nav focus states only surfaced on
  Thursday during QA, after the visible-layout fix. Fixing them was
  quick, but it created last-minute pressure on Thursday afternoon.
- The mid-sprint check-in worked, but a single 15-minute slot on
  Wednesday was tight for talking through the blocker properly.

## What we learned

- "Looks fine on my screen" is not enough — explicit viewport
  targets (320 / 375 / 768 / 1024) belong in the QA checklist from
  day one, not added reactively.
- Accessibility checks (contrast, focus state, keyboard navigation)
  should run **before** a card moves to **Review**, not after.
- Logging a blocker the same day on both Trello and GitHub
  Discussions made it visible to the whole team without a meeting,
  which kept momentum.
- A small, concrete sprint goal made trade-off decisions easy when
  the blocker hit.

## Action items for Sprint 2

- [ ] Add explicit **320 / 375 / 768 / 1024** viewport targets to
      the QA checklist template.
- [ ] Add a short **accessibility pass** (contrast, visible focus,
      keyboard nav, landmarks) as a required gate before any card
      moves to **Review**.
- [ ] Bring QA in earlier — Member C reviews the in-progress build
      from Day 2, not only after Development is mostly done.
- [ ] Keep the commitment small again next sprint (4–5 cards),
      especially while the team is still calibrating.
- [ ] Consider extending the mid-sprint check-in to 20 minutes if a
      live blocker discussion is needed.

## Feedback to the class group

- A small, **specific** sprint goal made every other decision
  easier — strongly recommend writing one before picking tasks.
- A **same-day blocker rule** (Trello card + Discussions post the
  day it appears) avoided "I'll mention it tomorrow" delays.
- Build the QA / accessibility checklist **before** development
  finishes; otherwise contrast and focus issues land in the last
  24 hours of the sprint.
- A simple **To Do → In Progress → Review → Done** board is enough
  for a small team — extra columns are not needed yet.

## Sign-off

Retrospective closed at ~15:20. A short summary message was posted
on GitHub Discussions (see the communication log in
[sprint-1-daily-updates.md](sprint-1-daily-updates.md#communication-log--github-discussions-snippets)).
