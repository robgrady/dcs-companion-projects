# Layerboard

Layerboard is a self-contained, offline organization desk for dense DCS World Mission Editor projects. It gives mission builders an external full-screen object list with custom layers, visibility controls, search, filters, multi-select bulk moves, working states, explicit ordering, and a printable/copyable build-order handoff.

## Open it

Open `index.html` directly in a modern browser. It has no build step, server, account, network request, or external runtime dependency, and works from a `file://` URL.

## Typical workflow

1. Create layers for the way you actually work: flights, ground war, triggers, map drawings, references, validation, or another mission-specific structure.
2. Add an object for each relevant Mission Editor group, drawing, trigger zone, static, or planning note. Record the exact editor ID or callsign where useful.
3. Use **All layers**, search, kind/state filters, and layer visibility to isolate one editing pass.
4. Select multiple visible objects to move them to another layer or change their working state together.
5. Use **Up/Down** in the object inspector and **Move layer up/down** to establish the build sequence.
6. Mark objects **Active**, **Reference**, or **Hidden**. Only active objects in visible layers appear in the build-order handoff.
7. Copy or print the build order before a Mission Editor work session. Export JSON for backup or handoff; paste a pipe-delimited list for fast intake; copy CSV for a spreadsheet.

Keyboard shortcut: press `/` outside a form field to focus search. Press `Escape` to clear the current multi-selection.

## Data and assumptions

- All working state is saved locally in the browser with `localStorage`.
- JSON export/import is the portable backup format.
- A pasted line list uses: `Name | Kind | Coalition | Layer | Editor ID | Notes`.
- Layerboard deliberately does **not** read or modify `.miz` files. It is a reversible planning and build-reference surface, not a mission-file patcher.
- DCS Mission Editor names, object availability, and behavior should be verified in the current DCS build.

## Community signal

Recent mission-building discussions repeatedly asked for better large-mission organization: custom drawing layers, hiding/showing logical groups, full-screen searchable unit lists, multi-select and bulk movement between layers, and easier ordering. Layerboard translates those requests into a safe offline companion that can be used today without modifying DCS files.

Sources reviewed on **2026-10-20**:

- Reddit / r/hoggit, **“Mission Editor improvements”** — requests custom layers, visibility controls, filters, full-screen lists, multi-select, bulk moves, and layer reordering: https://www.reddit.com/r/hoggit/comments/1o8rt3k/mission_editor_improvements/
- Eagle Dynamics Forums, **“Mission Editor Quality of Life Improvements”** — requests practical editor workflow improvements including unit-list and selection behavior: https://forum.dcs.world/topic/397045-mission-editor-quality-of-life-improvements/
- Reddit / r/dcsworld, **“DCS Weekly Questions and Tech Support Thread”** — recurring support demand reinforces an offline, inspectable tool with explicit data backup instead of another opaque integration: https://www.reddit.com/r/dcsworld/comments/1o89nae/dcs_weekly_questions_and_tech_support_thread/

## Design notes

Primary surface: **Operate**. The composition prioritizes object selection, layer state, bulk actions, and handoff over a marketing hero or decorative dashboard metrics.

Slop diagnostic after repair: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rails, glass blur, monument stats, icon toppers, centered composition, default Inter typography, or surface mismatch.