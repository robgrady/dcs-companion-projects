# PATCHLINE

PATCHLINE is a self-contained, offline DCS World update-verification desk. It helps a pilot or squadron define a small, explicit pre/post-patch test line, record observed results, and separate reproducible failures from patch-day impressions.

## Use

1. Open `index.html` directly in any modern browser; no server, account, installation, or network connection is required.
2. Name the run and enter the previous and new DCS build numbers.
3. Keep, remove, or resolve the four generic platform checks. Add only the module/system checks that matter to your normal flying.
4. For each check, state the observable expected result, assign a priority, then mark it **Pass**, **Fail**, or **Skip** after the update. Put a useful timestamp, track filename, log reference, or concise observation in Evidence.
5. Filter by group/status, print a compact run card, or export the complete run as JSON. JSON exports can be imported later or handed to another tester.

All useful state autosaves in browser `localStorage`. Reset restores the four generic core checks. Printing suppresses controls and produces a clean verification card.

## Assumptions and boundaries

- PATCHLINE is a runbook and evidence recorder, not an automated DCS test harness.
- A failed check is not automatically a DCS defect. Reproduce it on a clean setup, account for mods and local configuration, and collect logs/tracks before reporting.
- The built-in checks are intentionally module-agnostic and make no claim about a specific aircraft's systems.
- Exported JSON may contain user-entered notes; inspect it before sharing.
- The app requires a modern browser with `localStorage`, `Blob`, and file input support. It runs under `file://` and has no external runtime dependencies.

## Community signal (researched 2026-08-26)

Today's official patch status listed **26 August 2026** as the next planned update. In the fresh August/September patch discussion, users immediately asked whether specific Apache flight-model work, MiG-29 work, Viper MFD colors, further DTC integration, and an updated F-14B(U) campaign would be included. Those posts show a recurring patch-day problem: pilots care about different module behaviors, but patch anticipation and post-update impressions are not a shared, reproducible test plan. PATCHLINE converts that uncertainty into scoped checks and evidence without asserting that any requested change actually shipped.

Sources:

- Eagle Dynamics Forums, “Patch Status” — current build and planned update date: https://forum.dcs.world/topic/233848-patch-status (accessed 2026-08-26)
- Eagle Dynamics Forums, “patch note discussion August / September 2026” — current user questions and requested areas: https://forum.dcs.world/topic/391583-patch-note-discussion-august-september-2026/ (accessed 2026-08-26)
- Eagle Dynamics Forums, “DCS Changelog and Updates 2026” — authoritative changelog context: https://forum.dcs.world/topic/384996-dcs-changelog-and-updates-2026/ (accessed 2026-08-26)

## Files

- `index.html` — complete application, with CSS and JavaScript inline
- `README.md` — usage, assumptions, provenance, and sources
