# ALE-47 Wire

**ALE-47 Wire** is a self-contained, offline countermeasure-program workbench for the DCS: F-14B(U). It turns the module’s newly programmable ALE-47 into a crew-readable mission contract: define all eight programs, compare their expendable cost against the loaded chaff/flare inventory, route broad threat conditions to programs, rehearse each sequence on a compressed timeline, and print or export a concise mission card.

Open `index.html` directly in any modern browser. No server, account, network connection, package install, or build step is required.

## How to use

1. Set the airframe bucket loadout in **Loadout contract**. Bucket chaff and flare must total 60 and each quantity must be a multiple of 10. Enable the LAU-138 option when the rails are part of the DCS loadout.
2. Select Programs 1–8 from the left rail. Give each program a mission-specific name and priority, then enter chaff and flare burst quantities, burst intervals, salvo quantities, and salvo intervals.
3. Review **Full runs** and the right-side **Program budget**. These show how many complete activations fit within the planned stock.
4. In **Threat routing**, assign general search/track/launch conditions to the desired program. This is a briefing worksheet; the actual automatic and semi-automatic threat mapping must be configured in DCS.
5. Use **Sequence simulator** to inspect the timing and concurrency of one complete selected-program activation.
6. Use **Print card** for a cockpit/kneeboard-friendly crew brief. **Export** saves the complete editable state as JSON; **Import** restores it later. The current state is also persisted automatically in browser `localStorage`.
7. Transcribe or verify the finished values in DCS Mission Editor → DTC → CMDS and confirm the actual countermeasure loadout on the DCS kneeboard before flight.

Keyboard conveniences: press `1`–`8` outside a form control to select a program; `Ctrl/Cmd+S` exports the program set.

## Important assumptions and limits

- This is a planning and rehearsal aid, not a direct DTC writer and not a tactical recommendation. It deliberately does not invent threat-specific effectiveness claims.
- The included program values are editable **training examples**, not authoritative operational settings. Match them to mission intelligence, server rules, the current DCS build, and your squadron’s procedures.
- Program cost is calculated as `burst quantity × salvo quantity` independently for chaff and flare. Sequence duration is the later of the chaff and flare channels: `(salvos − 1) × salvo interval + (burst quantity − 1) × burst interval`.
- Inventory math treats each programmed CH/FL command as one expendable release. The LAU-138 option adds 40 synchronized chaff releases to planning stock, following the current Heatblur manual’s description; DCS chooses the actual dispenser behavior.
- The current Heatblur manual states that the two airframe launchers total 60 cartridges, each section holds one cartridge type, and quantities are therefore loaded in multiples of 10. It also identifies eight programs: Programs 1–4 are available to DCDU manual/automatic/semi-automatic logic, Programs 5–7 map to RIO switches, Program 7 is Jester’s default, and Program 8 is the pilot DLC-switch program.
- Higher-priority-program interruption is represented only as a planning priority field; the simulator dry-runs a single program and does not emulate the aircraft’s complete threat-detection or priority arbitration logic.
- Browser clipboard permission can be restricted under `file://`; if so, **Copy** selects the card for a normal manual copy. Printing and JSON backup remain local.

## Why this project now

The July 22, 2026 F-14B(U) release created a strong current community and product signal around learning its new systems. Recent r/dcsworld posts tracked the content/release buildup and shared the release patch notes, while Heatblur’s release feedback thread documents continued active post-release learning and fixes. More specifically, Eagle Dynamics and Heatblur identify the ALE-47 as a major B(U) addition and confirm that it is programmable, mission-configurable, and integrated with the Mission Data Loader/DTC. Heatblur’s newly published manual exposes the exact program fields and control mapping, making a focused offline planning and rehearsal tool timely and supportable without guessing.

Sources reviewed on **2026-08-23**:

- r/dcsworld — “Everyone’s F-14 B(U) content - release date?” (release anticipation and demand signal): https://www.reddit.com/r/dcsworld/comments/1umn7fv/everyones_f14_bu_content_release_date/
- r/dcsworld — “2026/07/22 DCS Patch Notes - 2.9.28.26283” (community discussion of the release patch): https://www.reddit.com/r/dcsworld/comments/1v3isdu/20260722_dcs_patch_notes_292826283/
- Eagle Dynamics Forums — F-14B(U) release feedback thread (active post-release feedback and July 28 hotfix context): https://forum.dcs.world/topic/390381-f-14bu-release-feedback-thread/
- Eagle Dynamics Forums — F-14B(U) FAQ (scope, ownership, and feature context): https://forum.dcs.world/topic/388826-dcs-f-14bu-frequently-asked-questions/
- Eagle Dynamics product page — official July 22, 2026 release date; ALE-47, DTC, and Mission Data Loader features: https://www.digitalcombatsimulator.com/en/products/planes/f-14bu
- Heatblur F-14 manual — authoritative ALE-47 capacities, eight-program roles, controls, priority, bingo, program fields, and LAU-138 behavior: https://f14.manuals.heatblur.se/f14bu/systems/defensive_systems/countermeasures/ale_47.html
- Heatblur F-14 manual — DCS Mission Editor and DTC/CMDS integration: https://f14.manuals.heatblur.se/dcs/mission_editor.html

## Privacy and portability

All data stays in the browser unless you explicitly export a JSON file or print. The app uses no analytics, remote assets, fonts, CDNs, or network requests and works from `file://`.
