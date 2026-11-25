# Fogline

Fogline is a self-contained, offline DCS World weather-qualification desk. It turns changing fog, cloud, precipitation, light, AI, sensor, designator, and weapon behavior into a controlled test ladder instead of a remembered anecdote.

## Use

1. Open `index.html` directly in a current browser. No server, internet connection, package install, or build step is required.
2. Record the DCS build, map/range, aircraft, sensor/designator, weapon/task, target, crew, controlled variables, and pass rule.
3. Keep **Clear baseline** as the first ladder row. Edit or add weather conditions that matter to the mission.
4. Select a row, run the same geometry and procedure, then score acquisition, tracking, designation/handoff, and intended effect as Pass, Fail, N/A, or Untested.
5. Enter the measured range and an evidence note, then select **Commit active run**.
6. Review the local clearance summary. Fogline calls out a failed baseline, incomplete gates, and non-monotonic evidence that deserves a repeat.
7. Copy or print the clearance brief, or export JSON for backup and handoff.

Campaign state is stored in browser `localStorage`. The app includes JSON import/export and a clearly labeled example evidence set that replaces the current campaign only after confirmation.

## Important assumptions

- Fogline records empirical results; it does not connect to DCS, parse a mission, read telemetry, or calculate sensor physics.
- Results apply only to the recorded DCS build, mission geometry, target, loadout, crew procedure, and weather setup.
- A lower stated visibility condition passing while a clearer condition fails is flagged as a repeatability problem, not automatically interpreted as a simulator defect.
- Weather labels and numerical settings are user-entered because mission presets, maps, modules, and test goals differ.
- “Qualified” means the app's user-defined gates passed. It is not an official module limitation and is never real-world aviation or weapon-performance data.
- Re-run important ladders after relevant DCS updates or mission changes.

## Community signal

Built on **2026-11-25** after reviewing current official changes and recurring community uncertainty about what fog and cloud conditions affect in a given DCS version:

- Eagle Dynamics' 2026 release changelog states that DCS 2.9.29.27278 improved fog-condition effects on laser weapons and designators. That is a direct reason to re-test mission assumptions by build rather than rely on old rules of thumb. Accessed 2026-11-25: https://www.digitalcombatsimulator.com/en/news/changelog/release/
- Eagle Dynamics' Volumetric Weather White Paper says fog and dust can affect AI and sensor visibility and describes weather-related behavior as an area of continuing development. Accessed 2026-11-25: https://www.digitalcombatsimulator.com/upload/medialibrary/4be/i4yclzs5ict5bkd1pe4bxrz0zqz1dffz/Volumetric_Weather_White_Paper.pdf
- An r/hoggit discussion, “Does DCS AI still see you through the clouds?”, shows players actively testing and disagreeing about AI behavior under cloud, fog, rain, and tasking conditions. Fogline is designed to capture a controlled answer for the user's exact build and setup. Accessed 2026-11-25: https://www.reddit.com/r/hoggit/comments/1k5clkm/does_dcs_ai_still_see_you_through_the_clouds/
- The r/hoggit discussion around the fog-progress newsletter repeatedly asks whether visual weather, AI detection, sensors, and weapons now agree. That recurring uncertainty supports a reusable qualification ladder rather than another static reference card. Accessed 2026-11-25: https://www.reddit.com/r/hoggit/comments/1gry8wt/dcs_newsletter_f104_video_report_fog_progress/
- Eagle Dynamics forum users continue to compare auto/manual fog behavior and script-visible fog settings, reinforcing the need to record the exact test contract and build. Accessed 2026-11-25: https://forum.dcs.world/topic/366655-does-new-fog-works-with-auto-mode/

Community statements are demand signals, not technical authority. Official notes describe product changes but do not replace a controlled mission-specific test.

## Design notes

**Surface:** Configure is primary; Monitor is secondary. The test contract and weather ladder dominate the composition, while the right rail monitors evidence quality and the active run. A marketing hero would be the wrong surface.

**System:** near-black weather-station surfaces, warm ochre action color, restrained sea-glass secondary color, Georgia headings, Avenir/system body, and monospaced evidence labels. Motion is limited to the run timer and toast; reduced-motion preferences are respected.

**Anti-slop audit before repair: 0/10.** None of the ten tells fired: no tech gradient, generic indigo accent, feature-tile grid, accent rail, decorative blur, monument statistic, icon toppers, center stack, default Inter typography, or surface mismatch.

**Anti-slop audit after verification: 0/10.** The composition remained contract-first and ladder-first at desktop and responsive breakpoints.

## Files

- `index.html` — complete app with inline CSS and JavaScript
- `README.md` — usage, assumptions, source context, and design audit
