# Cartridge Desk

Cartridge Desk is a self-contained, offline mission-data worksheet for DCS World. It turns a mission brief into an orderly cockpit-entry queue: navigation/target points, a cross-airframe radio card, a threat/action contract, and free-form crew notes. It does **not** write DCS files or claim to emulate a module's data-transfer cartridge; it produces a human-readable entry and kneeboard aid.

## Use

1. Open `index.html` directly in a modern browser; no server or network connection is required.
2. Identify the mission and aircraft, then work left-to-right through Points, Radios, Threats, and Crew notes.
3. Watch the readiness inspection for incomplete categories. Values save automatically in browser `localStorage`.
4. Print the active section as a compact card, or export JSON for backup and later import.
5. Treat the included point example strictly as a formatting example and replace every value before flight.

## Assumptions and safety

- Coordinates, elevations, frequencies, threat envelopes, and reactions must come from the current mission brief and applicable module documentation.
- Coordinate text is preserved verbatim; Cartridge Desk performs no datum or format conversion.
- Radio and navigation entry procedures vary by aircraft. This tool is an airframe-neutral worksheet, not an avionics authority.
- Export/import covers the complete worksheet. Browser-local data remains on the current browser profile unless exported.

## Community signal (reviewed 2026-08-13)

Recent live search was constrained by Reddit returning HTTP 403 to direct listing/API requests, so no inaccessible post text is quoted. The accessible current Eagle Dynamics forum index surfaced the active question **“Isn't a DTC a thing for the A-10C too?”**, reinforcing recurring demand for easier mission-data preparation across modules rather than another airframe-only aid. The current DCS User Files index also showed fresh July 2026 cockpit-readability modifications, a secondary signal that cockpit-readable information presentation remains an active user concern. Cartridge Desk deliberately addresses the preflight/human-readable portion without pretending to integrate with DCS avionics.

Sources accessed 2026-08-13:

- Eagle Dynamics, Digital Combat Simulator forum index: https://forum.dcs.world/forum/22-digital-combat-simulator/
- DCS World User Files index (current listing/search signal): https://files.digitalcombatsimulator.com/en/files/index.php
- r/hoggit recent search endpoint (request returned HTTP 403; recorded for research transparency): https://www.reddit.com/r/hoggit/search.rss?q=DCS&restrict_sr=on&sort=new&t=month
- r/dcsworld recent search endpoint (request returned HTTP 403; recorded for research transparency): https://www.reddit.com/r/dcsworld/search.rss?q=DCS&restrict_sr=on&sort=new&t=month

## Design and accessibility

The app uses a **Configure** surface: mission identity first, sequential data sections second, and persistent readiness inspection alongside. It has semantic tabs, keyboard arrow navigation, visible focus states, 44px controls, responsive single-column behavior, restrained print output, and no external dependencies.
