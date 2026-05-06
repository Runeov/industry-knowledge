# Sprint 1 Reflection

```
GitHub Username: Runeov
Team Name: Team Onepage
Role: Scrum Master
```

Sprint 1 ran from Mon Apr 27 to Fri May 1, 2026, and my role was
Scrum Master for Team Onepage. Member B, C, and D were simulated for
this practice run, which meant I was effectively running the full
process myself; the goal was to demonstrate that I can plan,
facilitate, and document a sprint properly, not just write code. I
started the week by accepting the GitHub team invitation to
`Runeov/industry-knowledge` and confirming repository access, then
ran a short kickoff meeting at 09:00 on Monday to agree the sprint
goal, the four cards, and the working norms.

In planning I deliberately kept the scope small: a responsive
one-page site with hero, about, and contact sections, plus relocating
the Netlify CMS admin under `/admin/`. With four people and one week,
four cards (Design, Development, QA, Scrum Master facilitation) felt
honest. Each card had clear acceptance criteria — for example, the
Development card explicitly required the page to work at 320 / 375 /
768 / 1024+ widths — which made it much easier later to decide when
a card was actually "Done". Roles were split cleanly: Member D on
wireframe and visual direction, Member B on the build, Member C on
the QA checklist, and me on facilitation and the board.

Execution went mostly to plan until Wednesday. At the mid-sprint
check-in on Apr 29, Member B reported that the mobile layout broke
below about 360px — the CTA button was overlapping the hero text. I
treated this as a same-day blocker: I logged it on the Development
project-board card and posted a visibility note on GitHub Discussions that
afternoon, reprioritised polish work, asked Member D for a quick
spacing and type-scale suggestion, and asked Member C to add
explicit 320 / 375 / 768 / 1024 viewport checks to the QA checklist.
Member B applied the CSS fix on Thursday morning and QA re-verified
the same afternoon. On Thursday QA also flagged two accessibility
issues — the primary CTA failed WCAG AA contrast at 4.5:1, and the
nav links had no visible focus state — both of which were fixed by
Member B that afternoon and re-tested before the end of the day.

Communication was the part I worked hardest on. Day-to-day status
lived on the project board so that anyone could see card state at a glance, and
the more important moments — kickoff, the blocker, the review
handoff with the accessibility fixes, sprint completion, and the
retro summary — went on GitHub Discussions so they were recorded
permanently. Having a written same-day rule for blockers was the
single most useful agreement we made; it stopped the mobile overlap
from quietly slipping into Thursday and gave the rest of the team
visibility without needing another meeting.

The retrospective on Friday made the lessons clear. The same-day
blocker rule and the small, specific sprint goal both worked well.
What I underestimated was CSS responsiveness — narrow viewport
targets need to be in the QA checklist from day one, not bolted on
mid-sprint — and accessibility, which we currently catch only when
QA runs near the end. For Sprint 2 we agreed to add explicit
viewport targets to the QA template and to require a short
accessibility pass (contrast, focus, keyboard nav, landmarks)
before any card can move to **Review**, and to bring QA in earlier
in the week. The biggest thing I learned personally was how much of
"running a sprint" is just keeping communication honest and timely:
a clear goal, a visible board, written updates at the right
moments, and a rule for what to do the moment something goes wrong.
