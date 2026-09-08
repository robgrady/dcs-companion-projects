# Sequence Sentry

**Sequence Sentry** is a self-contained, offline debrief desk for F-14B(U) crews who see an unexpected waypoint while using a CDNU flight plan. It compares the Mission Editor route you intended with the AUTO sequence you actually observed, identifies the first divergence, flags repeated and off-route waypoint IDs, and highlights correlation with IDs used by map drawings or additional points.

Open `index.html` directly in any modern browser. No server, installation, account, or network connection is required.

## Use

1. Enter the intended route as one waypoint per line: an ID from 1–99 and an optional short label.
2. Enter the waypoint IDs observed in flight, in order.
3. Optionally list IDs associated with plot lines, drawings, or additional point sets, and record the steering mode shown.
4. Select **Analyze sequence**. Start with the first divergence in the diagnosis pane.
5. Use **Previous** and **Next** to rehearse the transition point-by-point.
6. Complete the controlled-test checklist, add debrief notes, then print or export the session as JSON.

The useful working state is saved in browser `localStorage`. **Clear all** removes it after confirmation.

## Important assumptions and limits

- This is a structural comparison and evidence-capture tool, **not** an emulator of DCS, the Mission Editor, the Mission Data Loader, or the CDNU.
- An overlap between an unexpected waypoint and a drawing/additional-point ID is correlation only; Sequence Sentry deliberately does not declare a simulator bug or root cause.
- The tool accepts waypoint IDs 1–99 for practical note-taking. Heatblur documents up to 50 pre-planned waypoints and 49 additional waypoints, as well as up to 12 flight plans; those facts do not imply every entered ID is valid in every DCS route context.
- Heatblur documents AUTO, OFLY, and MAN as EGI flight-plan steering modes and states that EGI steering uses the active flight-plan waypoint. The checklist asks the crew to verify source and mode rather than inferring them.
- The forum-pattern sample is a diagnostic reconstruction of a reported shape (an intended 1–11 route diverging to waypoint 20 after waypoint 6), not a bundled DCS mission and not proof that all such routes behave identically.

## Why this exists

Recent F-14B(U) discussion shows a specific, repeatable navigation-learning problem: users reported difficulty understanding automatic waypoint sequencing, including a Mission Editor route that advanced from waypoint 6 to waypoint 20 after a plot line was added. The release feedback thread also contains reports where steering behavior differed by page or cockpit start state. The official manual confirms the new EGI/CDNU architecture, multiple steering sources, flight-plan modes, and Mission Editor/DTM flight-plan relationship. Together, those signals support a narrow comparison desk that helps a crew capture exact evidence before changing the mission or reporting a defect.

A contemporaneous r/hoggit thread about long, disappearing F-14 training instructions also reinforced the value of persistent, step-through companion tools. Sequence Sentry applies that persistence to route diagnosis rather than repeating the existing general training-prompt project in this repository.

## Sources reviewed

Accessed **2026-09-08**:

- Eagle Dynamics Forums — **DCS: F-14B(U) – Systems – Navigation**: user reports difficulty understanding AUTO order and a route advancing from WP6 to WP20 after adding a plot line.  
  https://forum.dcs.world/topic/389889-dcs-f-14bu-systems-navigation
- Eagle Dynamics Forums — **F-14B(U) Release Feedback Thread**, page 4: recent navigation and steering-state observations from released-module users.  
  https://forum.dcs.world/topic/390381-f-14bu-release-feedback-thread/page/4
- Eagle Dynamics Forums — **DCS: F-14B(U) Release / DCS 2.9.28.26283**: release status and the upgrade’s EGI/CDNU navigation context.  
  https://forum.dcs.world/topic/390531-dcs-f-14bu-release-dcs-292826283-update-released
- Heatblur F-14B(U) Manual — **Control Display Navigation Unit**: CDNU role, controls, and flight-plan functions.  
  https://f14.manuals.heatblur.se/f14bu/systems/nav_com/cdnu/control_display_navigation_unit.html
- Heatblur F-14B(U) Manual — **Navigation Controls and Displays**: EGI AUTO/OFLY/MAN modes and steering-source behavior.  
  https://f14.manuals.heatblur.se/f14bu/systems/nav_com/navigation_controls_displays.html
- Heatblur F-14B(U) Manual — **Mission Data Loader**: Mission Editor route as flight plan 1 and DTM flight-plan/additional-point structure.  
  http://f14.manuals.heatblur.se/f14bu/systems/mdl/mission_data_loader.html
- Reddit r/hoggit — **DCS World Tutorials**: a user describes losing long F-14 training instructions and repeatedly restarting, a signal for persistent step-through aids.  
  https://www.reddit.com/r/hoggit/comments/1oc0e4d/dcs_world_tutorials/

## Privacy

All data stays in the browser on the local machine unless the user explicitly exports a JSON file. The app makes no network requests.
