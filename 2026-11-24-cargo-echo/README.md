# Cargo Echo

Cargo Echo is a self-contained, offline evidence desk for DCS World logistics incidents. It helps a mission builder or multiplayer crew record what each observer sees at the same cargo transition, identify the first useful divergence, and produce a concise reproduction packet without uploading mission data.

## Use

1. Open `index.html` directly in a browser; no server or build step is required.
2. Record mission, map, server/host, DCS build, and test date.
3. Add each cargo object by its exact Mission Editor name and state the expected behavior.
4. Start at **Baseline spawn**, then log host, pilot, client, ground-observer, or replay evidence at attach, lift, transit, release, and post-drop transitions.
5. Keep paired observations within the same clock minute. Cargo Echo distinguishes observer splits, placement/geometry evidence, shared state loss, partial evidence, and coherent runs.
6. Mark the controlled proof gates, change only one variable on each retry, then copy, print, or export the resulting packet.

All working data is stored in browser `localStorage`. JSON export/import provides backup and handoff. The **Load demonstration** command is optional and explicitly replaces the current local incident after confirmation.

## Important assumptions

- Cargo Echo records observations and performs pattern-based triage; it does not inspect a `.miz`, connect to DCS, or establish the simulator's root cause.
- An observer split is evidence that viewpoints disagree, not proof of a specific network, script, or engine defect.
- Clock-minute grouping is intentionally simple so crews can coordinate without telemetry. More exact timestamps remain visible in the observation wire.
- Object names, locations, build numbers, masses, and expected behavior are user-entered because they vary by mission and module.
- The app makes no claim that every cargo path or module shares the same behavior.

## Community signal

Built on 2026-11-24 after reviewing current DCS community discussions and official update notes:

- A recent r/hoggit discussion described recurring logistics and cargo pain including cargo disappearing, desynchronizing between users, or spawning in/under geometry. The thread also showed players compensating for missing or unreliable campaign/logistics behavior with their own mission tooling. Accessed 2026-11-24: https://www.reddit.com/r/hoggit/comments/1xsmnrp/dcs_has_a_structural_dependency_issue/
- A recent r/dcsworld Mission Editor question showed how hidden task state can make observed behavior differ from the designer's intent, reinforcing the value of recording the first transition where expected and observed states separate. Accessed 2026-11-24: https://www.reddit.com/r/dcsworld/comments/1y2gjet/ai_planes_disobeying_my_direct_orders/
- Eagle Dynamics' 2026 release changelog shows active changes around cargo-adjacent systems, including trailer attach/detach tasks, mission-state saving, dynamic spawn, and airfield ground behavior. Accessed 2026-11-24: https://www.digitalcombatsimulator.com/en/news/changelog/release/

## Files

- `index.html` — complete app with inline CSS and JavaScript
- `README.md` — usage, assumptions, and source context
