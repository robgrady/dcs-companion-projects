# Hun Checksmith

Hun Checksmith is a self-contained, offline builder and preflight checker for the custom `checklist.json` supported by the DCS: F-100D Super Sabre module. It turns the module's JSON schema into a fast three-pane workbench: organize categories and procedures, author ordered checklist items, and inspect an in-cockpit-style preview before exporting.

## Use

1. Open `index.html` directly in a modern browser. No server, install, account, or network connection is required.
2. Add categories, procedures, and ordered items. Each item needs an action, required state, and detail priority:
   - **1 — Mandatory**: required to complete the procedure.
   - **2 — Abbreviated**: checks that can be performed in DCS.
   - **3 — Realistic**: real-world checks that may not be testable in DCS.
3. Optionally supply a cockpit clickable identifier, a numeric/string condition, and `once` behavior for advanced module integration.
4. Resolve issues in **Preflight**, then choose **Export checklist.json**.
5. On the DCS computer, place the exported file at `C:/Users/<your username>/Saved Games/DCS: F-100D/checklist.json`. The F-100D manual says this custom file replaces the built-in checklist. Keep a backup of a known-good file.

The browser saves the working draft in `localStorage`. **Import JSON** opens an existing compatible checklist, **New draft** restores the included starter, and **Print preview** creates a compact reference. All data stays local.

## Assumptions and guardrails

- The exported top-level format follows the official F-100D manual: an array of categories, each containing named procedures and item arrays.
- Export preserves only documented item keys used by this app: `text`, `value`, `priority`, `clickable`, `condition`, and `once`.
- Condition strings and clickable point names are module implementation identifiers; Checksmith checks their shape but cannot prove that an identifier exists in the current cockpit model. The official manual recommends DCS ModelViewer2 for finding clickables and the DCS log for diagnosing load errors.
- This is an authoring companion, not a replacement for the module's live automatic condition checks or its **Show Me** cockpit highlighting.
- DCS/module behavior can change during Early Access. Retain the built-in `default.json` as a schema reference after updates.

## Why this project

Current F-100D discussion shows unusually strong demand for the module's new interactive-checklist workflow. A recent Eagle Dynamics forum thread links the official customization instructions, and a user says the checklist “totally changes this module.” The official manual exposes a useful but hand-edited JSON schema, creating a clear need for an offline visual builder that catches missing fields before DCS loads the file. Recent DCS patch discussion also documents active F-100D checklist fixes, reinforcing that pilots are adopting the feature now.

Sources reviewed on **2026-08-22**:

- Eagle Dynamics Forums — “Interactive checklist” (recent F-100D community reaction and link to customization): https://forum.dcs.world/topic/388988-interactive-checklist/
- Official Grinnelli Designs DCS F-100D Manual — “Checklist” (usage, detail priorities, custom-file location, JSON structure, clickables, conditions, and error logging): https://grinnellidesigns.github.io/f-100d-manual/Meta/checklist.html
- Eagle Dynamics Forums — “DCS Changelog and Updates 2026” (F-100D checklist-refresh crash fix and current module update context): https://forum.dcs.world/topic/384996-dcs-changelog-and-updates-2026/
- r/dcsworld — “DCS: F-100D Super Sabre” (community signal around the challenge of a non-fly-by-wire, non-digital aircraft): https://www.reddit.com/r/dcsworld/comments/1suj1aw/dcs_f100d_super_sabre/
- r/dcsworld — DCS 2.9.28.26283 patch discussion (new first-party checklist/bombing-tool workflows elsewhere in DCS, showing wider demand for in-sim procedural aids): https://www.reddit.com/r/dcsworld/comments/1v3isdu/20260722_dcs_patch_notes_292826283/

## Privacy and compatibility

Hun Checksmith has no external runtime dependencies, analytics, telemetry, or network requests. It works from `file://` and uses standard browser APIs: localStorage, File/Blob export, file import, and print. It was created for Rob Grady (`rob@robgrady.com`) as part of the DCS Companion Projects collection.
