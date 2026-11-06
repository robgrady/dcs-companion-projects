# Track Witness

Track Witness is a self-contained, offline DCS World replay-divergence desk. It helps a pilot, mission author, tester, or video creator define observable checkpoints, timestamp them during the original sortie and replay pass, then identify the first continuity break and quantify timing drift.

## Use

1. Open `index.html` directly in a browser. No server, installation, network connection, or build step is required.
2. Name the case and record the DCS build, aircraft/module, track or mission name, environment, and test conditions.
3. Edit the supplied checkpoints or add events that are externally observable and unambiguous.
4. In **Original sortie**, start the stopwatch at a repeatable reference and press **M** at each event.
5. Switch to **Replay pass**, zero the stopwatch at the same reference, and mark the same events.
6. Classify each checkpoint as **Match**, **Diverged**, or **Not observed**. The diagnosis panel identifies the first break, mean timing drift, comparison coverage, and a suggested disposition.
7. Copy a plain-text report, export/import a JSON case file, or print the evidence sheet.

Keyboard controls: **Space** starts or pauses, **M** marks the next checkpoint, and **R** zeros the timer. Shortcuts are disabled while typing in a field.

## Assumptions and limits

- Track Witness does not parse `.trk` files or repair replay behavior. It creates repeatable human-observed evidence around a DCS track.
- Timing begins from a user-selected repeatable reference, not necessarily mission start.
- A timing match does not prove every simulation state matches; checkpoint quality matters.
- Use the same DCS build, mission, control profile, and playback behavior for both passes. Avoid taking control during replay.
- Data remains in browser `localStorage` unless exported. Clearing site data clears the saved case.
- The default DCS build shown is the stable build listed by Eagle Dynamics when this project was created; users should replace it when testing another build.

## Community signal

This project responds to a persistent, current need for compact replay evidence rather than another general checklist or mission planner:

- An October 6, 2026 r/hoggit changelog discussion celebrated a replay-desync fix while linking an acknowledged Eagle Dynamics report about AI diverging during even short single-player replays. The same discussion shows how update-specific replay behavior remains something users actively verify. Accessed 2026-11-06: https://www.reddit.com/r/hoggit/comments/1wzd0s8/20261006_dcs_293028738_change_log/
- The linked Eagle Dynamics forum report documents AI replay divergence in short, controlled single-player tests across versions after DCS 2.9.13.68180. Accessed 2026-11-06: https://forum.dcs.world/topic/376666-ai-desyncs-in-short-sp-replays-all-dcs-versions-after-291368180/
- A March 27, 2026 r/hoggit thread asks whether track files are usable in 2026 and describes replays that open but fail to reproduce the sortie, including discussion of F-4/Jester-related replay limitations. Accessed 2026-11-06: https://www.reddit.com/r/hoggit/comments/1s527yi/track_files_and_multiplayer_servers_in_2026/
- A broader Eagle Dynamics replay thread records content-creator frustration with AI behavior differing between live flight and replay. Accessed 2026-11-06: https://forum.dcs.world/topic/379485-please-fix-the-replay-system/
- Eagle Dynamics' update service listed DCS stable version `2.9.31.29434` on the access date. Accessed 2026-11-06: https://updates.digitalcombatsimulator.com/

## Design posture

Track Witness is an **Operate** surface: the timer, next checkpoint, phase, and first divergence carry the hierarchy. It deliberately avoids a marketing hero, decorative statistics, generic feature tiles, gradients, blur, and icon-topper cards. The restrained cockpit-neutral palette uses amber only for active controls and scan priority.

## Privacy

The app is fully offline. It sends no telemetry and loads no external runtime assets.
