# Formation Forge

Formation Forge is a self-contained, offline geometry desk for building and checking formations made from multiple DCS AI groups. It generates course-relative placement plans for up to 16 group leaders, previews the package in plan view, calculates map X/Z anchors when a lead coordinate is available, checks nearest-neighbor spacing, and produces a Mission Editor build sheet.

Open `index.html` directly in a browser. It has no server, build step, package installation, external font, or network dependency.

## Use

1. Name the mission or package and select a pattern: box, line abreast, trail, echelon, vic, or bomber stream.
2. Set group count, lateral and trail spacing, altitude rule, minimum separation gate, package course, and speed.
3. Optionally enter the lead group's DCS map X/Z coordinates. The ledger will calculate each follower's approximate group-leader anchor in metres.
4. Click any plotted group or ledger row to inspect it. Type exact offsets or nudge it left, right, forward, aft, or vertically without disturbing the rest of the formation.
5. Resolve spacing warnings, transfer the group leaders to the Mission Editor, and close the three verification gates only after placement, route/action review, and an in-sim test.
6. Copy the build sheet, print the board, export CSV for a spreadsheet, or export/import the full plan as JSON. Working state is saved automatically in `localStorage`.

## Important assumptions

- Formation Forge positions **group leaders**. It does not set the formation of aircraft inside a DCS group, modify a `.miz` file, run a script in DCS, or control AI behavior.
- Right/left and ahead/trail offsets are relative to the package's true course. Positive right is starboard of course; positive ahead is forward along course.
- One nautical mile is treated as exactly 1,852 metres. Feet are used for the planning display; the CSV and build sheet retain feet for altitude because this is the value the mission maker selected.
- Calculated X/Z values use a flat local rotation around the entered lead point. They are intended as placement anchors or scripting references, not a geodetic conversion and not a substitute for checking the actual map.
- The spacing gate compares horizontal distance between group leaders. It does not model aircraft wingspan, intra-group dimensions, wake, turn geometry, vertical clearance, collision avoidance, or terrain.
- Built-in patterns are starting geometry. DCS waypoint actions, tasking, route turns, speed, altitude, skill, aircraft type, and the current AI build can all change what happens after mission start.
- Every formation should be tested through spawn, join-up, turns, leader loss, and the intended attack or recovery sequence in the target DCS version.

## Why this project now

Sources reviewed on **2026-10-02**:

- A recent r/dcsworld mission-editor help thread described rebuilding a large WWII bomber scenario with roughly twelve four-aircraft groups, staggered altitudes, and formation settings, only to have the groups spawn in an unintended trail. The concrete pain point is coordinating many group leaders while AI formation behavior is difficult to diagnose: https://www.reddit.com/r/dcsworld/comments/1su2snp/help_with_mission_editor/
- Another April 2026 r/dcsworld thread asked how to create formations larger than four aircraft. The practical community answer was to use separate flights with common waypoints or `Follow` tasks, while warning that units placed too close can cause problems: https://www.reddit.com/r/dcsworld/comments/1sq2y78/how_can_i_add_more_than_4_wingmen/
- Eagle Dynamics' **DCS 2.9.30.28536** changelog dated **2026-09-30** says the `Change formation` command's strange AI behavior was fixed; the same update includes other AI takeoff, carrier-landing, crosswind, and formation-spacing fixes. That makes a repeatable before/after formation plan especially useful when retesting missions after the patch: https://www.digitalcombatsimulator.com/en/news/changelog/release/2.9.30.28536/
- An August 2026 r/dcsworld thread about mass-selecting airfields produced the recurring joke that simple or convenient Mission Editor operations are often unavailable, with users exchanging manual workarounds instead: https://www.reddit.com/r/dcsworld/comments/1vsz70d/dcs_mission_editor/
- A recent r/hoggit discussion tied mission-maker burnout to the time and micromanagement required to build scenarios, while also discussing formation-flying AI work: https://www.reddit.com/r/hoggit/comments/1pzqb99/in_anticipation_of_2026_and_beyond_lets_list_all/
- Eagle Dynamics' 2026 roadmap says AI improvements remain an active focus and explicitly advises users to watch update changelogs. Formation Forge therefore records a reproducible intended geometry without assuming today's AI result will remain fixed: https://www.digitalcombatsimulator.com/en/news/2026-01-09/

Formation Forge responds to that signal with a narrow job: make a multi-group formation explicit, editable, measurable, portable, and testable before the mission maker spends another cycle dragging groups by eye.

## Design and accessibility

This is a **Configure** surface: geometry inputs, plan view, placement ledger, selected-group inspector, validation, and test gates dominate. Controls use labels, visible focus states, keyboard-selectable plotted groups and rows, responsive layouts, 44-pixel-class targets, high-contrast status text, reduced-motion handling, and print styling.

Slop diagnostic: the initial completed artifact scored **0/10** and the final check remained **0/10**. No tech gradient, generic indigo accent, equal feature-tile grid, accent rail, unearned blur, monument stat, icon topper, center-stack composition, default Inter typography, or wrong-surface composition was present.
