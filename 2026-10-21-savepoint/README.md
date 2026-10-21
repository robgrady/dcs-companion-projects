# Savepoint

Savepoint is a self-contained, offline change-control desk for DCS World Mission Editor work. It helps mission builders record meaningful edits, create deliberate versioned checkpoints, preserve manual rollback instructions, and verify that a saved `.miz` remains usable.

It does **not** read, modify, or inspect mission files. It is a companion ledger for the human workflow around Mission Editor.

## Why this exists

Mission builders continue to ask for undo support and safer recovery from accidental edits. A July 2026 Eagle Dynamics forum thread announced a third-party Mission Editor undo extension, described the missing undo capability as a long-running problem, and drew requests for wider coverage including routes, waypoint actions, triggers, weather, briefings, and drawings. The thread also notes that an editor update can require the extension installer to be rerun, which leaves value in a dependency-free manual safety workflow.

Recent Reddit discussions reinforce the same operating pattern: keep a known-good mission, save iterative copies, and roll back when experimentation breaks a mission. Savepoint turns that advice into a disciplined, visible process without installing a mod or touching DCS files.

## Use

1. Open `index.html` directly in a browser. No server or network connection is required.
2. Enter the current working `.miz` filename.
3. Before or immediately after each meaningful Mission Editor operation, log:
   - the object or editor area;
   - what changed;
   - a manual reverse step;
   - the focused test that should prove the edit works;
   - the risk level.
4. Before risky work—or after a coherent batch—choose **Create checkpoint**.
5. Use DCS **Save As** with the generated versioned filename, then confirm that step in Savepoint.
6. Complete the verification gate: separate save exists, file reopens, mission loads, and focused tests pass.
7. If work must be abandoned, use **Rollback** to reverse dirty changes from newest to oldest.
8. Export a JSON backup when moving browsers or archiving a project handoff.

## Features

- Dirty-change queue with risk labels and explicit reverse/test instructions
- Sequential, generated `.miz` checkpoint filenames
- Reverse-ordered rollback runbook with completion tracking
- Four-step known-good verification gate
- Copyable dirty-change brief
- JSON backup and restore
- Print-friendly active views
- Responsive layout, keyboard-visible focus, 44px mobile targets, and reduced-motion support
- Local persistence through `localStorage`

## Important assumptions

- Savepoint cannot confirm that a `.miz` was actually saved, reopened, or tested; the operator attests to those steps.
- A checkpoint should be a separate DCS **Save As** file, not an overwrite of the only known-good mission.
- Rollback instructions are only as useful as the detail entered before the problem occurs.
- Browser storage is device/profile specific. Export JSON backups for durable records.
- Import replaces the current Savepoint workspace after confirmation.
- The app has no external runtime dependencies and is designed to work through `file://`.

## Community signals reviewed

Accessed **2026-10-21**:

- Eagle Dynamics Forums — “Undo functionality for DCS Mission Editor” (July 2026). Announces a third-party undo extension, lists initial edit types, and records community requests to cover waypoint properties/actions, triggers, weather, briefing, and drawings: https://forum.dcs.world/topic/390272-undo-functionality-for-dcs-mission-editor/
- r/dcsworld — “help with mission editor” (April 24, 2026). A responder recommends retaining an unchanged mission, saving experiments, and returning to the last good `.miz` when changes break the setup: https://www.reddit.com/r/dcsworld/comments/1su2snp/help_with_mission_editor/
- r/hoggit — “Problem with a mission after saving it” (September 20, 2024). Advice emphasizes alternating filenames or incrementing versions after major changes so lost or damaged work does not reset the project to zero: https://www.reddit.com/r/hoggit/comments/1flnk1c/problem_with_a_mission_after_saving_it/
- r/dcsworld — “Petition to introduce undo/redo into DCS Mission Editor” (July 24, 2023). A high-response request illustrates the longstanding demand and the ease of accidental destructive edits: https://www.reddit.com/r/dcsworld/comments/157upu0/
- Eagle Dynamics Forums — “DCS 2026 Core feature Wishlist.” The current wishlist again requests Mission Editor undo: https://forum.dcs.world/topic/384194-dcs-2026-core-feature-wishlist/

## Design posture

Savepoint is an **Operate** surface. The dirty queue, checkpoint action, rollback order, and verification state carry the hierarchy. It intentionally avoids a marketing hero, decorative statistics, gradients, glass effects, and equal-weight feature tiles.

## Privacy

All operating data remains in the current browser unless the user explicitly exports a JSON file or copies a brief. No analytics, network calls, or external assets are included.
