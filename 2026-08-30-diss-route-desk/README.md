# DISS Route Desk

An offline Mi-24P route-planning and active-leg rehearsal companion for DCS World. It turns manually entered route legs into explicit DISS course settings, true/magnetic cross-checks, leg times, an active-leg timing display, cross-track intercept cues, and a printable/copyable crew card.

## Open and use

1. Open `index.html` directly in a modern browser. No server, installation, network connection, or build step is required.
2. Enter the magnetic variation shown by the actual mission/F10 planning data. Use east-positive and west-negative values.
3. Select the heading reference that matches the cockpit setup:
   - **KM-2 corrected / true reference**: the card uses true course as the DISS course setting.
   - **KM-2 at zero / magnetic reference**: the card uses magnetic course as the DISS course setting.
4. Add route legs with fix names, true courses, distances in kilometers, and planned groundspeeds in km/h.
5. Select a leg with the `›` button. Use **Start run** to rehearse timing. Enter observed cross-track displacement (left negative, right positive) and current DISS distance remaining for a bounded intercept cue.
6. Copy or print the compact kneeboard card. Export/import JSON to move a route between browsers or retain a separate mission file.

The active route is saved automatically in browser `localStorage`. The design is responsive, keyboard-focusable, print-aware, and self-contained for `file://` use.

## Important assumptions and limits

- This is a planning/rehearsal aid, not an aircraft flight manual, navigation database, or live connection to DCS.
- The pilot must deliberately choose the heading reference. The app cannot inspect KM-2, heading-system, or DISS state in the cockpit.
- Magnetic course is calculated as `true course − easterly variation` (and therefore plus westerly variation). Courses are normalized to 000–359 degrees.
- Leg time is `distance ÷ groundspeed`. It assumes constant groundspeed and does not calculate wind, acceleration, terrain avoidance, climb/descent, fuel, or threat reactions.
- The active-leg expected-distance display is a timing rehearsal, not sensor data.
- The intercept cue uses `atan(|cross-track| ÷ remaining distance)`, capped at 45 degrees. It is a simple direct-to-course-line geometry cue, not a prescribed Mi-24P technique; use pilot judgment and avoid aggressive corrections near the fix.
- Magnetic variation changes with theater, location, and mission date. Do not reuse the starter value without checking the mission.
- Cross-check mission data, aircraft procedures and limits, weather, terrain, obstacles, fuel, and DISS indications before and during flight.

## Community signal

Accessed **2026-08-30**:

- [Digital Kneeboard Simulator / DCS Mission Card Creator discussion](https://forum.dcs.world/topic/377954-digital-kneeboard-simulator-dcs-mission-card-creator/) — a Mi-24P pilot explicitly requested mission-planning support for fuel/loadout management, **DISS-15 navigation information, true and magnetic headings, and waypoint distance**, noting that an Excel sheet was being used manually. This project addresses the navigation slice without attempting to duplicate that broader web app.
- [Helpful Tip Concerning Doppler Navigation — page 2](https://forum.dcs.world/topic/274428-helpful-tip-concerning-doppler-navigation/page/2/) — May–June 2026 posts show current confusion over whether true or magnetic heading should be entered in the Mi-24P DISS. The discussion explains that KM-2 correction affects the heading reference supplied to the system and that the default corrected setup can show true heading. This directly inspired the app’s explicit heading-reference contract and side-by-side TC/MC output.
- [Mi-24 navigation and targeting capabilities discussion](https://forum.dcs.world/topic/247157-mi-24-nav-amp-targeting-system-capabilities/) — describes the Mi-24’s Doppler/dead-reckoning context, including course, traveled distance, course deviation, and moving-map support. It reinforces the value of a route-leg rehearsal aid rather than a modern GPS-like planner.
- [Official DCS changelog mentioning Mi-24P DISS-15](https://www.digitalcombatsimulator.com/en/news/changelog/openbeta/2.8.7.42583/) — official Eagle Dynamics changelog evidence that the DISS-15 is modeled as a powered aircraft system in the DCS Mi-24P module.

## Design posture

This is an **Operate** surface. The composition prioritizes the heading-reference decision, editable route legs, active-leg action, and the final crew card. It intentionally avoids a marketing hero, decorative statistics, generic feature tiles, gradients, glass effects, and invented operational data.
