# Shrike Wire

Shrike Wire is a self-contained, offline F-4E AGM-45 attack-contract desk for DCS World. It separates three things that are easy to conflate under pressure: the intended radar emitter, the loaded frequency-specific seeker head, and the missile attack profile selected during arming. It then builds a pilot–WSO readback, checks six commitment gates, and gives a clear **COMMIT**, **HOLD**, or **ABORT** verdict.

## Use

1. Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.
2. Select the radar role you intend to suppress and the seeker head actually loaded.
3. Select the F-4E delivery mode and the missile's arming-menu attack profile. These are independent choices.
4. Close the six commitment gates only after verifying each condition in the mission.
5. Record the egress and crew note. Save locally, copy the readback, or print the compact contract.
6. Open **Seeker Table** for RF limits or **Field Notes** for the key conceptual separations.

The active plan and up to 12 saved contracts persist in browser `localStorage`. **Reset** clears the active contract but does not erase saved contracts; each saved row has its own delete control.

## Important assumptions and limits

- This is an F-4E planning and rehearsal aid, not a ballistic calculator and not a substitute for the current Heatblur manual.
- Seeker RF limits and DCS compatibility are transcribed from Heatblur's current F-4E manual. In its compatibility notation, parentheses mean the radar provides tone/needles and can be tracked; an unparenthesized radar can be tracked without those cockpit indications.
- The app deliberately does not invent a fixed launch range. Aircraft state, geometry, target elevation, the selected profile, and the in-cockpit WRCS/indexer cues govern the release.
- `WRCS AGM-45`, `WRCS DIRECT`, and `LABS LOFT` are cockpit delivery modes. `LOFT ATTACK` and `DIRECT ATTACK` are missile guidance profiles selected during arming. The cockpit delivery-mode knob does not change missile guidance logic.
- A radar shutdown can accomplish suppression even without a physical kill. Mission effects and egress survival matter more than a scoreboard event.
- DCS behavior and tables may change with module updates. Re-check the source manual after updates.

## Why this exists

A recent r/hoggit discussion asked how useful Shrikes are on the F-4E and A-4E-C. Replies repeatedly exposed the same practical failure modes: choosing the wrong frequency-specific seeker, attacking a search radar instead of the tracking radar, mixing up cockpit delivery mode with missile attack profile, expecting modern HARM-like behavior, and treating a miss as failure even when the emitter shut down. The tool turns those recurring points of confusion into explicit pre-commit gates rather than another long procedure card.

Community and technical signals reviewed on **2026-09-16**:

- r/hoggit, “looking to study SEAD for F4E & A4 mod... how good are AGM45 shrike on these dcs aircraft?” — current discussion of seeker selection, tracking-radar targeting, loft/direct limitations, and suppression-versus-destruction outcomes: https://www.reddit.com/r/hoggit/comments/1q7hk1a/looking_to_study_sead_for_f4e_a4_mod_how_good_are/
- Heatblur F-4E manual, “AGM-45 Shrike Anti-Radiation Missile” — current module-author reference for variants, delivery modes, guidance profiles, seeker RF limits, and DCS emitter compatibility: https://f4.manuals.heatblur.se/stores/air_to_ground/missiles/shrike.html
- Heatblur F-4E manual, “AGM-45 Missile” — concise cockpit tune-up and launch checklist: https://f4.manuals.heatblur.se/procedures/agm_45.html
- Eagle Dynamics forum, “AGM-45 Shrike Quick Guide by Klarsnow” — detailed explanation of the recurring mode/profile confusion and WRCS cues, later incorporated into the Heatblur manual: https://forum.dcs.world/topic/349673-agm-45-shrike-quick-guide-by-klarsnow-updated-june-5th-2024/

## Offline and privacy

All CSS, JavaScript, data, and documentation are included locally. The app makes no network requests and sends no telemetry. User-entered plans remain in the browser profile's local storage unless copied or printed.