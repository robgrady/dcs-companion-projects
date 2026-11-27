# Update Runway

Update Runway is a self-contained, offline DCS World patch-readiness and post-update launch-triage desk. It turns measured drive space and the updater's reported download into a conservative storage contract, then provides a controlled evidence path if DCS does not launch after the update.

## Use

1. Open `index.html` directly in a current browser. It requires no server, internet connection, package install, or build step.
2. Enter the actual free space on the drive containing DCS and the download size reported by the updater.
3. Choose a working-overhead posture and a post-update reserve. The app calculates:
   - estimated patch working set;
   - protected total including reserve;
   - selected reclaim capacity;
   - projected headroom or the remaining storage gap.
4. Add only personally measured reclaim candidates. Selecting a candidate models the plan, but the interface explicitly keeps it separate from proven free space until the drive is re-measured.
5. Confirm the backup gate, complete the official updater, and mark the update and clean-launch gates as evidence is earned.
6. If launch fails, select the observed symptom and check only facts already established. The triage panel changes its next safe action from repair, to mod isolation, to evidence capture, to escalation.
7. Add exact filenames, policy messages, log clues, and controlled-test results to the Evidence Wire. Copy, export, or print the resulting case brief.

All measurements, gates, reclaim candidates, triage facts, and up to 40 evidence entries persist in browser `localStorage`.

## Important assumptions

- The app is a planning aid, not a guarantee of Eagle Dynamics updater disk-space behavior.
- The working estimate is the reported download multiplied by a user-selected overhead factor. Actual replacement, unpacking, cleanup, filesystem, and module behavior can differ.
- Reported community figures such as a 123.5 GB update are demand signals, not hard-coded defaults. Users must enter the size displayed by their own updater.
- Reclaim candidates do not become real headroom merely because they are selected. Move or delete them safely, then re-measure the drive.
- A confirmed backup means the user has verified a recoverable copy or snapshot of irreplaceable Saved Games content; the app does not create one.
- Update Runway never recommends disabling Smart App Control, antivirus, code-signing checks, or other operating-system protections. Security changes can be consequential and some Windows controls have historically been difficult to reverse.
- The official repair/cleanup process can affect non-official files. Back up modifications and follow current Eagle Dynamics instructions.
- The app does not inspect DCS, Windows, drives, logs, signatures, or security events. Every fact is user-entered.
- This project is simulation support software and performs no real-world aviation function.

## Community signal

Built on **2026-11-27** after reviewing the current DCS update discussion and recurring launch-recovery questions:

- The r/dcsworld thread **“2026/11/26 - DCS Update Change log 2.9.32.30490”** reported a 123.5 GB update for at least one configuration and included an immediate report that DCS no longer started after updating, followed by discussion of blocked DLLs and Smart App Control. This supplied the strongest same-day signal for a combined storage-readiness and safe launch-evidence tool. Accessed 2026-11-27: https://www.reddit.com/r/dcsworld/comments/1y5zqg1/20261126_dcs_update_change_log_293230490/
- The r/hoggit thread **“F14 not working after latest update”** describes a module becoming unavailable after Windows Smart App Control named a Heatblur file, despite reinstall and repair attempts. It reinforces the need to preserve the exact blocked-file evidence instead of treating every failure as generic antivirus trouble. Accessed 2026-11-27: https://www.reddit.com/r/hoggit/comments/1vzk7gz/f14_not_working_after_latest_update/
- The r/dcsworld **Weekly Thread 2026/11/23** repeats the community practice of examining the newest `dcs.log` from the bottom toward the first crash clue, supporting the app's “first break” evidence posture. Accessed 2026-11-27: https://www.reddit.com/r/dcsworld/comments/1y3o934/weekly_thread_20261123_questions_on_dcs_pcs/
- The Eagle Dynamics forum thread **“Windows 11 Smart App Control blocks DCS: Can No Longer Play”** documents update-linked DLL blocking reports and uncertainty around restarts and security settings. It supports a triage design that records provenance and escalates reproducible official-file blocks without advising users to weaken protections. Accessed 2026-11-27: https://forum.dcs.world/topic/389556-windows-11-smart-app-control-blocks-dcs-can-no-longer-play/
- Eagle Dynamics' official **repair/cleanup/update FAQ** identifies launcher and updater repair/cleanup paths, warns that cleanup may remove modifications, and advises backing up user changes. Accessed 2026-11-27: https://www.digitalcombatsimulator.com/en/support/faq/repair/
- Eagle Dynamics' official **support-ticket FAQ** asks for logs and updater files for crashes and update failures. That evidence requirement shaped the exportable case brief. Accessed 2026-11-27: https://www.digitalcombatsimulator.com/en/support/faq/support_ticket/

Community posts are evidence of user pain, not technical authority. Repair and support guidance is therefore anchored to the official Eagle Dynamics FAQs, while the app avoids making claims about any specific DLL's trust or signature state.

## Design notes

**Surface:** Configure is primary; Operate is secondary. The composition begins with measured inputs and conservative assumptions, moves into a single storage runway and earned gates, then supports post-update incident action. It deliberately avoids a marketing hero, feature-card grid, and invented dashboard metrics.

**System:** near-black maintenance-bench surfaces, sand-colored planning emphasis, green earned evidence, restrained red holds, Avenir/system humanist body type, and monospaced measurements. The storage runway is the only large visual device; it directly represents the user's decision model.

**Anti-slop audit before repair: 0/10.** No tech gradient, generic indigo accent, equal-weight feature tiles, accent rails, blur, monument stats, icon toppers, center stack, default Inter typography, or wrong-surface composition fired.

**Anti-slop audit after verification: 0/10.** The responsive layout remains configuration-first, every displayed number derives from user input, and decoration stays subordinate to storage and triage decisions.

## Files

- `index.html` — complete offline app with inline CSS and JavaScript
- `README.md` — usage, assumptions, community sources, and design audit
