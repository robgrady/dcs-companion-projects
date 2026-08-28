# FREQ MARSHAL

FREQ MARSHAL is a self-contained, offline radio-frequency allocation desk for DCS World mission builders and package leads. It centralizes flight, controller, tanker, JTAC, and package assignments; detects exact collisions, reserved-frequency conflicts, out-of-band entries, and user-defined separation warnings; and produces a common comm plan for briefing, print, or handoff.

## Use

1. Open `index.html` directly in a modern browser. No server, connection, install, or build step is required.
2. Name the mission and enter every frequency that must be protected in **Reserved / ATC frequencies**. Include the DCS map's ATC channels, mission AI assignments, guard/server conventions, and any other frequencies already in use.
3. Edit the starter rows or add assignments. Select rows and choose **Auto-assign selected** for collision-free candidate values within the broad band selected on each row.
4. Resolve every red or amber status. Exact duplicates, reserved values, and out-of-band values are red; unassigned and nearby values are amber.
5. Copy the text comm plan, print the board, export CSV, or save a JSON backup. The current board is also persisted in browser `localStorage`.

## Important assumptions and limits

- FREQ MARSHAL is a planning and deconfliction aid, not an RF spectrum authority and not a replacement for the DCS Mission Editor, aircraft manuals, server rules, or local mission standards.
- The built-in UHF (225–399.975 MHz), VHF AM (118–151.975 MHz), and VHF FM (30–87.975 MHz) bands are broad planning buckets. Individual aircraft radios, presets, modulation support, channel steps, AI units, maps, and servers may support narrower or different ranges.
- Auto-assignment uses 0.025 MHz increments and avoids exact values already on the board or in the reserved list. It does **not** claim valid preset compatibility, electromagnetic separation, real-world authorization, or protection from intermodulation.
- The separation-warning value is a user-controlled visual check, not a guarantee. Verify every final frequency and channel in the actual mission and every participating aircraft.
- Starter callsigns and roles are editable organizational examples. Their frequencies are intentionally blank rather than invented.
- All operational data stays in the local browser unless the user explicitly exports or copies it.

## Community signal

The direct signal was a May 10, 2026 Eagle Dynamics forum request describing complex-mission frequency management as “tiresome and challenging.” The requester specifically asked for one central table, duplicate avoidance (including map ATC), bulk assignment, and an exportable list; replies additionally requested reusable variables and channel numbers. A recent r/hoggit discussion also notes that setting radio channels is useful when a mission is not already built with its SRS frequencies, reinforcing the handoff and preset-number workflow.

Sources reviewed on **2026-08-28**:

- Eagle Dynamics Forums — “Radio frequency management tool” (posted May 10, 2026): https://forum.dcs.world/topic/387974-radio-frequency-management-tool/
- r/hoggit — “The A-10C II and CDU usage” (search result surfaced current discussion of setting ARC-210 channels when mission SRS frequencies are absent): https://www.reddit.com/r/hoggit/comments/1ur78o9/the_a10c_ii_and_cdu_usage/
- r/dcsworld — DCS 2.9.28.26283 patch discussion, showing ongoing DTC, aircraft data, and mission-planning workflow changes: https://www.reddit.com/r/dcsworld/comments/1v3isdu/20260722_dcs_patch_notes_292826283/
- Eagle Dynamics — DCS: F-100D Development Report (current module/community context reviewed; not used to invent radio facts): https://www.digitalcombatsimulator.com/en/news/2026-08-22/

## Design note

This is an **Operate** surface: the allocation table, selection state, validation status, and handoff actions carry the hierarchy. It intentionally avoids a marketing hero, decorative metrics, generic feature cards, gradients, glass effects, and non-operational imagery.
