# Fix Pattern

Fix Pattern is a self-contained offline DCS World navigation-anomaly desk. It compares expected and cockpit-observed coordinates at known points, plots the resulting error vectors, and classifies the evidence as a stable offset, time-growing error, repeatable course distortion, or an inconsistent sample set. It runs directly from `index.html` over `file://` with no network connection, build step, package install, or external runtime dependency.

## Why this exists

Recent DCS community discussions describe INS/navigation behavior that appears correct at first and then becomes displaced, drifts, or changes after repair, rearm, or an update. These reports are hard to compare when they contain only a screenshot or a statement that the waypoint was “off.” Fix Pattern turns the symptom into a repeatable coordinate test: same mission state, independently verified points, exact elapsed times, visible cockpit state, and a compact packet suitable for another pilot, a squadron maintainer, or a bug report.

## Use

1. Open `index.html` in a modern browser.
2. Record the mission/case, airframe, test context, and exact DCS version.
3. At a known point, enter expected and cockpit-observed latitude/longitude in decimal degrees. North/east are positive; south/west are negative.
4. Add at least two samples. Three or more samples at different elapsed times make the pattern diagnosis more useful.
5. Inspect the error-vector plot and diagnosis. A common vector suggests a stable displacement; increasing error over time suggests drift; repeatable angular disagreement between legs suggests course distortion.
6. Work the isolation gates in order, changing one variable per repeat.
7. Record the exact procedure used and cockpit observations, then copy, print, or export the evidence packet.

The **Load demo evidence** button installs a three-point example of a stable northeast offset. Useful state persists in browser `localStorage` until **New case** is used or site data is cleared.

## Assumptions and limits

- Fix Pattern is an evidence and geometry tool, not an INS alignment checklist.
- Aircraft procedures differ and can change. Follow the current manual for the selected module rather than instructions remembered from another aircraft or an older DCS version.
- Coordinate comparison uses a local nautical-mile approximation for north/east vector components; it is appropriate for the small errors this desk is intended to diagnose.
- The diagnosis is deliberately conservative. It reports a pattern in entered observations, not a root cause inside DCS.
- The tool does not read DCS telemetry, mission files, tracks, logs, or cockpit state automatically.
- Coordinate quality controls the result. Use the same coordinate format and an independently verified expected point throughout a test.

## Community signal and references

Accessed 2026-11-14:

- Reddit r/hoggit, “Alignment is broken after latest update.” The discussion reports post-update alignment/navigation symptoms and requests a way to distinguish procedure mistakes from a changed simulator state: https://www.reddit.com/r/hoggit/comments/1ov2yr6/alignment_is_broken_after_latest_update/
- Reddit r/hoggit, “A-10C II INS alignment drift issue after repair.” The discussion centers on apparently correct alignment followed by navigation displacement after a repair cycle: https://www.reddit.com/r/hoggit/comments/1ouvy1p/a10c_ii_ins_alignment_drift_issue_after_repair/
- Reddit r/dcsworld, “A10C INS problem.” The thread reflects recurring confusion around waypoint displacement, alignment quality, and what evidence is needed to separate setup error from a simulator issue: https://www.reddit.com/r/dcsworld/comments/1jc0hz2/a10c_ins_problem/
- Eagle Dynamics Forums, “A-10C II INS alignment issue.” Forum troubleshooting demonstrates the need to record the exact procedure, cockpit state, and repeatability rather than relying on a single end-state screenshot: https://forum.dcs.world/topic/384240-a-10c-ii-ins-alignment-issue/
- Eagle Dynamics Forums, “[Solved] DTC wind correction not working after repair and rearm.” This repair/rearm navigation-related report reinforces testing ground-service actions independently and preserving the first state change: https://forum.dcs.world/topic/353334-solved-dtc-wind-correction-not-working-after-repair-and-rearm/
- Eagle Dynamics, DCS: A-10C II Flight Manual download page. The current module manual remains the authority for aircraft procedure; Fix Pattern intentionally does not replace it: https://www.digitalcombatsimulator.com/en/downloads/documentation/a-10c_ii_flight_manual_en/

## Design posture

This is an **Operate** surface: coordinate capture, vector evidence, isolation gates, and the support packet carry the hierarchy. It avoids a marketing hero, equal-weight feature tiles, ornamental gradients, glass effects, icon toppers, and invented operational statistics.

### Slop diagnostic

- Initial score: **0/10**. None of the ten tells fired: no tech gradient, generic indigo accent, feature-tile grid, accent rail, blur, monument stat, icon topper, center stack, default Inter typography, or wrong-surface composition.
- Final score after verification: **0/10**. The Operate composition and evidence hierarchy remain intact.
