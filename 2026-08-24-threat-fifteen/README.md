# Threat Fifteen

Threat Fifteen is a self-contained, offline F-16C mission-planning desk for deciding which threat sites deserve the 15 pre-planned threat steerpoint slots (56–70). It treats a tactical SAM site as one decision rather than consuming attention with every launcher, ranks sites with a transparent mission-consequence score, lets planners protect must-load sites, and produces a concise cockpit-entry/print card.

## Use

1. Open `index.html` directly in any modern browser; no server, install, login, or network is required.
2. Add one entry per tactical site or independent threat. Give the site a coordinate in the exact format your crew intends to enter in DCS.
3. Rate lethality, route relevance, and confidence. The tool computes `lethality × 4 + route relevance × 3 + confidence × 2`; this is prioritization, not a weapon-range or performance model.
4. Protect a site only when mission intent requires it. The first 15 ranked sites are assigned sequentially to steerpoints 56–70; overflow entries are clearly marked `CUT`.
5. Copy or print the cockpit-entry card. Export JSON for backup or handoff; imports replace the current board after validation.

Useful state persists in browser `localStorage`. The app does **not** create or modify a DCS `.dtc` file, infer coordinates, estimate SAM envelopes, or guarantee that a mission's threat picture is current. Planners must validate coordinates, site composition, survivability assumptions, and DCS behavior against the current mission, module guide, and squadron procedures.

## Community signal (accessed 2026-08-24)

- [Eagle Dynamics forum — Threat Waypoint Issues](https://forum.dcs.world/topic/388921-threat-waypoint-issues?do=getLastComment): a current discussion describes large/dynamic missions overflowing the F-16's 15 pre-planned threat positions, multiple launchers from one battery consuming separate positions, and pilots lacking a useful way to prioritize what gets loaded. This is the direct problem Threat Fifteen addresses.
- [r/dcsworld — 2026/07/22 DCS Patch Notes 2.9.28.26283](https://www.reddit.com/r/dcsworld/comments/1v3isdu/20260722_dcs_patch_notes_292826283/): the community patch discussion references DTC threat classes and waypoint data, confirming that DTC threat planning is an active, current workflow.
- [Eagle Dynamics forum — Universal Route Planner With Functional DTC + Persistence System](https://forum.dcs.world/topic/382911-universal-route-planner-with-functional-dtc-persistence-system/): users request centralized route/DTC planning and persistent, accessible mission-planning support.
- [Eagle Dynamics forum — DCS World Mission Plan](https://forum.dcs.world/topic/387925-dcs-world-mission-plan-v110/): positive response to a browser-based, offline/mobile mission-briefing workflow supports this project's portable `file://` format.

## Design and privacy

The app is an **Operate** surface: dense enough to scan, explicit about selection state, keyboard-focus visible, responsive on tablets, and print-friendly. It has no analytics or external runtime dependencies; data stays in the browser unless the user exports it.

Created for Rob Grady (`rob@robgrady.com`) on 2026-08-24.