# Trim Cycle

Trim Cycle is a self-contained, offline DCS World AH-64D force-trim rehearsal tool. It isolates the control-order problem that often gets buried inside hover practice: establish the new control position, hold force trim, release it without drifting, and—when the selected behavior requires it—return the physical controls through a configurable center gate.

## Use

1. Open `index.html` directly in a current browser. No server, internet connection, package install, or build step is required.
2. Match **Rehearsal behavior** to the control-return behavior you want to practice:
   - **Center-return gate** grades the release and then requires cyclic and pedals to return inside the configured center tolerance before time expires.
   - **Immediate trim** grades the trim release without a return gate.
3. Choose guided prompts or a check ride, set the center tolerance and return time, and select one of the four maneuver cues.
4. Start the exercise. Use arrow keys or the on-screen pad for cyclic, `J` / `L` for pedals, and hold `Space` or the force-trim button.
5. Complete the full cycle. Trim Cycle records position accuracy, sequence faults, return time, duration, and pass/review status.
6. Review recent cycles, export the local log as CSV, or print the debrief wire.

Settings and up to 30 recent cycles persist in browser `localStorage`.

## Important assumptions

- This is a procedural rehearsal, not a simulation of the AH-64D flight model, SCAS, aerodynamics, control loading, or a specific joystick mechanism.
- The four target positions are invented practice cues. They are not real aircraft control values and should not be used as performance guidance.
- “Center-return gate” and “Immediate trim” describe this trainer's two rehearsal behaviors; users must match them to their own DCS Special Options, hardware, and current module behavior.
- A pass means only that the page's interaction sequence, accuracy threshold, and configured timing gate were met.
- Verify actual controls, trim options, and procedures in the current DCS AH-64D, its official documentation, and a safe simulation mission.
- The app is simulation-only and never connects to DCS or reads a physical controller.

## Community signal

Built on **2026-11-26** after reviewing current official development signals and repeated community discussion about AH-64D handling changes and force-trim technique:

- Eagle Dynamics' 2026 roadmap identifies a new AH-64D flight model and SCAS-related work as planned development. That makes control-technique rehearsal timely while also making a version-independent procedural tool safer than hard-coding aerodynamic claims. Accessed 2026-11-26: https://www.digitalcombatsimulator.com/en/news/2025-12-26/
- The r/dcsworld discussion **“My expectations for the new AH-64 FM”** centers on hover behavior, control responsiveness, and the practical difficulty of handling the helicopter with desktop controls. Accessed 2026-11-26: https://www.reddit.com/r/dcsworld/comments/1ptj7tk/my_expectations_for_the_new_ah64_fm/
- The r/hoggit discussion **“DCS AH-64D new flight model unofficial leaked”** shows strong current attention to the module's handling revision and specifically discusses hover feel, force trim, SCAS, and joystick setup. Accessed 2026-11-26: https://www.reddit.com/r/hoggit/comments/1z7ul5v/dcs_ah64d_new_flight_model_unofficial_leaked/
- The Eagle Dynamics forum thread **“AH-64 Flight Model”** contains recurring reports and advice about hover stability, trim technique, controller centering, and the relationship between hardware and Special Options. Accessed 2026-11-26: https://forum.dcs.world/topic/385512-ah64-flight-model/

Community statements are demand signals, not technical authority. Trim Cycle deliberately trains sequence and evidence rather than claiming to reproduce the current or forthcoming flight model.

## Design notes

**Surface:** Operate is primary; Learn is secondary. The central control scope, force-trim action, explicit phase strip, and return gate dominate the composition. Setup and debrief remain narrow supporting rails; there is no marketing hero or equal-weight feature grid.

**System:** near-black instrument surfaces, amber control emphasis, mint target/evidence color, restrained red faults, Avenir/system humanist body type, and monospaced instrumentation. Motion is limited to control position and state feedback, with `prefers-reduced-motion` support.

**Anti-slop audit before repair: 0/10.** None of the ten tells fired: no tech gradient, generic indigo accent, feature-tile grid, accent rail, decorative blur, monument statistic, icon toppers, center stack, default Inter typography, or wrong-surface composition.

**Anti-slop audit after verification: 0/10.** The desktop and responsive layouts remain action-first, with all decoration subordinate to the trim cycle.

## Files

- `index.html` — complete offline app with inline CSS and JavaScript
- `README.md` — usage, assumptions, community sources, and design audit
