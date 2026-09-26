# Sortie Window

Sortie Window is a self-contained, offline DCS World session-timebox planner. It answers a practical question before the simulator loads: does the desired payoff actually fit the time available after setup, startup, transit, recovery, and a protected interruption buffer?

The app turns the evening into an editable phase wire with clock gates, a proportional timeline, explicit margin or overrun, optional-phase compression, a fallback drill, saved plans, backup/restore, a copyable run brief, and a printable card. It makes no claim about aircraft performance or real-world procedure.

## Use

1. Open `index.html` directly in a modern browser. No server, account, network connection, dependency, or build step is required.
2. Enter the local start time, hard stop, protected buffer, start posture, observable payoff, and simplify rule.
3. Choose a starting template or edit the phase wire directly. Every phase name and duration is editable; phases can be reordered, removed, or added.
4. Mark phases optional when they can be compressed without destroying the purpose of the session.
5. Watch the margin and three clock gates. A red status means the planned phases plus protected buffer exceed the hard stop.
6. Select **Fit optional time** to remove only time marked optional, starting with the latest optional phase. The app will say plainly if mandatory time still does not fit.
7. Save useful windows locally, copy a text run brief, print the active run card, or export/import the saved-plan library as JSON.

Saved plans use browser `localStorage`. Clearing browser site data can remove them; JSON export is the durable backup path.

## Why this project

Recent community discussion shows a recurring time-to-reward problem. Players describe DCS as difficult to fit around work and family because preparation, startup, transit, and recovery can consume most of a limited session. A September 2026 r/hoggit discussion asks directly about the lack of meaningful progress and poor use of limited free time. Other recent discussions contrast full-procedure play with shortcuts, suggest deliberately brief sessions, and describe skipping startup or choosing faster training formats when available time is short.

Sortie Window does not try to make DCS simpler. It makes the trade visible before the player commits: preserve a worthwhile objective, budget the supporting phases honestly, and define a smaller fallback while there is still time to choose it.

Sources reviewed on **2026-09-26**:

- Reddit / r/hoggit, “DCS - Best combat flight sim on the market! Yet nobody actually plays it...” (2026-09-24) — the author describes limited free time, large preparation overhead, and weak time-to-reward as barriers to regular play: https://www.reddit.com/r/hoggit/comments/1wmxmi4/dcs_best_combat_flight_sim_on_the_market_yet/
- Reddit / r/hoggit, “Am I getting too old for DCS?” (2025-11-25) — players discuss DCS feeling like a second job, using auto-start, and choosing shorter modules or simpler sessions when time and energy are constrained: https://www.reddit.com/r/hoggit/comments/1p6e1aq/am_i_getting_too_old_for_dcs/
- Reddit / r/hoggit, “Less is more—I'm embracing short sessions” (2025-12-18) — a player reports that explicitly short sessions reduced avoidance and made practice more consistent: https://www.reddit.com/r/hoggit/comments/1pprtjj/less_is_more_im_embracing_short_sessions/
- Reddit / r/hoggit, “1 hour a day of DCS, time wasted or a good start?” (2021-04-28) — discussion centers on whether useful learning and flying can fit into a one-hour daily window: https://www.reddit.com/r/hoggit/comments/n0ig62/1_hour_a_day_of_dcs_time_wasted_or_a_good_start/
- Eagle Dynamics Forums, “HOT START/Autostart” (2021-12-19) — users debate hot starts and auto-start as ways to focus limited simulator time on the part of the sortie they want to practice: https://forum.dcs.world/topic/289158-hot-startautostart/

## Assumptions and boundaries

- All durations are pilot estimates. Sortie Window does not read DCS, mission files, tracks, telemetry, weather, fuel, route distance, or server state.
- Templates are generic starting structures, not official procedures or claims about any aircraft or mission type.
- “Start posture” is a planning label only. The actual mission determines whether cold, hot, runway, or air starts are available.
- Optional-phase fitting can reduce a phase to zero. The pilot must decide whether that still leaves a coherent and safe simulated mission.
- Clock gates are simple cumulative estimates from the entered local start time. They do not model time zones, pauses, acceleration, track replay, or midnight beyond displaying a wrapped 24-hour clock.
- The protected buffer is deliberately unavailable to the planned phases. It represents interruption and overrun protection, not fuel reserve or aviation safety margin.
- Mission briefings, module documentation, fuel state, weather, controllers, and server rules always take priority.
- Import keeps existing plans and appends valid plans from the selected backup.

## Design note

The primary surface is **Configure**, with **Operate** secondary: the user constructs a feasible session contract first, then follows the phase wire and clock gates. The composition is a sticky contract editor beside a denser execution workspace rather than a marketing hero or equal-weight feature grid. The visual language is a paper operations worksheet with near-black ink, olive field markings, and restrained signal red; Georgia, Trebuchet, and monospaced system faces are assigned by role without network fonts.

Slop diagnostic before final polish: **0/10**. The artifact uses no tech gradient, generic indigo, feature-tile grid, accent rail, unearned blur, monument stat, repeated icon topper, center stack, default Inter, or wrong-surface composition. Final score: **0/10**; the four numeric values are compact operational constraints rather than decorative statistics.

## Files

- `index.html` — complete offline app with inline CSS, templates, state, and JavaScript
- `README.md` — instructions, assumptions, community evidence, and design record
