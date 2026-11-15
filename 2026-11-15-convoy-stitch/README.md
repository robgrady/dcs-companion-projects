# Convoy Stitch

Convoy Stitch is a self-contained, offline DCS World ground-route reliability desk. It turns a convoy route into named proof points, highlights geometry and mission-state combinations worth testing first, times a live mission run, and records the first checkpoint where the group fails to progress.

Open `index.html` directly in any modern browser. No server, account, package install, or network connection is required.

## What it does

- Builds an ordered route from origin through decision points, choke points, and destination.
- Records each arriving leg's distance, planned speed, surface, turn severity, and usable width.
- Audits the route with transparent planning heuristics for long unobserved legs, tight turns, bridges/urban passages/fords, narrow routes, surface transitions, mixed mobility, dispersal under fire, and triggered starts.
- Generates a horizontal route thread and a concise Mission Editor test card.
- Runs a proof timer, records checkpoint arrival times, and captures the first observed break.
- Persists the current case in browser `localStorage`.
- Imports and exports complete cases as JSON and provides a print layout.

## Recommended workflow

1. Enter the exact DCS group name, vehicle count, spacing, formation, and relevant mission-state options.
2. Add an origin with a 0 km arriving leg.
3. Add every meaningful route checkpoint in travel order. Bridges, town entries, sharp turns, gates, fords, surface transitions, and destinations should be explicit points.
4. Review the Route Audit. Its findings prioritize proof effort; they do not predict the DCS pathfinder.
5. Run the actual mission, start the Proof Run timer, and mark each checkpoint reached.
6. If movement fails, use **Log break here** at the first failed checkpoint. Preserve the unchanged mission and repeat once before isolating composition, threat/dispersal state, activation logic, or route geometry.
7. Export the case or print the generated test card before clearing it.

## Important assumptions and limits

- Convoy Stitch does **not** simulate DCS AI, terrain meshes, road graphs, bridge logic, collision behavior, or Mission Editor internals.
- Risk thresholds are conservative planning heuristics created for this tool, not published Eagle Dynamics limits.
- Planned travel time is simple distance divided by entered speed; it excludes acceleration, formation compression, traffic, combat, and pathfinding delays.
- A clean audit is not proof of a working route. Only a controlled run in the current DCS build can establish that.
- When reporting a reproducible issue, keep the mission and track as short as practical and record the exact DCS version.

## Community signal

Accessed **2026-11-15**.

- A November 10, 2026 r/hoggit discussion about DCS's structural dependencies argues that persistent logistics and dynamic missions remain fragile and explicitly identifies improved ground AI as necessary for a useful dynamic campaign. This suggested a practical tool focused on locating the *first route break*, not merely noting that a convoy never arrived: https://www.reddit.com/r/hoggit/comments/1xsmnrp/dcs_has_a_structural_dependency_issue/
- An August 29, 2026 r/hoggit mission-design discussion describes unreliable AI pathfinding and the burden of testing shorter route segments. Convoy Stitch turns that community workaround into named, timed proof points without treating the post's suggested distances as official limits: https://www.reddit.com/r/hoggit/comments/1w1ogtc/drunk_ai_pathfinding/
- An Eagle Dynamics forum report documents ground groups ignoring on-road routing or stopping after triggered waypoint pushes. That supports recording late activation, explicit checkpoints, and the first failed push: https://forum.dcs.world/topic/354654-go-to-waypoint-no-longer-functions-since-29657650/
- An Eagle Dynamics forum thread on bridge failures describes reproducible route breaks and units attempting shortcuts around roads, statics, trees, and buildings. That supports explicit bridge and choke-point proof gates: https://forum.dcs.world/topic/332744-ground-units-getting-stuck-at-bridges/
- A forum report about a ground convoy slowing or stopping notes that mixed tracked/wheeled composition and a particular road segment were relevant to isolation. That supports preserving exact composition and comparing controlled runs rather than immediately rebuilding the route: https://forum.dcs.world/topic/380836-ground-convoy-slows-to-a-crawl-or-stops-completely/

The result is deliberately module-agnostic and complements, rather than repeats, the repository's prior cargo evidence, campaign turnboard, trigger-logic, formation-layout, and mission-build tools.

## Design note

Primary surface: **Operate**. The composition centers route construction, findings, proof controls, and evidence capture rather than a marketing hero or equal-weight feature tiles.

Anti-slop audit after implementation: **0/10**. No tech gradient, generic indigo accent, feature-tile grid, accent rails, glass blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch was retained.
