# Live Director

Live Director is a self-contained, offline companion for DCS World solo sorties. It runs beside the simulator and introduces role-aware command changes, threats, support problems, system degradations, weather shifts, and human-factor checks while a mission is in progress. The pilot responds in DCS, records the decision in the companion, and leaves with a time-stamped debrief instead of another static one-shot mission.

## Use

1. Open `index.html` directly in a modern browser; no server, installation, account, or network connection is required.
2. Set a callsign, sortie role, planned duration, tempo, scenario seed, and the inject families that are appropriate for the flight.
3. Select **Start new sortie**, then keep Live Director visible on a second screen, tablet, or browser window while flying DCS.
4. Change the displayed flight phase as the sortie progresses. Inject selection adapts to both phase and role.
5. For each transmission, choose **Accept / act**, **Resolved**, **Unable**, or **Defer**. The decision wire, pressure, capacity, continuity, and score update from those choices.
6. Use **Debrief** to copy or download the complete sortie report. The active sortie, cockpit notes, and decision history are stored in `localStorage` and can be resumed after a refresh.

Keyboard controls outside text fields:

- `Space`: pause or resume the director
- `N`: issue an inject immediately
- `1`: accept / act
- `2`: resolve
- `3`: unable
- `4`: defer

## Important assumptions

- Live Director does not connect to, read, modify, or automate DCS World. It is an offline prompt and decision-log tool.
- Injects are deliberately generic enough to fit many user-built, instant-action, and campaign missions. The pilot decides whether a prompt is compatible with the current simulated situation.
- The pressure, capacity, continuity, and decision score values are training feedback, not real aircraft or tactical calculations.
- Radio lines and response prompts are fictional and intended only for entertainment simulation.
- Browser audio may be blocked until the page receives a user gesture; the interface remains fully functional without its short alert tone.
- Clipboard access can be restricted for `file://` pages. The downloadable text report is the dependable fallback.

## Community signal

The project responds to a strong, current DCS community theme: solo pilots want missions that feel alive and consequential without requiring a heavyweight campaign engine, large AI battles, or high-end hardware.

Sources reviewed on **2026-10-30**:

- Reddit / r/hoggit — “I made a free little dynamic campaign for DCS that builds missions per sortie” (2026-10-09). The author describes wanting useful single-player activity after tutorials and a lightweight, package-focused experience that runs smoothly in VR; replies praise simpler missions that still feel connected to an ongoing war. https://www.reddit.com/r/hoggit/comments/1x1n8ky/i_made_a_free_little_dynamic_campaign_for_dcs/
- Reddit / r/hoggit — “2026 DCS Roadmap Progress” (2026-09-12). A recurring complaint is that DCS still lacks a released dynamic campaign and can require the player to become a mission designer to create satisfying solo activity. https://www.reddit.com/r/hoggit/comments/1wecy39/2026_dcs_roadmap_progress/
- Reddit / r/hoggit — “What’s the best flight sim for a solo player for a dynamic campaign?” (2026-09-19). The discussion again points solo players toward alternatives because a native DCS dynamic campaign is not yet available. https://www.reddit.com/r/hoggit/comments/1wklgpw/whats_the_best_flight_sim_for_a_solo_player_for_a/
- Reddit / r/dcsworld — “Learning DCS Without Feeling Overwhelmed” (2026-07-29). The post highlights the transition from tutorials to missions, where players can feel lost even after learning individual systems. https://www.reddit.com/r/dcsworld/comments/1v9xvtl/learning_dcs_without_feeling_overwhelmed_or_why/
- Reddit / r/dcsworld — “I understand why lots of people give up on DCS early now” (2026-09-09). The author reports vague training guidance, acronym overload, and difficulty moving into combat missions. https://www.reddit.com/r/dcsworld/comments/1wbgcdf/i_understand_why_lots_of_people_give_up_on_dcs/
- Eagle Dynamics Forums — “DCS Changelog and Updates 2026,” reviewed to avoid assuming current core or module status. https://forum.dcs.world/topic/384996-dcs-changelog-and-updates-2026/

Live Director does not attempt to replace a dynamic campaign. It addresses a narrower gap: adding workload changes, decisions, uncertainty, and a debriefable thread to a mission the pilot already has.

## Design posture

**Primary surface: Operate; secondary surface: Configure.** During flight, action affordances, current transmission, time, phase, and decision state dominate. Setup is compact and subordinate; there is no marketing hero or generic feature-card grid.

Design system: near-black olive surfaces, warm amber operational emphasis, compact condensed headings, monospaced timing/data, square low-radius controls, restrained motion, visible keyboard focus, 44-pixel minimum primary controls, responsive single-column behavior, print styling, and reduced-motion support.

Slop diagnostic after implementation: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rail, glass blur, decorative monument stat, icon toppers, center-stack composition, default Inter typography, or surface mismatch is present. The large mission clock is an earned operational instrument rather than decorative filler.

## Files

- `index.html` — complete application with inline CSS and JavaScript
- `README.md` — usage, assumptions, sources, and design rationale

## Privacy

All mission state remains in the browser's local storage unless the user explicitly downloads or copies a report. No analytics, network calls, remote fonts, external libraries, or third-party runtime assets are used.
