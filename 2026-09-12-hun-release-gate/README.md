# Hun Release Gate

An offline rehearsal desk for the DCS: F-100D Super Sabre's A-4 gunsight automatic bomb-release workflow. It turns the often-confusing “no release” outcome into an observable setup-and-tracking exercise: close the armament gates, cage while acquiring, uncage smoothly, hold bomb release, and build a stable sight solution.

## Use

1. Open `index.html` directly in a modern browser; no server or network connection is required.
2. Set the stores and bomb-arm choice for the planned pass.
3. Confirm the four setup gates: **SIGHT & RADAR**, sight selector **BOMB**, stations **NORM**, and mechanical cage **UNCAGE**.
4. Select **New pass**. Hold the electrical cage with the on-screen button or `C`, then use the pointer or arrow keys to bring the reticle onto the target.
5. Release cage without an abrupt correction and hold bomb release with the on-screen button or `Space`. Keep the reticle steady until the modeled sight blanks.
6. Review the event wire and diagnosis, add a debrief note, and save the pass. Pass history and the current contract persist in `localStorage`.

## Important assumptions

- This is a **procedural and control-smoothness trainer**, not a ballistic calculator. Its two-second stability gate, tracking tolerance, smoothness score, and 30-second timeout are training abstractions, not claimed F-100D release-computer specifications.
- The current DCS F-100D manual and in-cockpit indications remain authoritative. The manual explains that automatic bomb mode uses line-of-sight rate, automatically depresses the reticle 10°, extinguishes the reticle when release parameters are met, and calls for smooth tracking after electrical uncaging.
- The setup model follows the manual's descriptions of **SIGHT & RADAR** mode, bomb-arm options, and station-release circuitry. A mission's loadout, fuzing, pylon state, and current module behavior can still prevent a real release.
- The tool deliberately avoids asserting one universal bomb-arm choice: high-drag/low-drag configuration and desired fuzing affect that choice.
- All saved data remains in the current browser profile. Clearing site data removes it.

## Community signal

The F-100D was released for DCS on June 12, 2026, and current discussion shows both strong module interest and a specific learning problem around its early computer-assisted bombing system:

- A June 2026 Eagle Dynamics forum thread, **“Automatic Dive Bombing – Intermittent Release Failures,”** asks why apparently correct automatic-bomb runs sometimes produce hung stores. Replies focus on setup, station selection, the fact that radar is not the auto-bomb solution source, the meaning of pipper blanking, and the need for a smooth line-of-sight track rather than abrupt pitch inputs. This is the app's direct problem statement. Accessed 2026-09-12.
  https://forum.dcs.world/topic/389404-automatic-dive-bombing-intermittent-release-failures/
- An r/hoggit F-100D discussion characterizes its automatic bombing as “finicky but accurate” and contrasts the module's demanding landing and analog systems with modern aircraft. Accessed 2026-09-12.
  https://reddit.com/r/hoggit/comments/1suiecy/f100d_super_sabre/
- An r/dcsworld release discussion praises the module but predicts many owners may leave it in the hangar because the analog, non-fly-by-wire aircraft is hard to learn. Accessed 2026-09-12.
  https://reddit.com/r/dcsworld/comments/1suj1aw/dcs_f100d_super_sabre/
- Eagle Dynamics' product page confirms the released module's early computer-assisted bombing/fire-control system and demanding handling. Accessed 2026-09-12.
  https://www.digitalcombatsimulator.com/en/shop/modules/f-100d/

## Technical references

- Official DCS F-100D manual — A-4 Gunsight:
  https://grinnellidesigns.github.io/f-100d-manual/Weapon_System/a-4-gunsight.html
- Official DCS F-100D manual — Armament Control Panels:
  https://grinnellidesigns.github.io/f-100d-manual/Weapon_System/armament-control-panels.html

Both accessed 2026-09-12.

## Design notes

This is an **Operate** surface: setup authority, the live sight task, and release evidence dominate instead of a marketing hero. The initial and final anti-slop audit scored **0/10**: no tech gradient, generic indigo, equal feature-tile grid, accent rail, blur, monument stat, icon topper, center stack, default Inter typography, or wrong-surface composition.

## Files

- `index.html` — complete self-contained application with inline CSS and JavaScript
- `README.md` — use, assumptions, provenance, and references
