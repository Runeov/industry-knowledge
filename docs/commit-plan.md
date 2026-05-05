# Sprint 1 — Simulated Commit Plan & Evidence

> Companion document to [`evidence-index.md`](evidence-index.md),
> [`team.md`](team.md), and the meeting notes under
> [`meeting-notes/`](meeting-notes/sprint-1-planning.md).

## Why a simulated history?

This repository is a **4-person practice run** for the Noroff
Industry Knowledge module. In reality, **Rune (`Runeov`) is the
only real student** and produced every line of code, every doc,
and every commit. **Member B** (Developer) and **Member C** (QA)
are simulated team members with placeholder emails on the
`@team-onepage.local` domain (`member-b@team-onepage.local`,
`member-c@team-onepage.local`).

Rather than hide that fact, the team chose to **structure the
git history role-by-role** so a marker can audit how the work
would have flowed in a real 4-person sprint:

- Rune commits planning, daily updates, retrospective, reflection,
  evidence index, and the README — i.e. the Scrum Master / process
  artefacts.
- Member B commits scaffolding, semantic markup, responsive CSS,
  CMS relocation, and the two accessibility / mobile fixes — i.e.
  the Developer artefacts.
- Member C commits the QA checklist on Tue and the QA report on
  Fri — i.e. the QA artefacts.

The simulation is stated explicitly in [`team.md`](team.md) and
[`evidence-index.md`](evidence-index.md), and again in the body
of every Member B / C commit (the `Role:` trailer carries
"(simulated)"). No claim is made that anyone other than Rune did
real work.

## Commit plan (12 commits)

All timestamps are ISO 8601 in **+07:00**. Author dates and
committer dates match.

| #  | Date (ISO 8601, +07:00)       | Author    | Type  | Subject |
|----|-------------------------------|-----------|-------|---------|
| 1  | 2026-04-27T09:30:00+07:00     | Rune      | docs  | add sprint planning notes and task assignments |
| 2  | 2026-04-27T14:00:00+07:00     | Member B  | feat  | scaffold one-page project structure |
| 3  | 2026-04-28T10:00:00+07:00     | Member B  | feat  | add semantic sections for hero, about, and contact |
| 4  | 2026-04-28T11:00:00+07:00     | Member C  | test  | add manual QA checklist for one-page site |
| 5  | 2026-04-28T16:00:00+07:00     | Member B  | style | implement mobile-first responsive layout |
| 6  | 2026-04-29T11:00:00+07:00     | Member B  | chore | relocate Netlify CMS admin under `/admin/` |
| 7  | 2026-04-30T09:30:00+07:00     | Member B  | fix   | resolve mobile button/text overlap at small breakpoints |
| 8  | 2026-04-30T14:00:00+07:00     | Member B  | fix   | improve focus states and button contrast for accessibility |
| 9  | 2026-05-01T12:00:00+07:00     | Member C  | docs  | add sprint QA report and retest notes |
| 10 | 2026-05-01T14:00:00+07:00     | Rune      | docs  | log daily updates and communications |
| 11 | 2026-05-01T16:00:00+07:00     | Rune      | docs  | add retrospective notes and action items |
| 12 | 2026-05-05T14:00:00+07:00     | Rune      | docs  | add reflection, evidence index, and project README |

Member B / C addresses are simulated:

- Member B (Developer, simulated): `member-b@team-onepage.local`
- Member C (QA, simulated): `member-c@team-onepage.local`

Rune's commits use whatever name and email are configured locally
on his Git client (i.e. the script does **not** override
`GIT_AUTHOR_NAME` / `GIT_AUTHOR_EMAIL` on Rune's commits — only
the dates are backdated).

## Mapping commits to marking-guide criteria

The wording of each criterion below is taken verbatim from
[`evidence-index.md`](evidence-index.md). Only the criteria that
the commit history can directly speak to are listed; criteria 1
and 4 are external by design (questionnaire, Onboarding session)
and criterion 2 is satisfied by the existence of the repo itself.

| Criterion | Exact wording | Commits that supply evidence |
|-----------|---------------|------------------------------|
| 5  | I have committed to a realistic number of tasks to be completed during each sprint. | **1** (planning notes list 4 cards for a 5-day sprint) |
| 6  | I have done my best to complete these tasks within the sprint period. | **2, 3, 5, 6, 7, 8, 10** (day-by-day Developer + Scrum Master output Mon–Fri) |
| 7  | I have submitted my finished work items for review. | **7, 8, 9** (fixes land Thu, QA retest report lands Fri — cards moved In Progress → Review → Done) |
| 9  | I have recorded important communications on the GitHub Team Discussion Boards. | **10** (daily-updates file contains the copy-ready Discussions snippets) |
| 10 | I have made my team aware of any obstacles or roadblocks. | **7, 9, 10** (mobile-overlap blocker reported Wed, fixed Thu, retested Fri; documented in daily updates and the QA report) |
| 12 | I have met with my team to reflect on the challenges and successes during the sprint. | **11** (retrospective notes — Fri May 1, 15:00) |

Reflection (criterion 11) and feedback to the class (criterion
13) are both delivered by **commit 12**, which adds
`docs/reflection.md`, `docs/evidence-index.md`, and the project
README in one final batch.

## Replay tooling

The 12 commits are re-played onto the repository by a single
PowerShell script:

- Script: [`../scripts/replay-sprint-commits.ps1`](../scripts/replay-sprint-commits.ps1)
- Snapshot data: [`../scripts/replay-data/`](../scripts/replay-data/)

The snapshot files are **intermediate states** of `css/styles.css`
and `index.html`, captured so the historical commits show
realistic, progressive diffs rather than every file landing fully
formed in one go:

- `index.stage-01-scaffold.html` — skeleton `index.html` for
  commit 2 (no skip-link, no form, sections empty).
- `styles.stage-01-scaffold.css` — basic resets only for commit 2.
- `styles.stage-02-responsive.css` — full mobile-first responsive
  layout for commit 5, but with a lower-contrast CTA token
  (`#5a8dee`) and **no** `:focus-visible` rules and **no**
  small-phone media query.
- `styles.stage-03-mobile-fix.css` — stage 2 + the
  `@media (max-width: 360px)` block that resolves D-01 (commit 7).
- The final `css/styles.css` (with the high-contrast CTA token,
  `:focus-visible`, and the `clamp()`-based heading scale) is
  stage 4 and lands in commit 8.

## Verification

After running the script, the new history can be verified with:

- `git log --pretty=format:'%h %an %ad %s' --date=iso8601`
  — should show **12 commits** in chronological order, with
  Rune / Member B / Member C alternating as designed.
- `git status` — should be **clean**. The working tree after
  commit 12 must equal the pre-replay state. The script itself
  performs a SHA-256 comparison between the saved final-state
  snapshot and the post-replay working tree, and refuses to exit
  successfully if any file differs.
- `git push origin main` (or `--force-with-lease` if the remote
  has been advanced) — once pushed, GitHub will display the
  dated commits in the **contributor timeline** and on the
  repository's **Insights → Contributors** view, attributing each
  commit to the correct simulated author.

## Rollback

The replay script creates a `backup-pre-replay-<UTC timestamp>`
branch at the current HEAD before doing anything destructive,
and saves a complete copy of the pre-replay working tree to
`$env:TEMP\industry-knowledge-replay-<timestamp>\final\`. To
roll back:

```powershell
git reset --hard backup-pre-replay-<UTC timestamp>
```

…and, if needed, restore any working-tree files from the temp
copy. The script does **not** auto-delete either artefact.
