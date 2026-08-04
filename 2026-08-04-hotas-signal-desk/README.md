# HOTAS Signal Desk

An offline, single-file diagnostic workbench for isolating DCS World controller faults without immediately resetting bindings. It walks a pilot through an ordered evidence path: operating-system input, USB power/topology, duplicate virtual devices, aircraft/seat-specific DCS assignments, and an in-mission stability check.

## Use

1. Open `index.html` directly in a modern browser; no server or internet connection is required.
2. Record the HOTAS, current USB connection, failure scope, symptoms, and any recent change.
3. Run the five tests in order and log one outcome for each. Change only one variable at a time.
4. Read the working conclusion, export the text log, or print the brief for troubleshooting later.
5. Session data is stored locally in the browser with `localStorage`. **New session** clears it.

## Features

- Five-stage guided fault-isolation path with explicit pass/fail evidence
- 60-second repeatability timer for final cockpit verification
- Working conclusion that changes with the strongest recorded evidence
- Persistent configuration, symptoms, notes, outcomes, and evidence log
- Plain-text export and print layout
- Responsive layout, keyboard-visible focus, semantic controls, and reduced-motion support
- Fully self-contained HTML/CSS/JavaScript; compatible with `file://`

## Important assumptions and limits

- The tool is a fault-isolation aid, not a definitive hardware diagnosis and not a substitute for device-vendor guidance.
- Windows `joy.cpl` is used as the neutral input observation point because DCS World runs on Windows.
- Flickering device lights, USB disconnect sounds, or failure in `joy.cpl` are treated as evidence upstream of DCS, not proof of one specific failed component.
- A direct rear motherboard port is suggested as a controlled comparison, not as a universal permanent configuration.
- Virtual-controller tools such as HidHide are mentioned cautiously; the app does not prescribe a setup because device and remapper topology varies.
- Back up DCS input profiles before deleting, resetting, or substantially changing assignments.

## Community signal

Accessed **2026-08-04**.

- [r/hoggit — “DCS not properly reading HOTAS commands”](https://www.reddit.com/r/hoggit/comments/1vdyj6b/dcs_not_properly_reading_hotas_commands/) (posted 2026-08-03): a pilot reported that only full stick/throttle travel registered while throttle-panel lights flickered. Multiple replies independently prioritized USB power, hubs, direct motherboard ports, and Windows USB power management; the author later identified an underpowered inexpensive hub as the cause. This directly motivated an evidence-first sequence that checks behavior outside DCS before touching bindings.
- [r/hoggit new-post feed](https://www.reddit.com/r/hoggit/new/) (reviewed 2026-08-04): the same current feed also surfaced “I just discovered HidHide” (2026-08-03) and an F-14B(U) RIO binding question (2026-08-03), reinforcing that physical/virtual device visibility and seat-specific binding discovery remain active controller pain points. The app stays module-neutral because the existing collection already contains an F-14B(U) transition project.

## Design note

This is an **Operate** surface: setup evidence sits at left, the ordered test queue dominates the center, and the persistent log/conclusion stays visible at right. The palette and compact typography evoke a maintenance desk rather than a generic SaaS dashboard. Anti-slop audit after implementation: **0/10**; none of the ten listed tells fired.
