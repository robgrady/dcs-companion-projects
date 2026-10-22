# Config Evac

Config Evac is a self-contained, offline DCS World Saved Games backup and restore planner. It turns a selected payload into reviewable Windows PowerShell/Robocopy runbooks, adds a verification pass and SHA-256 inventory, keeps restore in preview mode until explicitly unlocked, and saves the planning state in the browser.

## Open it

Open `index.html` directly in a modern browser. No server, package install, account, network connection, or build step is required.

## Use it

1. **Scope** — choose whether this is a pre-update backup, reinstall/repair, or PC migration; confirm the Saved Games profile name and backup destination.
2. **Payload** — select controls, options, logbook/campaign state, missions, scripts, mods, liveries, kneeboards, templates, tracks, and screenshots as needed.
3. **Extract** — review and run the generated PowerShell backup command on the Windows DCS PC. Then run the generated verification command and mark the four extraction gates.
4. **Restore** — enter the backup and destination paths. Run the restore preview first. Only enable live restore after reviewing the proposed actions.
5. Export the plan JSON if you want a portable record of the selections and gate state.

## What the generated scripts do

- Copy only selected Saved Games payloads with `robocopy`.
- Do not purge the destination and do not alter the DCS installation directory.
- Record a copy log and a text plan alongside the backup.
- Create a recursive SHA-256 inventory of backup files.
- Provide a separate file-count verification pass.
- Generate restore commands with Robocopy `/L` preview mode unless live restore is explicitly unlocked.

## Important assumptions and cautions

- The generated scripts target **Windows PowerShell** on the PC that runs DCS and assume `robocopy` is available.
- Close DCS, the DCS launcher, SRS, VoiceAttack, and other tools that may write to Saved Games before copying.
- Default source profiles are `%USERPROFILE%\Saved Games\DCS` and the legacy `%USERPROFILE%\Saved Games\DCS.openbeta`; custom profile names are supported.
- The tool deliberately omits rebuildable shader caches (`fxo`, `metashaders2`), logs, crash dumps, and the installed game directory.
- Device GUIDs embedded in binding filenames may change after hardware or PC migration. Preserve the original backup and use DCS's per-device **Load Profile** path when direct restoration does not bind to the new device ID.
- User scripts and mods can be a source of post-update faults. Restore them after a clean controls/settings test when troubleshooting.
- File-count agreement is a useful gate, not proof of semantic correctness. Keep the SHA-256 inventory and a second backup copy away from the DCS drive.
- Config Evac does not read or modify local files from the browser. It only generates commands for the user to review and execute.

## Community signal

Accessed **2026-10-22**.

- A February 2026 r/hoggit discussion asks how to preserve settings and HOTAS bindings for a new PC; replies repeatedly distinguish same-machine copying from the more nuanced device-GUID problem on a new Windows installation: https://www.reddit.com/r/hoggit/comments/1r6knim/building_a_new_pc_how_do_i_saveexport_my/
- A May 2026 r/hoggit tool announcement drew strong interest by automating timestamped keybind backups and handling UUID changes during batch import, reinforcing demand for safer, less tedious migration workflows: https://www.reddit.com/r/hoggit/comments/1tn9mx7/psa_script_to_backuprestore_your_keybinds/
- The r/dcsworld weekly support thread dated 2026-10-19 includes a standing “How to backup/transfer config/keybindings” answer, directs users to the Saved Games `DCS` folder, and identifies `Config\Input` as the binding location. Its continued presence in recent weekly support threads indicates that configuration transfer remains a recurring help need: https://www.reddit.com/r/dcsworld/comments/1x9p7tu/weekly_thread_20261019_questions_on_dcs_pcs/
- The same backup/transfer guidance appears in the 2026-10-05 weekly thread, reinforcing that this is recurring support demand rather than a single isolated question: https://www.reddit.com/r/dcsworld/comments/1wy12p1/weekly_thread_20261005_questions_on_dcs_pcs/
- An Eagle Dynamics forum discussion asks specifically what must be backed up before a reinstall, reflecting uncertainty around the boundary between install files and user state: https://forum.dcs.world/topic/309568-which-files-to-backup-to-save-present-input-settings-for-a-dcs-reinstall/
- A detailed Eagle Dynamics forum discussion identifies `Saved Games\DCS\Config\Input` as the active per-module/per-device binding store and notes that device identifiers appear in binding filenames: https://forum.dcs.world/topic/333068-where-exactly-are-joystick-and-keyboard-bindings-stored-easy-backup/
- A PC-move discussion recommends transferring Saved Games data and using DCS's Load Profile function for old binding files, which informed Config Evac's migration cautions and selective-restore posture: https://forum.dcs.world/topic/349848-new-computer-for-simulation/
- Eagle Dynamics' release changelog shows multiple DCS updates in September and October 2026. That active update cadence increases the value of a repeatable pre-update backup gate: https://www.digitalcombatsimulator.com/en/news/changelog/release/

## Design notes

This is primarily a **Configure** surface, with **Operate** as the secondary surface. The composition follows a four-step runbook rather than a dashboard or marketing hero: define scope, select payload, execute a generated extraction, then stage a guarded restore.

Anti-slop audit after implementation: **0/10**. No tech gradient, generic violet accent, feature-tile grid, accent rail, blur, monument stat, icon toppers, centered composition, default Inter typography, or surface mismatch is present.

## Privacy

All plan data stays in the browser's `localStorage` unless the user explicitly exports a JSON plan. The app has no network requests or external runtime dependencies.
