# Sprint 1 — Manual QA Checklist

- **Author:** Member C (QA, simulated)
- **Date:** Tue Apr 28, 2026
- **Sprint:** Sprint 1 (Mon Apr 27 → Fri May 1, 2026)
- **Repository:** <https://github.com/Runeov/industry-knowledge>

> Member C is a simulated team member for this practice run. The
> checklist itself is real and was used to drive the manual QA pass
> against the Sprint 1 deliverable. See [`team.md`](../team.md) and
> [`evidence-index.md`](../evidence-index.md) for context.

## Scope

This checklist covers the Sprint 1 deliverable:

- The public **one-page site** with three sections — **hero**,
  **about**, **contact** — served from the repository root.
- The **Netlify CMS admin** relocated under `/admin/`, reachable
  from the public site footer.

Out of scope for Sprint 1: real form submission, server-side
integration, multi-page navigation, content authoring workflows
beyond a single editor opening `/admin/`.

## Test environment

- **Browser:** desktop Chromium-based browser (Chrome / Edge),
  most recent stable channel.
- **Keyboard-only mode:** all interactive elements verified using
  Tab / Shift+Tab / Enter / Space, with the mouse left untouched.
- **Viewport widths to verify:** **320 / 375 / 768 / 1024+** px
  (small phone, common phone, tablet, desktop). Use the browser
  devtools responsive mode to switch between widths.
- **Reduced motion:** OS-level "Reduce motion" toggle on for at
  least one pass through the page.

## Layout integrity

- [ ] Hero section renders with heading, tagline, intro paragraph,
      and a single primary CTA button.
- [ ] About section renders with heading and at least one paragraph
      of intro copy.
- [ ] Contact section renders with heading, intro paragraph, and
      the contact form.
- [ ] No overlapping elements at any of the four target widths.
- [ ] No horizontal scrollbars at any of the four target widths.
- [ ] Footer is visible and contains a copyright line and links.

## Navigation links

- [ ] Brand link in the header returns to `#home`.
- [ ] Header nav has links to **Home**, **About**, and **Contact**.
- [ ] Each nav link scrolls to the correct in-page section.
- [ ] Footer link to `admin/` opens the CMS admin shell.
- [ ] Footer link to the GitHub repository opens the right URL in
      a new tab / safely (with `rel="noopener"`).

## In-page anchor scroll

- [ ] Clicking a nav link smoothly scrolls to the matching section
      (or jumps instantly under reduced-motion).
- [ ] After the scroll, keyboard focus is moved to the target
      section so subsequent Tab presses continue from there.
- [ ] On mobile, clicking a nav link also closes the mobile nav
      panel.

## Contact form

- [ ] Every input has a visible, programmatically associated label.
- [ ] Name, email, and message fields are marked `required`.
- [ ] Email field uses `type="email"` so mobile keyboards adapt.
- [ ] Tab order is: Name → Email → Message → Send.
- [ ] Submit button is reachable by keyboard and shows a clear
      focus state.
- [ ] The "demo only" note is present and visually distinct.

## Responsiveness

- [ ] Layout is intact at **320 px** width with no overflow.
- [ ] Layout is intact at **375 px** width.
- [ ] Layout is intact at **768 px** width with the desktop nav
      visible and the mobile toggle hidden.
- [ ] Layout is intact at **1024+ px** width with comfortable
      content padding.

## Contrast (WCAG AA)

- [ ] Primary CTA button text vs background passes WCAG AA
      (>= 4.5:1 for normal text).
- [ ] Body text vs page background passes WCAG AA.
- [ ] Form field text vs background passes WCAG AA.

## Visible focus states

- [ ] Header brand link shows a visible focus ring.
- [ ] Each header nav link shows a visible focus ring.
- [ ] CTA button shows a visible focus ring.
- [ ] Each form field shows a visible focus state.
- [ ] Submit button shows a visible focus ring.
- [ ] Footer links show a visible focus ring.
- [ ] Skip link becomes visible on first Tab press.

## Semantic landmarks

- [ ] Page has exactly one `<header>` landmark.
- [ ] Page has exactly one `<main>` landmark.
- [ ] Page has exactly one `<footer>` landmark.
- [ ] Primary nav uses a `<nav>` element with an accessible name.
- [ ] Each section uses `<section>` with a heading that describes
      it (`aria-labelledby`).

## Skip-to-content link

- [ ] First Tab press on a fresh page focuses the **Skip to main
      content** link.
- [ ] Activating it moves focus to the `#home` section.

## Mobile nav toggle

- [ ] Toggle button is visible at < 768 px and hidden at >= 768 px.
- [ ] Toggle has `aria-controls="primary-nav"`.
- [ ] Toggle's `aria-expanded` flips between `false` and `true`
      on activation.
- [ ] When open, the nav panel is reachable by keyboard.
- [ ] Selecting a nav link from the open panel closes the panel.

## Reduced motion

- [ ] With "reduce motion" enabled, in-page anchor scrolling is
      instant rather than animated.
- [ ] No essential information is conveyed via animation only.

## CMS admin

- [ ] `/admin/` loads the Netlify CMS shell without console errors.
- [ ] The admin page is reachable from the footer link on the
      public site.
- [ ] The original root-level `config.yml` is no longer used; the
      admin reads `admin/config.yml`.

## Regression notes

This checklist is the **baseline** for Sprint 1. It was first run
on Tue Apr 28 against the in-progress site, then re-run as a full
pass on Fri May 1 after each blocker fix landed. Any failure
discovered during the sprint is logged in the QA report
([`sprint-1-report.md`](sprint-1-report.md)) with a defect ID, an
owner, and a retest result. The checklist will be re-run in full
after any blocker fix and again before the sprint demo.

## Sign-off

- **QA name:** ___________________________
- **Date:** _______________________________
- **All items pass:** [ ] yes  [ ] no (see report)
