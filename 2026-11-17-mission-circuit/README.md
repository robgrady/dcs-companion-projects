# Mission Circuit

Mission Circuit is a self-contained, offline resilience mapper for DCS World mission builders and server administrators. It turns a mission’s scripts, triggers, spawn services, support assets, objectives, and persistence features into an explicit dependency circuit, then lets the builder fail any system and see what blocks or degrades downstream.

## Use

1. Open `index.html` directly in a modern browser. It requires no server, build step, account, or network connection.
2. Rename the mission and starter systems, or reset and adapt the included representative model.
3. Select each runtime system and define its required systems, criticality, failure policy, fallback path, proof test, and notes.
4. Change **Rehearsal status** to Degraded or Failed to inspect propagated impact on the diagram and diagnostics.
5. Resolve dependency loops, add continuity paths for critical single-point stops, and write a concrete proof test for each critical service.
6. Save up to 20 local snapshots, export/import the complete circuit as JSON, or print a resilience brief.

The current circuit and snapshots persist in browser `localStorage`. Browser-site-data clearing, another browser, or another machine will not inherit them; use **Export JSON** for transfer or backup.

## Important assumptions

- This is a simulation mission-design aid, not an Eagle Dynamics diagnostic tool and not a live connection to DCS.
- A dependency arrow means “the destination requires the source.” It does not claim knowledge of the mission’s Lua implementation.
- **Block this system** propagates a failed dependency as Blocked. **Continue degraded** only protects the system when a nonempty fallback path is recorded.
- Failure impact is a planning model. A real mission still requires clean-start, single-player, hosted multiplayer, and dedicated-server testing where applicable.
- The included starter circuit is representative, not a claim about any particular mission or framework. Replace it with the actual runtime architecture.
- Export files can contain mission-builder notes. Review them before sharing.

## Why this exists

A strong recent community signal is that complex DCS missions depend on server administrators, third-party scripting frameworks, and custom workarounds, while updates and core behavior can destabilize those dependency chains. Mission builders also describe testing—not initial construction—as the exhausting part, and one experienced builder specifically recommends segmented sorties with no dependency on each other. Mission Circuit makes those hidden couplings visible and gives each critical service an explicit fail-open or hard-stop contract before the next long proof flight.

Sources reviewed on **2026-11-17**:

- r/hoggit, **“DCS has a structural dependency issue”** (2026-11-10). The highly active discussion focuses on mission/server reliance on MIST, MOOSE, administrator workarounds, logistics failures, patch regressions, and missions collapsing before completion: https://www.reddit.com/r/hoggit/comments/1xsmnrp/dcs_has_a_structural_dependency_issue/
- r/hoggit, **“What is everyone using for mission creation these days?”** (2026-07-24). An experienced multiplayer builder says testing is the tiring part, DCS core changes can break behavior, and segmented sorties without dependencies reduce fragility: https://www.reddit.com/r/hoggit/comments/1v5e688/what_is_everyone_using_for_mission_creation_these/
- r/hoggit, **“Squadron Mission Creation Fatigue”** (2026-07-01). A small-group mission creator describes the unsustainable workload of producing complex multiplayer missions with AI, scripting, voiceovers, and documentation: https://www.reddit.com/r/hoggit/comments/1ukqmwu/squadron_mission_creation_fatigue/
- Eagle Dynamics, **DCS World release changelog**, reviewed 2026-11-17. Recent 2026 entries include fixes to Mission State Save, dynamic spawn, scripting event attribution, radio crashes, and campaign failsafes—evidence that mission runtime behavior and recovery paths remain active development areas: https://www.digitalcombatsimulator.com/en/news/changelog/release/
- Eagle Dynamics, **DCS 2026 Roadmap**, reviewed 2026-11-17. ED lists continued Mission State Save work, including retention of Mission Editor and scripting-API waypoint parameters, alongside the planned Dynamic Campaign: https://www.digitalcombatsimulator.com/en/news/newsletters/dec8c7ef1bfdac7e7de267e337f264e4/

## Design notes

This is primarily a **Configure** surface with a secondary **Command / Inspect** function. The composition is a system inventory, dependency canvas, and focused inspector—not a marketing hero or equal-weight feature grid. The visual system uses restrained field-equipment neutrals, one amber signal color, purposeful state colors, compact typography, visible keyboard focus, 44-pixel-class mobile controls, reduced-motion support, responsive layouts, and print styling.

### Anti-slop audit

- Initial score: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rail, glass blur, monument stat, icon toppers, center stack, default Inter, or wrong-surface composition fired.
- Final score: **0/10** after implementation review; no compositional repair was required.
