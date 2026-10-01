# Launch Rail

Launch Rail is a self-contained, offline departure-sequencing workbench for DCS mission makers who need several AI groups to leave the same airfield without parking collisions, runway pileups, or ambiguous activation logic. It turns AI group setup into an explicit launch contract: start condition, parking ownership, release trigger, ready time, expected runway occupancy, minimum separation, and three test gates.

Open `index.html` directly in a browser. No server, build step, package installation, or network connection is required.

## Use

1. Set the airfield, active runway, mission start, minimum runway separation, and planning horizon.
2. Add every AI group that must depart during the opening window.
3. Record each group's ready time (`T+`), expected runway occupancy, start condition, parking slots, release trigger, route note, and whether the Mission Editor's runway-lineup option is being used.
4. Resolve red runway-separation and duplicate-parking warnings. Use **Compact schedule** to place groups at the selected minimum separation while preserving order.
5. Open each flight after testing the mission and close the parking/start, trigger/activation, and taxi/runway gates.
6. Copy the Mission Editor build sheet, print the rail, or export the plan as JSON. State is also saved automatically in the browser's `localStorage`.

## Important assumptions

- Launch Rail is a planning and test-record aid; it does not read or modify `.miz` files.
- Ready time is relative to mission start. Runway occupancy is a user-entered test estimate, not an aircraft performance calculation.
- A conflict is raised when the next group becomes ready before the prior group's occupancy plus the selected separation has elapsed.
- Parking slots are compared as literal comma-, semicolon-, or space-separated labels. The mission maker remains responsible for matching DCS's current slot numbering and checking large-aircraft clearance.
- The **AI runway lineup** field records intended use of the current Mission Editor option. Because AI behavior can vary by airfield, aircraft, route, and DCS build, the app deliberately requires an in-mission route test rather than treating the option as proof of a safe departure.
- The board is useful for single-player and multiplayer mission construction, but all affected client slots and activation paths should be tested in the target DCS version.

## Why this project now

Sources reviewed on **2026-10-01**:

- Eagle Dynamics' DCS 2.9.30.28536 changelog (2026-09-30) added an **“AI runway lineup”** option for AI groups and also listed a fix for runway collisions during AI takeoff. That creates a timely need for a small planning surface that helps mission makers decide where to apply the option and verify the whole departure sequence: https://www.digitalcombatsimulator.com/en/news/changelog/release/2.9.30.28536/
- The r/dcsworld changelog discussion repeated those AI departure changes, showing immediate community attention to the new option: https://www.reddit.com/r/dcsworld/comments/1wu630n/20260930_293028536_change_log/
- A recent r/dcsworld Mission Editor thread captured the recurring complaint that convenient bulk or workflow operations are often absent from the editor, with users sharing manual workarounds: https://www.reddit.com/r/dcsworld/comments/1vsz70d/dcs_mission_editor/
- A recent r/dcsworld AI discussion emphasized that dependable scenarios still require scripting, Mission Editor knowledge, and awareness of AI quirks: https://www.reddit.com/r/dcsworld/comments/1vfy7t7/does_dcs_have_good_ai/
- A broader r/hoggit discussion described AI micromanagement and mission-building time as a source of mission-maker burnout: https://www.reddit.com/r/hoggit/comments/1pzqb99/in_anticipation_of_2026_and_beyond_lets_list_all/
- The Eagle Dynamics forum discussion of the Mission Editor action described the runway-lineup feature in the context of AI formation takeoff: https://forum.dcs.world/topic/385284-mission-editorai-runway-line-up/

Launch Rail responds to that combined signal without pretending to automate DCS: it makes the intended AI departure order visible, catches two common setup collisions before launch, and preserves a compact test record for each group.

## Design and accessibility

This is an **Operate** surface: the queue, timeline, conflicts, and readiness state dominate instead of marketing content. It uses semantic controls, visible keyboard focus, labels on every field, 44-pixel-class touch targets, responsive layouts, reduced-motion support, print styling, and high-contrast status colors that are always paired with text.
