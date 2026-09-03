# TARPS Runboard

TARPS Runboard is a self-contained, offline F-14 reconnaissance-pass companion for DCS World. It turns a planned groundspeed, lead-in distance, and recording-leg distance into a live run timeline; enforces a five-item crew ready gate; records MARK events; keeps recent sorties in local storage; exports a JSON run log; and prints a compact mission/debrief card.

## Use

1. Open `index.html` directly in a modern browser. No server, install, network connection, or build step is required.
2. Enter the flight/target label, sensor plan, groundspeed, photo-leg length, lead-in distance, altitude, and crew notes.
3. Complete all five readiness checks. The run control remains inhibited until every check is complete and the numeric setup is valid.
4. Select **Start lead-in**. The board counts down to the planned photo line.
5. At the line, hold the aircraft's Store Release control (or command TARPS through Jester), then select **Begin recording** in the board.
6. Select **MARK frame** only when you want an image filename flagged for quicker post-flight review. Stop the recording after the collection leg, finish the DCS flight, and review the recovered images.
7. Use **Export log** for a JSON handoff or **Print card** for a paper/PDF record. Setup, ready checks, and up to eight completed passes persist in browser local storage.

Keyboard shortcuts outside form fields: `Space` advances the run phase and `M` records a MARK while filming.

## Important assumptions and limits

- Timing is a planning aid: `seconds = nautical miles ÷ groundspeed in knots × 3600`. It uses entered groundspeed as constant and does not read telemetry from DCS.
- This is not a substitute for the Heatblur manual, mission brief, aircraft indications, crew judgment, or threat procedures.
- Sensor labels follow Heatblur's 26 August 2026 patch notes: KS-87 vertical/FWD and KA-99 panoramic modes. The current official TARPS manual page still contains pre-patch limitation text, so the app deliberately avoids unverified camera footprint, interval, and exposure calculations.
- Heatblur clarified in the patch feedback thread that **MARK does not enable automatic unit annotation**. MARK adds a suffix to filenames for later inspection; automated unit marking is separate and, at that time, not optional. Image availability is post-flight.
- The patch feedback also identifies the pilot/Jester route as **A/G → Utilities → TARPS**, with MARK appearing after filming begins. Controls and behavior may change in later patches.
- All data stays in the browser except when the user explicitly exports a JSON file.

## Community signal — accessed 2026-09-03

- [Heatblur / Eagle Dynamics forum: F-14B(U) patch feedback, 26 August 2026](https://forum.dcs.world/topic/391643-feedback-thread-f-14bu-patch-aug-26th-2026/) — announces the performance pass and expanded TARPS implementation: KS-87 FWD mode, KA-99, revised controls, pilot Store Release recording, Jester submenu, and automatic image analysis. Replies immediately ask for a step-by-step walkthrough, ask where the Jester TARPS menu lives, and confuse MARK with automatic annotation; Heatblur clarifies the behavior in-thread.
- [r/hoggit: “F-14 Bros, We are so back”](https://www.reddit.com/r/hoggit/comments/1qop19l/f14_bros_we_are_so_back/) — strong F-14B(U) interest and recurring concern about operating complex back-seat sensors from the pilot seat when time or scheduling prevents flying with a human RIO.
- [Heatblur F-14 manual: TARPS](https://f14.manuals.heatblur.se/f14ab/systems/tarps.html) — confirms pod location and sensor roles, but its implementation-status paragraph lagged the 26 August patch when accessed; this mismatch reinforced the need for a narrowly scoped post-patch run aid.
- [Heatblur F-14B(U) manual: Jester overview](https://f14.manuals.heatblur.se/f14bu/jester_iceman/overview.html) — confirms the context-driven pilot/Jester interaction model in the B(U).

## Design and accessibility

This is an **Operate** surface: the live run, readiness state, and action controls receive visual priority. The app uses semantic controls, visible keyboard focus, 44-pixel minimum targets, responsive layouts, reduced-motion support, high-contrast status cues, and print styles. It has no external runtime dependencies and works from `file://`.
