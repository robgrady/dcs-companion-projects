# VDIG Scan

An offline F-14B(U) VDIG-R HUD interpretation trainer for DCS World. It turns the dense modernized pilot display into an interactive scan: choose a tactical format, inspect representative cues, complete a five-second scan contract, and practice recognition questions. Progress is stored locally in the browser.

## Use

1. Open `index.html` directly in a modern browser; no server, network connection, or build step is required.
2. Choose a format in the left rail: TWS/AIM-54, STT/AIM-7, STT/AIM-9, gun director, or landing/AWL.
3. Click green cues in the HUD schematic for an operational explanation.
4. Complete the five scan gates at right, then answer the recognition drills.
5. Keyboard shortcuts: `1`–`5` select formats, `N` advances the drill, and `R` clears the current format's scan gates.

## Assumptions and boundaries

- This is a DCS reference and recognition aid, not real-world flight instruction.
- The HUD is an original schematic optimized for learning. Cue placement is representative rather than a pixel-exact cockpit reproduction.
- Facts are limited to behavior documented in Heatblur's current F-14B(U) manual: VDIG-R common symbology, A/A formats, launch-range cues, target-designate behavior, pilot track selection, and landing/AWL cues.
- The application does not calculate weapon performance or promise a valid shot. It trains interpretation of displayed cues.
- Browser state is saved under the `vdigScanState` localStorage key. Reset Progress removes the app's score and scan-gate state only.

## Why this project

The F-14B(U) released on 2026-07-22 with a modernized VDIG-R HUD, PTID, JDAM, EGI/CDNU, DFCS, ALE-47, and other late-service systems. Current community activity shows sustained interest in learning the new displays rather than merely watching the release: an r/dcsworld VDIG-R systems discussion appeared during the launch buildup; a large r/hoggit thread focused on the HUD's new track, RWR, navigation, and targeting information; and Heatblur's release-feedback thread accumulated 172 replies through late August. Older r/hoggit questions about interpreting the original Tomcat VDI/HUD reinforce the recurring display-literacy problem. VDIG Scan answers that signal with a mode-specific, interactive recognition tool rather than another startup checklist.

## Sources (accessed 2026-09-09)

### Community signal

- r/dcsworld — “DCS: F-14B(U) - New Systems - VDIG-R”: https://www.reddit.com/r/dcsworld/comments/1uj4col/dcs_f14bu_new_systems_vdigr/
- r/hoggit — “F-14 Bros, We are so back”: https://www.reddit.com/r/hoggit/comments/1qop19l/f14_bros_we_are_so_back/
- Eagle Dynamics Forums — “F-14B(U) Release Feedback Thread”: https://forum.dcs.world/topic/390381-f-14bu-release-feedback-thread/
- r/hoggit — “Help with F-14 VDI and HUD”: https://www.reddit.com/r/hoggit/comments/hj4qr8/help_with_f14_vdi_and_hud/

### Fact verification

- Eagle Dynamics — DCS: F-14B(U) product page and release date: https://www.digitalcombatsimulator.com/en/products/planes/f-14bu
- Heatblur manual — VDIG-R system and common symbology: https://f14.manuals.heatblur.se/f14bu/systems/vdig_r/vertical_display_indicator_group_replacement.html
- Heatblur manual — VDIG-R A/A formats: https://f14.manuals.heatblur.se/f14bu/weapons/air_to_air/vdigr_aa.html

## Privacy

No analytics, network calls, external assets, or third-party runtime dependencies are used. Everything remains in the local browser profile.
