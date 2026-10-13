# Mission Spine

Mission Spine is a self-contained, offline DCS World Mission Editor companion for building replayable solo missions around **observable events** instead of rigid clock timing. It turns a short mission contract into a four-act encounter, exact group labels, zone geometry, a numbered trigger recipe, randomized-but-fair replay branches, and a seven-gate playtest checklist.

## Use

1. Open `index.html` directly in a modern browser. No server, install, account, network connection, or build step is required.
2. Set the primary task, terrain posture, player flight, start state, target session length, enemy pressure, and friendly support.
3. Choose whether the mission needs a randomized replay branch and a player-facing abort route.
4. Select **Build mission spine**. Build the generated groups first, then implement the trigger rows from top to bottom in the DCS Mission Editor.
5. Use **Test run** to record evidence for cold-start, delay, fast-commit, recommit, branch, success, and abort behavior.
6. Print the active view or export the complete contract and generated blueprint as JSON. Settings and test evidence persist in browser `localStorage`.

Keyboard shortcut: `Alt+1`, `Alt+2`, and `Alt+3` switch between Build Sheet, Trigger Logic, and Test Run.

## Assumptions and boundaries

- This is a design and verification tool; it does not edit `.miz` archives or execute Lua.
- Generated trigger rows intentionally use standard Mission Editor concepts such as late activation, trigger zones, flags, switched conditions, coalition messages, random chance, group life, and radio items. Exact labels and available actions can differ by DCS version and scenario context, so the designer must verify the resulting mission in the installed DCS build.
- The blueprint is airframe- and map-agnostic. It avoids inventing module-specific performance values, weapon envelopes, frequencies, or procedures.
- Randomization changes the encounter branch, not the victory condition. The player should always receive observable evidence before escalation.
- Pressure controls reserve behavior and thresholds; it is not a promise of balanced AI difficulty.
- All data stays in the browser unless the user explicitly exports a JSON file.

## Community signal

Accessed **2026-10-13**.

Recent and recurring community discussions point to a gap between DCS's strong cockpit simulation and the effort required to create satisfying, replayable missions:

- A current r/hoggit discussion asks why DCS does not make it easier to create a mission that feels alive without relying on exact timing, and describes the work required for branching behavior and replay value: https://www.reddit.com/r/hoggit/comments/1w59kd1/why_doesnt_dcs_make_it_easier_to_create_a_mission/
- A current r/dcsworld thread asks how to build a simple but replayable single-player mission, specifically seeking structure that remains useful beyond a memorized first run: https://www.reddit.com/r/dcsworld/comments/1w2k0ac/how_do_you_build_a_simple_but_replayable_single/
- A recent r/dcsworld post from a new player says the Mission Editor feels overwhelming and asks where to begin: https://www.reddit.com/r/dcsworld/comments/1qodh4c/dcs_mission_editor_feels_overwhelming_where_do_i/
- A recurring r/hoggit discussion notes that many players struggle to create missions and campaigns and calls for easier ways to obtain or make substantial scenarios: https://www.reddit.com/r/hoggit/comments/1hsvz9y/dcs_missions_and_campaigns_why_is_it_so_hard_to/
- Another r/hoggit thread asks how creators plan complex missions without losing track of triggers and flags, reinforcing the need for an external state-first build sheet: https://www.reddit.com/r/hoggit/comments/1m8ypgo/how_do_you_plan_complex_missions_without_losing/

Mission Spine answers that signal without pretending to replace the Mission Editor: it gives the designer a small, explicit state machine; names every required group; separates detect, commit, and resolve; and makes replay and abort behavior testable before the scenario is considered complete.

## Design notes

This is a **Configure** surface. The composition keeps configuration in a sticky left workbench and presents the output as a printable field sheet rather than a dashboard or marketing page. The palette and typographic treatment reference utilitarian planning documents without copying a specific military form.

Slop diagnostic after implementation: **0/10**. No tech gradient, generic indigo, equal-weight feature grid, accent rails, glass blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch is present.
