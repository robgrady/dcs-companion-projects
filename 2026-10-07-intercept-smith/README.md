# Intercept Smith

Intercept Smith is a self-contained offline DCS Mission Editor build desk for creating a simple, testable alert-intercept scenario. It turns a protected point, intruder route, alert-base position, speeds, detection range, response delay, and desired intercept standoff into a geometry plot, timing gate, explicit trigger recipe, and four-run verification card.

## Use

1. Open `index.html` directly in a browser. No server, account, network connection, package install, or build step is required.
2. Name the mission, terrain, intruder group, and alert group. The generated recipe uses those group labels literally.
3. Enter all positions as true bearing and nautical-mile range from the protected point. Set speeds as planned ground speeds.
4. Enter the geometric detection radius, activation delay, desired intercept standoff, protected-zone radius, and timing reserve.
5. Review the plotted geometry and timing margin. A positive margin means the entered transit speed reaches the planned intercept point before the intruder, after subtracting both delay and reserve.
6. Build the seven-step Mission Editor recipe, then fly all four tests. Test evidence and the current contract persist in browser `localStorage`.
7. Copy the build brief or positions, print the sheet, or export/import JSON for backup and handoff.

## Important assumptions

- The timing model is deliberately transparent and two-dimensional. It assumes straight-line ground tracks and constant entered ground speeds; it does not model climb, acceleration, turn radius, fuel, sensor performance, weapons, ROE, terrain masking, or DCS AI decision-making.
- The planned intercept point lies on the radial between the intruder start and the protected point. Interceptor transit distance is the straight-line distance from the entered alert-base position to that point.
- Detection is represented as a circular trigger zone centered on the protected point. If the mission is intended to model radar or visual detection, add that uncertainty deliberately rather than treating this geometric zone as a sensor simulation.
- Distances shown for DCS trigger zones are converted with 1 nautical mile = 1,852 meters.
- Trigger labels, flag numbers, success criteria, tasks, waypoint actions, altitude, fuel, and combat behavior must be checked in the current DCS build. Intercept Smith is a build-and-test aid, not an assurance that the AI will execute a tactically correct intercept.
- Group names should be unique. The recipe uses flags 101 and 102 as a suggested local convention; change them if the mission already uses those flags.

## Community signal — accessed 2026-10-07

The project responds to a current mix of beginner demand and long-running Mission Editor friction:

- An October 7, 2026 r/dcsworld post asks for help creating a cinematic intercept mission and says the author has difficulty turning the idea into Mission Editor logic: https://www.reddit.com/r/dcsworld/comments/1wzoptv/help_with_mission_editor/
- The October 7, 2026 r/hoggit weekly questions thread continues to collect Mission Editor and DCS setup questions in a high-traffic support format: https://www.reddit.com/r/hoggit/comments/1wzqrr8/weekly_questions_thread_oct_07/
- A recent r/hoggit discussion describes the editor as powerful but fickle and highlights the continuing interest in tools that reduce scenario-authoring effort: https://www.reddit.com/r/hoggit/comments/1wy9b0r/i_made_an_ai_powered_dcs_mission_generator_that/
- Eagle Dynamics' current 2.9.21.11560 changelog includes Mission Editor and AI behavior fixes, including an AI runway-lineup change. That reinforces the need to test behavior in the installed build rather than assume a recipe is stable forever: https://www.digitalcombatsimulator.com/en/news/changelog/stable/2.9.21.11560/
- Eagle Dynamics' public roadmap discussion also records continuing work on Mission Editor features and trigger functionality: https://forum.dcs.world/topic/237078-dcs-roadmap-unofficial-no-discussion-here/page/15/

Those signals favor a narrow scenario smith rather than another general-purpose mission planner: the app makes one common first scenario—detect, launch, intercept, resolve—concrete enough to build and test without pretending to replace the Mission Editor.

## Design notes

**Surface:** Configure is primary; Inspect is secondary. The left column defines the scenario contract, the central work area exposes geometry and trigger construction, and the right column holds validation and proof. There is no marketing hero or equal-weight feature grid.

**Slop diagnostic before repair:** 1/10. The first composition used system-ui as an unchosen fallback, firing the default-type tell. No compositional tells fired.

**Repair and final score:** 0/10. Typography was made deliberate with locally available Avenir Next for operational controls, Iowan Old Style reserved for future editorial use, and SF Mono for bearings, timing, flags, and coordinates. No tech gradient, generic indigo, feature-tile grid, accent rail, glass blur, monument stat, icon topper, center stack, default Inter/system-only typography, or wrong-surface composition remains.

The visual system uses a restrained field-desk neutral palette, one brass command accent, and distinct but muted friendly/hostile route colors. Motion is limited to the copy-status toast and is removed under `prefers-reduced-motion`.
