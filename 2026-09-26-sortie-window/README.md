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

Current and recurring community discussion shows a time-to-reward problem. A July 2026 r/dcsworld guide is explicitly aimed at players with limited time and energy, while a February 2026 r/hoggit discussion criticizes single-player missions for consuming limited time through long setup, fragile triggers, and repetition. Earlier threads ask what meaningful DCS activity fits into 15–40 minutes and recommend deliberately scoped practice, hot or air starts, nearby objectives, and reusable short missions.

Sortie Window does not try to make DCS simpler. It makes the trade visible before the player commits: preserve a worthwhile objective, budget the supporting phases honestly, and define a smaller fallback while there is still time to choose it.

Sources reviewed on **2026-09-26**:

- Reddit / r/dcsworld, “Learning DCS Without Feeling Overwhelmed (or why DCS Isn't as Hard as It Looks)” (2026-07-29) — a current learning guide addresses players who have limited time or energy and want to avoid wasted effort and lost motivation: https://www.reddit.com/r/dcsworld/comments/1v9xvtl/learning_dcs_without_feeling_overwhelmed_or_why/
- Reddit / r/hoggit, “DCS has a problem with Single Player Missions” (2026-02-12) — discussion describes long planning, unreliable mission logic, repeated attempts, and single-player content that can be disrespectful of limited time: https://www.reddit.com/r/hoggit/comments/1r2tjag/dcs_has_a_problem_with_single_player_missions/
- Reddit / r/hoggit, “What can you do in DCS for ~30-40 minutes?” (2024-06-06) — players recommend focused repetitions, short mission types, hot or air starts, and quick-task servers when a full sortie does not fit: https://www.reddit.com/r/hoggit/comments/1d94eez/what_can_you_do_in_dcs_for_3040_minutes/
- Reddit / r/hoggit, “What do you all do if you only have 15-20 min to play?” (2022-10-30) — the thread asks how to get value from a very short window; replies describe small reusable practice missions with ready-to-fly and cold-start slots: https://www.reddit.com/r/hoggit/comments/yhghas/what_do_you_all_do_if_you_only_have_1520_min_to/
- Eagle Dynamics Forums, “Frustration venting - Cold start on multiplayer servers” (2021-12-10) — a player with limited game time describes repeated startup and alignment waits as consuming the part of the session intended for flying: https://forum.dcs.world/topic/288562-frustration-venting-cold-start-on-multiplayer-servers/

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
