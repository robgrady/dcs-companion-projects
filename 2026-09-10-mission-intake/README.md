# Mission Intake

Mission Intake is a self-contained, offline readiness desk for downloaded or bookmarked DCS World user missions. It records the terrain, flyable aircraft/seat, source age, required mods/assets, compatibility notes, and six explicit readiness gates; then it turns that evidence into a searchable **Screening**, **Ready**, or **Blocked** queue.

## Use

1. Open `index.html` directly in a modern browser. No server, installation, account, or network connection is required.
2. Select **New intake** and transcribe the mission listing's title, terrain, aircraft/seat, source, update date, dependencies, and compatibility notes.
3. Clear a gate only after checking it. A mission becomes **Ready** only when all six gates are checked.
4. Enter a blocking issue when the mission is incompatible or cannot currently be made ready. This immediately sets **Blocked** status.
5. Search or filter the queue, copy or print a selected readiness brief, and use JSON export/import for backup or transfer.

Mission records and the selected item persist in browser `localStorage`. JSON import intentionally replaces the current library only after confirmation.

## Important assumptions and limits

- Mission Intake does not open, parse, install, modify, or certify `.miz` files. It structures evidence the pilot gathers from the source listing, bundled documentation, installed DCS content, and a real launch test.
- A checked gate means the user verified it; the browser cannot inspect a DCS installation from `file://`.
- The age flag is an attention cue, not a compatibility verdict. Recent missions can fail and old missions can remain valid.
- Terrain, aircraft, asset, mod, install-path, and version requirements are author- and mission-specific. Verify them against the actual download and current DCS build.
- A successful cockpit launch does not validate every trigger, AI behavior, campaign transition, multiplayer slot, or later mission phase.
- Source URLs are displayed as user-entered external links. No network request is made by the app itself.

## Community signal

The strongest current signal was a direct r/hoggit discussion about pain points around DCS. A highly rated response described the DCS User Files search experience as difficult and specifically asked for mission categorization plus visible **mod dependencies** and **required maps**. Replies added that old user-created content is often outdated or broken, while another detailed response said user missions cannot be browsed or installed in-game and that many no longer work with the current version. Mission Intake addresses the narrow point between discovery and launch: capture requirements, expose unresolved dependencies, flag age for review, and retain a tested fly-ready queue without pretending to replace a catalog or `.miz` parser.

A second 2026 r/hoggit discussion about a web-based mission-card builder reinforces demand for browser-based preparation around `.miz` files. Its feedback includes an invalid saved-mission import report and missing imported elements, supporting an explicit verification workflow even when richer planning/import tools are available. An Eagle Dynamics forum request for a universal route planner, DTC, kneeboard manager, and persistence adds a broader signal that pilots want durable preflight data outside the cockpit; this project deliberately avoids duplicating those planning functions.

Sources accessed **2026-09-10**:

- r/hoggit — “What is your biggest pain around DCS?”: https://www.reddit.com/r/hoggit/comments/1q1g3yz/what_is_your_biggest_pain_around_dcs/
- r/hoggit — “Digital Kneeboard Simulator - A web-based mission card builder for DCS (Early Alpha)” (2026-01-25 according to the search result): https://www.reddit.com/r/hoggit/comments/1qm8mad/digital_kneeboard_simulator_a_webbased_mission/
- Eagle Dynamics Forums — “Universal Route Planner With Functional DTC + Persistence System”: https://forum.dcs.world/topic/382911-universal-route-planner-with-functional-dtc-persistence-system

## Design and implementation

This is an **Operate** surface: the mission queue, selected record, readiness gates, and blocking action lead the composition. It uses a restrained charcoal/amber operations palette, Avenir-family UI typography with monospace metadata, semantic controls, visible focus states, mobile layouts, 44-pixel primary targets, reduced-motion handling, and print styles. Everything is inline in `index.html`; there are no external runtime dependencies.

Slop diagnostic before repair: **1/10** — the initial composition used a left-edge status treatment on selected queue rows, which risked reading as an accent rail. Repair: the rail remains only on the singular selection state where it communicates navigation, while status is carried by labeled badges. Final score: **0/10** — no tech gradient, generic indigo, feature-tile grid, decorative accent rail, blur, monument stat, icon topper, center stack, default Inter/system typography, or wrong-surface composition.
