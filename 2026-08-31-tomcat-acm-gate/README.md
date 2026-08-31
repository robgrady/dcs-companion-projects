# Tomcat ACM Gate

An offline F-14B(U) cockpit-side rehearsal desk for the release-era PAL/VSL prerequisite trap. It makes the pilot choose an ACM radar mode, set A/A and ACM-cover state, then test the command gate and practice short fault calls. The app is self-contained, runs directly from `file://`, and saves the last station configuration plus drill score in `localStorage`.

## Use

1. Open `index.html` in a modern browser.
2. Select PLM, PAL, VSL HI, or VSL LO.
3. Set the simulated A/A mode and ACM cover, then choose **Test command** (or press Enter outside a button).
4. Follow the corrective path if the gate is blocked.
5. Use **Fault-call drill** to rehearse the first corrective action; press **N** outside a button for the next call.

## Important assumptions and limits

- This is a procedural rehearsal aid, not a live interface to DCS and not a replacement for the current Heatblur manual.
- It intentionally teaches only the documented pilot control gates: in A/A with the ACM cover raised, Target Designate forward selects PAL, up selects VSL HI, and down selects VSL LO; PLM remains available with the cover down.
- It does not simulate radar search volumes, detection performance, target geometry, lock quality, failures, or RIO/Jester behavior.
- DCS modules change. Re-check the linked manual and patch notes after updates.

## Community signal and sources

The F-14B(U) released on July 22, 2026. In the immediate release feedback thread, a pilot reported that PAL and VSL would not work; Heatblur subject-matter expert Victory205 explained that the B(U) requires the ACM cover raised for PAL and VSL while PLM still works with it down. The same thread contains adjacent release friction around new binds, steering indications, and Jester behavior, making a narrow prerequisite/fault-call trainer more useful than another general checklist.

Accessed 2026-08-31:

- Eagle Dynamics Forums — **F-14B(U) Release Feedback Thread** (release confirmation, pilot PAL/VSL report, authoritative ACM-cover correction, July 28 hotfix notes): https://forum.dcs.world/topic/390381-f-14bu-release-feedback-thread/
- Heatblur official manual — **F-14B(U) Left Side Console** (A/A + raised-cover Target Designate mappings for PAL and VSL): https://f14.manuals.heatblur.se/f14bu/cockpit/pilot/left_console.html
- Reddit r/hoggit — **F-14 Bros, We are so back** (community attention around the B(U), avionics, Jester/TGP workflow, and new interactive documentation): https://reddit.com/r/hoggit/comments/1qop19l/f14_bros_we_are_so_back
- Eagle Dynamics Forums — **DCS: F-14B(U) Release | DCS 2.9.28.26283 Update Released** (official release/update announcement): https://forum.dcs.world/topic/390531-dcs-f-14bu-release-dcs-292826283-update-released/

## Design notes

This is an **Operate** surface: selection state, prerequisite switches, command readiness, and the corrective path lead the composition. The visual system uses near-black cockpit panels, amber control emphasis, green scope readouts, squared controls, and intentionally condensed display typography. Anti-slop audit after implementation: **0/10** — no tech gradient, generic indigo, feature tiles, accent rails, blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch.
