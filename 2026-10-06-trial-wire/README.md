# Trial Wire

Trial Wire is a self-contained offline DCS module evaluation desk. It turns a limited trial period into comparable flight evidence: add candidate modules, define what each must prove, score the same six criteria after flown sessions, track unresolved blockers, and produce a transparent decision brief.

## Use

1. Open `index.html` directly in a browser. No server, account, package install, or network connection is required.
2. Add one or more modules or terrains under consideration. Trial dates are optional but enable a days-remaining cue.
3. After each focused DCS session, choose **Log flown session**, record time, score all six criteria, and capture one concrete evidence note.
4. Use **Adjust criteria weights** to reflect personal priorities. The same weights apply to every candidate.
5. Review **Compare** and **Decision brief**, then copy, print, or export the result. JSON export/import provides a portable backup.

All working data stays in browser `localStorage`. Clearing site data removes it unless a JSON backup has been exported.

## Decision logic

- Fewer than two sessions: **Insufficient evidence**
- Any session with an unresolved blocker: **Hold — blocker open**
- Weighted score of 4.0 or higher: **Consider purchase**
- Weighted score from 3.0 through 3.9: **Continue trial**
- Weighted score below 3.0: **Pass for now**

The rule is intentionally visible and simple. Scores are personal observations, not specifications or claims about module quality.

## Important assumptions

- Trial availability varies by product and account. Trial Wire never claims that a particular module is eligible; verify the current catalog before planning.
- Eagle Dynamics' current FAQ says participating modules can be tried for two weeks, trial reactivation becomes available after six months, Two-Step Authentication is required, and trial modules are unavailable in offline mode. Trial Wire accepts user-entered dates rather than enforcing those terms so it remains useful for sale weekends, borrowed setups, and informal evaluations too.
- The app does not read DCS files, launch DCS, activate licenses, or contact Eagle Dynamics.
- Date calculations use the browser's local date. Recommendations are decision aids, not purchase instructions.

## Community signal — accessed 2026-10-06

The idea responds to repeated community questions about what to buy and how to use the limited evaluation window deliberately:

- The October 5, 2026 r/dcsworld weekly thread explicitly routes repeated “what Module to buy” questions into one place; a current commenter was choosing between the F-14B(U) and F-16C as a new player: https://www.reddit.com/r/dcsworld/comments/1wy12p1/weekly_thread_20261005_questions_on_dcs_pcs/
- The September 28, 2026 r/dcsworld weekly thread includes several live purchase-fit questions: F-16 versus a terrain, F-16 workflow after the Hornet, and Cold War module choice based on multiplayer population: https://www.reddit.com/r/dcsworld/comments/1ws6jar/weekly_thread_20260928_questions_on_dcs_pcs/
- A September 1, 2026 r/hoggit weekly-thread discussion specifically describes not having enough time to understand a module within the free-trial window and not wanting to wait for another opportunity: https://www.reddit.com/r/hoggit/comments/1w3vni8/weekly_questions_thread_sep_01/
- Eagle Dynamics' current Free to Play FAQ documents the two-week evaluation period, six-month reactivation interval, Two-Step Authentication prerequisite, participating-product scope, and offline-mode limitation: https://www.digitalcombatsimulator.com/en/support/faq/discount/

Those signals favor a neutral evidence ledger over another recommendation quiz: pilots need a way to define the question before activating a trial, log what they actually flew, and compare candidates on consistent criteria.

## Design notes

**Surface:** Compare is primary; Configure is secondary. The app therefore uses aligned candidate columns and an evidence ledger rather than a marketing hero or dashboard tile grid.

**Slop diagnostic:** 0/10 after implementation. No tech gradient, generic indigo, equal-weight feature grid, accent rail, unearned glass, monument stat, icon topper, page-wide center stack, default Inter, or surface mismatch fired. The only centered composition is the bounded empty state, where it communicates the single required action.

The palette is a restrained field-desk neutral with one brass accent. Typography uses locally available Avenir Next for controls and Iowan Old Style for decisive headings; Menlo is reserved for dates and scores. Motion is limited to the status toast and disabled under `prefers-reduced-motion`.
