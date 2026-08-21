# Mod Sift

Mod Sift is a self-contained, offline DCS World mod-isolation workbench. Given a list of suspect mods and a passing all-mods-disabled baseline, it repeatedly splits the suspect set in half and records whether the same fault appears. This reduces a long sequence of one-by-one tests to a short, auditable decision trail.

## Use

1. Open `index.html` directly in a browser; no server, installation, or network connection is required.
2. Enter the DCS build or a short incident label.
3. Add one mod or mutually dependent mod group per line, using the exact name shown by your mod manager.
4. Disable every listed mod with your normal manager and confirm the clean baseline passes.
5. Start isolation. For each step, enable only the amber **Enable + Test** set, keep the holdout disabled, reproduce the same scenario, and record whether the issue returned.
6. When one candidate remains, perform the requested A/B confirmation. Export the JSON decision log if you need to share or preserve the evidence.

The run, manifest, and history persist in `localStorage`. **Undo last** reverses a mistaken decision; **Reset run** clears saved state. Print styles provide a compact paper record.

## Important assumptions and limits

- Mod Sift does not inspect, enable, disable, delete, or repair any DCS file. It is a decision aid only.
- The procedure assumes DCS passes the same test with all listed mods disabled. If the clean baseline fails, mod isolation cannot establish that one listed mod is responsible.
- Each outcome must use the same launch path, mission, aircraft, and reproduction steps. Changing the test invalidates comparison.
- Binary isolation assumes one independently testable culprit. Dependency conflicts, load-order faults, and interactions between two otherwise clean mods may require grouping related mods on one line or testing combinations after isolation.
- Use a mod manager for changes and follow current official Eagle Dynamics cleanup/repair guidance. Root-folder modifications can be overwritten by updates; Saved Games mods behave differently.
- Antivirus quarantine, configuration faults, hardware, drivers, and DCS defects can resemble mod failures. A surviving candidate is evidence to confirm, not proof.

## Community signal (accessed 2026-08-21)

This tool responds to a recurring troubleshooting pattern rather than inventing aircraft data:

- In an r/hoggit discussion about DCS stopping at 44%, the reported community practice is to disable mods and re-enable them selectively to identify the problematic one: https://reddit.com/r/hoggit/comments/1ny93b6/dcs_not_loading_past_44/
- In an r/hoggit update-procedure discussion, users recommend trying DCS without mods first when problems appear and disabling root-folder mods before an update when managed through OvGME: https://reddit.com/r/hoggit/comments/1kg0ugz/update_procedure_for_sims/
- The recurring r/dcsworld weekly support thread advises crash-log inspection, removing all mods, and running a repair; it also distinguishes module deactivation problems that may involve antivirus quarantine: https://www.reddit.com/r/dcsworld/comments/1rotqc6/weekly_thread_20260310_questions_on_dcs_pcs.json
- A 2026 Eagle Dynamics forum crash thread repeats the baseline sequence: remove mods, run a repair, and test again: https://forum.dcs.world/topic/381287-dcs-does-not-start-anymore/
- Eagle Dynamics’ 2026 changelog shows continuing core and module updates, the conditions under which stale modifications can need renewed testing: https://forum.dcs.world/topic/384996-dcs-changelog-and-updates-2026/

## Technical notes

Everything is inline in `index.html`: semantic HTML, responsive CSS, and dependency-free JavaScript. It is designed for `file://` use and requires no build step or external runtime asset.
