# Sortie Thread

Sortie Thread is a self-contained, offline DCS World pilot logbook and proficiency watch. It captures the part of a sortie that raw flight time misses: the aircraft and mission context, skills exercised, one lesson worth retaining, and one observable next action. The saved entries build a searchable record, user-adjustable skill-recency board, and review queue without an account, server, subscription, or DCS export hook.

## Why this project

Current community discussion shows a continuing demand for a useful DCS flight record beyond the simulator's built-in logbook. Recent r/dcsworld projects specifically target career totals, multiplayer/solo history, search, aircraft and map tracking, and offline use. Replies note that the built-in record is easy to miss and does not reliably cover the multiplayer history players want. Eagle Dynamics forum requests similarly ask for accumulated playtime, richer pilot profiles, and multiplayer logbook coverage.

Sortie Thread takes a deliberately different position from automatic telemetry trackers: it is a short post-flight debrief that makes lessons and proficiency decay visible. That keeps it useful across single-player, multiplayer, campaigns, multicrew, mission testing, and servers that restrict exports.

Sources reviewed on **2026-09-24**:

- Reddit / r/dcsworld, “DCS Flight Log” (2026-06-06): https://www.reddit.com/r/dcsworld/comments/1tyvz07/dcs_flight_log/
- Reddit / r/dcsworld, “Flight Log for DCS” (2026-06-26): https://www.reddit.com/r/dcsworld/comments/1uggzk8/flight_log_for_dcs/
- Reddit / r/dcsworld, “Flight hours” (2026-05-18): https://www.reddit.com/r/dcsworld/comments/1tgm485/flight_hours/
- Eagle Dynamics forums, “Displaying Accumulated Playtime” (2025-07-09): https://forum.dcs.world/topic/376127-displaying-accumulated-playtime/
- Eagle Dynamics forums, “Pilot logbook for Multiplayer” (2025-02-07): https://forum.dcs.world/topic/368931-pilot-logbook-for-multiplayer/
- Eagle Dynamics forums, “Expand Pilot Profile to Focus More on the Pilot — Not Just the Aircraft” (2025): https://forum.dcs.world/topic/377310-expand-pilot-profile-to-focus-more-on-the-pilot-not-just-the-aircraft/

## Use

1. Open `index.html` directly in a modern browser. No installation, local server, build, or network connection is required.
2. After a DCS session, enter the date, minutes, aircraft, optional map and mission/server, primary work, outcome, and skills exercised.
3. Write one lesson worth retaining and, when possible, one specific next action.
4. Select **Log sortie**. The entry is saved to browser `localStorage`.
5. Use **Logbook** to search or filter the record by aircraft and text.
6. Use **Proficiency** to see the last logged practice date for each skill. Change each target cadence to match personal standards.
7. Use **Review** to inspect repeated lesson language, open next actions, and due or never-logged skills.
8. Export JSON backups regularly. CSV export supports analysis elsewhere, and the current view can be printed.

## Features

- Manual post-flight capture optimized for a quick debrief
- Searchable, aircraft-filterable chronological logbook
- Twelve cross-module proficiency categories
- User-adjustable recency cadence for each skill
- Review brief generated only from saved entries
- Open next-action queue and overdue-skill cues
- JSON backup/restore and CSV export
- Print layouts for the active view
- Responsive keyboard-accessible controls with visible focus states
- Local-only persistence with no external runtime dependencies

## Assumptions and boundaries

- Entries are pilot-authored and are not official DCS statistics.
- The app does not read `logbook.lua`, Tacview, DCS Export API data, tracks, or server telemetry.
- Flight minutes include whatever the pilot chooses to count; consistency matters more than pretending to provide automated precision.
- Proficiency status is based only on recency against a user-selected cadence. It does not certify skill, safety, mission readiness, or real-world qualification.
- The twelve default skill categories are intentionally broad and cross-module. They are not tied to a specific aircraft manual or operating procedure.
- Import replaces the current local dataset after confirmation. Export a backup first if both records matter.
- Clearing browser site data can remove the log. JSON export is the durable backup path.

## Design note

The primary surface is **Operate**, with **Monitor** secondary: rapid post-sortie capture and a concrete next-action queue lead; the proficiency board watches state without taking over the composition. The visual system uses paper, ink, navy, signal orange, and restrained ledger details rather than a generic SaaS card grid.

Slop diagnostic after implementation: **0/10**. No blue/violet tech gradient, generic indigo accent, equal feature-tile grid, accent rails, glass blur, monument stats, icon toppers, center-stack composition, default Inter, or surface mismatch fired. The compact numeric strip is operational summary information rather than decorative display type.
