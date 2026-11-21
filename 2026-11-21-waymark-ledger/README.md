# Waymark Ledger

Waymark Ledger is a self-contained, offline DCS World waypoint crosswalk and briefing-lint tool. It gives each meaningful point a stable, human-readable alias—such as `HOME`, `PUSH`, or `EGRESS`—then keeps planned and currently observed cockpit waypoint numbers side by side. The briefing linter finds fragile bare calls such as `WP7` and can convert uniquely mapped calls into alias-first language.

## Use

1. Open `index.html` directly in a modern browser. It requires no server, account, installation, build step, or network connection.
2. Name the sortie and add each meaningful route point. Give every point a unique stable alias and a concise purpose.
3. Enter the planned waypoint number and the number currently observed in DCS. **Renumber observed** can rebuild a simple sequential observed route from WP0 or WP1.
4. Paste the text briefing or comm plan into **Briefing lint**. Open **Report** to review bare waypoint references.
5. Use **Copy alias-first brief** to replace uniquely mapped raw calls with forms such as `PUSH (WP4)`. Ambiguous or unmapped numbers are deliberately left unchanged.
6. Copy the generated handoff, print a compact crosswalk, export CSV, or save the complete ledger as JSON.

The current ledger persists in browser `localStorage`. **Load demo** replaces it with an intentionally broken example containing number drift, raw calls, and a duplicate alias.

## Important assumptions and limits

- Waymark Ledger does not read or write `.miz`, DTC, cartridge, track, or aircraft files. Planned and observed numbers are entered by the pilot or planner.
- A stable alias is a crew convention, not a DCS feature. Every participant must receive and use the same crosswalk.
- The app treats a number as uniquely mapped only when exactly one ledger row has that planned or observed number. It will not guess through ambiguity.
- **Renumber observed** creates a simple contiguous sequence in the current ledger order. It does not claim to reproduce every aircraft's internal numbering rules or DCS route transformations.
- The linter recognizes bare English forms such as `WP4`, `WP #4`, and `waypoint 4`. It is not a full natural-language parser.
- Clipboard access from `file://` depends on browser policy; the app falls back to selecting and copying its generated handoff where possible.
- This is a simulation-only planning aid. The mission, current cockpit indications, module documentation, and flight lead remain authoritative.

## Why this project

A current r/hoggit release discussion for Frag Orders v2 shows strong demand for collaborative DCS planning around routes, waypoints, DTC data, radio presets, timelines, kneeboards, and visible changes across a package. A September community request separately described the pain of sharing complex routes and named functions such as hold points with ad-hoc multiplayer flights. The sharp failure mode comes from an August DCS changelog discussion: users documented route points being deleted or reindexed after progress/save behavior, breaking patrol logic as well as written briefs, annotated intel images, home-plate references, and calls such as “north of WP7.” Waymark Ledger addresses that narrow communication problem without trying to duplicate a full mission planner: names remain stable while cockpit numbers become replaceable crosswalk data.

Sources reviewed on **2026-11-21**:

- r/hoggit, **“Frag Orders: DCS Multiplayer Mission Planning system v2 release”** (2026-11-17). The tool and replies emphasize shared flight routes, waypoint editing, DTC preparation, radio presets, timelines, live planning changes, kneeboards, and slot coordination: https://www.reddit.com/r/hoggit/comments/1xy5vvy/frag_orders_dcs_multiplayer_mission_planning/
- r/hoggit, **“We desperately need a way to share waypoints and flight plans in MP”** (2026-09-17). The discussion asks for spontaneous multiplayer route sharing, including waypoint purpose, hold points, and TOT data, and describes manually talking other pilots through matching steerpoints as a recurring burden: https://www.reddit.com/r/hoggit/comments/1wiy5sc/we_desperately_need_a_way_to_share_waypoints_and/
- r/hoggit, **“DCS 2.9.29.27278”** changelog discussion (2026-08-26). A detailed route-indexing report explains that passed points can disappear or shift on save/resume, invalidating waypoint-number-based briefings, intel imagery, home-plate references, patrol routing, and multiplayer calls: https://www.reddit.com/r/hoggit/comments/1vz0axh/dcs_292927278/
- Eagle Dynamics Forums, **“DCS Changelog and Updates 2026.”** Current official changelog context includes continuing Route Tool and DTC waypoint work, including labels, route sequencing, and waypoint-number reordering: https://forum.dcs.world/topic/384996-dcs-changelog-and-updates-2026/

## Design notes

This is primarily a **Configure** surface with secondary **Inspect** behavior: the pilot defines a stable route vocabulary, enters planned/observed crosswalks, and resolves explicit validation findings. The table and checks dominate; there is no marketing hero, feature-card grid, or decorative dashboard. The visual system uses field-document neutrals, restrained amber action color, condensed utility type, visible focus states, 44-pixel controls, responsive stacking, reduced-motion handling, and print styling.

### Anti-slop audit

- Initial score: **0/10**. No blue/violet tech gradient, generic indigo accent, feature-tile grid, accent rail, unearned blur, monument stat, icon topper, center stack, default Inter, or wrong-surface composition fired.
- Final score: **0/10** after implementation review. The Configure composition remains dominant; the three compact counts report validation state rather than acting as decorative monument statistics.

## Privacy and portability

Waymark Ledger sends no data anywhere. Its route and briefing state stay in the browser's local storage until reset. The app contains all CSS and JavaScript inline, has no external runtime dependencies, and works from a `file://` URL.
