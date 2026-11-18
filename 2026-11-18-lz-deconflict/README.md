# LZ Deconflict

LZ Deconflict is a self-contained, offline staging-zone planner for DCS World cargo missions. It gives mission builders and logistics crews a top-down board for separating aircraft, cargo, scenery, equipment, and visual-reference footprints before a long mission test or multiplayer sortie.

## Use

1. Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.
2. Set the planning-zone width, depth, surface note, and plan name.
3. Add aircraft, cargo, obstacle, and reference footprints. Drag them on the board or use the arrow keys to move the selected footprint by 1 meter; hold **Shift** for 5 meters.
4. Select a footprint to edit its label, dimensions, heading, clearance margin, placement note, and sequence.
5. Resolve dashed conflict footprints until the header reports **Layout clear**.
6. Copy the generated placement card, export/import the plan as JSON, or print a staging sheet.

The active plan persists in browser `localStorage`. Use **Export JSON** before clearing browser data or moving the plan to another browser or machine.

## Important assumptions

- This is a planning and rehearsal aid, not a live DCS connection, terrain parser, cargo API, or authoritative separation standard.
- Every included footprint is a deliberately editable planning envelope. The starter dimensions are not claims about exact DCS object, aircraft, sling, rotor, or wake dimensions.
- Conflict detection uses rotated rectangular footprints expanded by the user-defined clearance margin. It does not model rotor discs, slopes, trees, collision meshes, downwash, cable dynamics, or line-of-sight.
- North/east offsets are relative to the board center, not geographic coordinates. Transfer them into a mission only after choosing a real reference point.
- A clear board does not prove that DCS will spawn, retain, synchronize, attach, detach, or score cargo correctly. Verify the real terrain, object placement, cargo state, load/unload path, and multiplayer behavior in DCS.
- The placement sequence is a crew/build contract, not an automated mission script.
- Export files may contain mission notes. Review them before sharing.

## Why this exists

Recent DCS community discussion continues to identify logistics missions as fragile at the exact handoff between cargo placement and runtime behavior: cargo can appear in an unusable location, disappear after landing, fail to synchronize, or be difficult to distinguish when multiple objects occupy the same pickup area. At the same time, renewed heavy-airlift interest increases the value of a fast preflight tool that separates aircraft, cargo, equipment, and approach references before testing. LZ Deconflict addresses the preventable spatial part of that problem without pretending to fix DCS runtime bugs.

Sources reviewed on **2026-11-18**:

- r/hoggit, **“DCS has a structural dependency issue”** (2026-11-10). The discussion specifically reports cargo disappearing, desynchronizing, or spawning inside objects and terrain, and argues that logistics missions remain dependent on server-side workarounds: https://www.reddit.com/r/hoggit/comments/1xsmnrp/dcs_has_a_structural_dependency_issue/
- Eagle Dynamics, **DCS World release changelog**, reviewed 2026-11-18. The October 2026 releases include fixes for dynamic cargo not being created, incomplete unload lists, and CH-47F cargo loading with closed doors—current evidence that cargo setup and runtime state remain active fault areas: https://www.digitalcombatsimulator.com/en/news/changelog/release/
- Eagle Dynamics Forums, **“AI Cargo doesn't drop cargo”**, reviewed 2026-11-18. A mission-builder reports an AI transport landing correctly while the cargo is not actually delivered, separating route success from cargo-state success: https://forum.dcs.world/topic/383769-ai-cargo-doesnt-drop-cargo/
- r/dcs, **“Multiplayer Server Desyncs when anyone interacts with cargo”**, reviewed 2026-11-18. The report describes cargo interactions causing multiplayer desynchronization during sling-loading and logistics use: https://www.reddit.com/r/dcs/comments/1n8qs5t/
- r/hoggit, **“C-130 Hercules on WWX – Air Drop in a Logistics Multiplayer War”** (2026-01-10). The discussion documents active multiplayer airlift use and a cargo-related workaround affecting automated drops: https://www.reddit.com/r/hoggit/comments/1q8tdbe/c130_hercules_on_wwx_air_drop_in_a_logistics/

## Design notes

This is primarily an **Operate** surface with a secondary **Configure / Inspect** function: the user manipulates spatial objects, sees selection and conflict states immediately, and edits one selected footprint in a focused inspector. It deliberately avoids a marketing hero, equal-weight feature tiles, decorative metrics, glass effects, and generic indigo styling. The field-board visual system uses restrained earth neutrals, one amber action signal, category colors reserved for map semantics, visible focus states, responsive layouts, keyboard nudging, reduced-motion support, and print styling.

### Anti-slop audit

- Initial score: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rail, blur, monument stat, icon topper, center stack, default Inter, or wrong-surface composition fired.
- Final score: **0/10** after implementation review. The Operate composition remains dominant and no compositional tell required repair.
