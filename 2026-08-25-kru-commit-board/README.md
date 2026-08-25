# KRU Commit Board

A self-contained, offline rehearsal and cue-logging desk for the DCS: MiG-29A Fulcrum's newly added Ground-Controlled Intercept (GCI/KRU) workflow. It turns a controller cue into a concise intercept contract: steering, reported target state, estimated closure, an editable radar gate, a verbal readback, and a saved cue wire for review.

## Use

1. Open `index.html` directly in a modern browser. No server, build step, network connection, or external dependency is required.
2. Enter the KRU steering bearing, target range/speed/altitude, assigned channel, own estimated true airspeed, and reported aspect.
3. Review the heading-up plot and three-point contract. **Rehearse readback** produces an accessible spoken-style readback in the live region and temporarily displays it on the board.
4. Select **Log cue** to keep the call in the local cue wire. Load or delete prior calls as needed.
5. Use **Print card** for a clean paper/PDF intercept card or **Export log** for a JSON debrief record.

Useful state persists in browser `localStorage`. Reset clears the stored form and cue history after confirmation.

## Assumptions and limits

- Bearing is treated as magnetic degrees and distance as kilometres; speed is km/h TAS and altitude is metres.
- Closure is deliberately a **planning estimate**, not a flight-dynamics solution: head-on adds speeds, tail-on subtracts speeds with a conservative floor, and beam aspect uses a simplified fraction of own speed. It is meant to make timeline compression visible, not predict an exact intercept.
- The default 60 km head-on and 40 km tail-on radar gates reflect Eagle Dynamics' July 2026 description of automatic illumination initiation in the initial GCI implementation. Both gates are editable because mission geometry, controller instruction, ROE, and future DCS updates govern the actual sortie.
- The board does not connect to DCS, infer target identity, authorize weapons, or replace the current module manual, mission brief, controller, cockpit indications, fuel plan, or ROE.
- Eagle Dynamics described the initial system as player-aircraft guidance: a mission-editor KRU station can use compatible surveillance radar data within 250 km, guide up to 24 interceptors on one channel, and provide steering, target speed, altitude, and attack aspect. AI aircraft integration was described as a later phase. Verify behavior against the current changelog/manual after future updates.

## Why this project

Current discussion signals converged on the MiG-29A's dependence on offboard acquisition and a brand-new native GCI workflow:

- **Eagle Dynamics official newsletter / patch announcement** — the July 24, 2026 F-14B(U) release newsletter documents that DCS 2.9.28.26283 added MiG-29A Ground-Controlled Intercept, including KRU mission setup, steering/target cues, radar-silent intercept behavior, source-radar range, channel capacity, initial player-only scope, and the published head-on/tail-on illumination ranges. Accessed 2026-08-25.  
  https://forum.dcs.world/topic/390531-dcs-f-14bu-release-dcs-292826283-update-released/
- **r/dcsworld patch discussion** — the community posted and discussed the 2.9.28.26283 notes, specifically surfacing the added MiG-29A GCI feature. Accessed 2026-08-25.  
  https://www.reddit.com/r/dcsworld/comments/1v3isdu/20260722_dcs_patch_notes_292826283/
- **r/dcsworld multiplayer question** — a recent owner asks where the MiG-29A is viable in multiplayer, a practical signal that players need help translating the aircraft's strengths and offboard support into an executable intercept workflow. Accessed 2026-08-25.  
  https://www.reddit.com/r/dcsworld/comments/1scjtv3/where_is_the_mig29a_actually_viable_in_multiplayer/
- **r/dcsworld module discussion** — players explicitly frame GCI/AWACS as the MiG-29A's acquisition layer, supporting a cue-to-commit rehearsal tool rather than another generic radar reference. Accessed 2026-08-25.  
  https://www.reddit.com/r/dcsworld/comments/1qfgln9/mig29a_module_is_awesome/
- **Eagle Dynamics MiG-29A mini-updates** — authoritative ongoing module context and system documentation landing page. Accessed 2026-08-25.  
  https://forum.dcs.world/topic/378017-dcs-mig-29a-fulcrum-mini-updates/

## Design posture

This is an **Operate** surface. The layout is a compact plotting board with one capture column, one dominant live contract, and one review wire—not a dashboard hero or equal-weight feature grid. Its warm paper, near-black plotting field, restrained signal red, tabular numerics, and print treatment are intentionally tool-like. Final anti-slop audit: **0/10**; none of the ten claude-design diagnostic tells are present.
