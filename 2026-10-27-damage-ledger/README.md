# Damage Ledger

Damage Ledger is a self-contained, offline DCS World weapon-effect test desk. It turns subjective reports such as “this target sometimes absorbs the same attack” into a controlled test contract, a pass-by-pass evidence ledger, drift warnings, outcome distributions, and comparable saved test sets.

## Why this project

Recent DCS community discussion continues to mix three different questions: whether a weapon hit, whether the hit produced the expected simulated effect, and whether repeated tests actually held target state and attack conditions constant. A September 2026 r/dcsworld discussion about aircraft damage from AI fire is a direct example: replies compare apparently different outcomes, speculate about hit location and AI damage, and ask whether the behavior is reproducible. Eagle Dynamics also continues to change weapon and damage behavior in updates—for example, a September 2026 changelog increased HE fragmentation effectiveness against soft targets and updated several warhead values—so remembered results from an older build may not describe the current one.

Damage Ledger does not decide whether the simulator is right or wrong. It gives the pilot a disciplined way to build evidence before making that claim.

## Use

1. Open `index.html` directly in a modern browser. It requires no server, network, install, build step, or external library.
2. Define a test contract: aircraft, weapon, target, skill, aspect, firing range, speed, expected quantity, mission, control notes, and success criterion.
3. Lock the baseline. The run form remains unavailable until the required contract fields are complete and locked.
4. Restart or clone the same test condition, fly a pass, and log quantity fired, estimated hits when available, outcome, control drift, mission restart state, elapsed pass time, and observations.
5. Record misses, aborts, and no-effect runs. The assessment uses only runs marked **Baseline matched**, while retaining drifted runs in the ledger.
6. After at least three controlled runs, inspect mission-effect rate, quantity-fired variation, outcome distribution, target-reset warnings, and the app’s deliberately cautious assessment.
7. Save a snapshot, change one variable, run another controlled set, and compare mission-effect rate and median quantity fired. The comparison is association, not proof of causation.
8. Print the report, export raw runs as CSV, or back up and restore the complete ledger as JSON.

Useful state persists in browser `localStorage`.

## Important assumptions

- This is a simulation companion only, not a real-world weapons tool.
- The app does not connect to DCS and cannot inspect telemetry, track files, logs, hit location, armor, penetration, target health, AI state, fragmentation, splash damage, or the installed DCS version.
- “Estimated hits” are a human observation and may be wrong. If hits are not known, delivery accuracy and weapon effect cannot be separated using this ledger alone.
- **Mission kill** is a user judgment. It can include crew abandonment or loss of combat function without the DCS object being destroyed.
- Only runs marked **Baseline matched** contribute to the assessment. This is based on the user’s assertion; the app cannot verify that conditions really matched.
- A mission restart or fresh target clone is important because prior damage may contaminate a later pass.
- Three controlled runs are a minimum prompt, not statistical proof. More runs and tighter controls improve confidence.
- A changed outcome after a DCS update does not by itself prove a regression. Preserve the DCS version, mission, track, logs, and exact reproduction steps for a useful report.
- Snapshot comparisons should change one variable at a time. The app reports association only and cannot establish causation.
- Built-in aircraft, weapon, and target examples are intentionally absent so the tool does not embed stale simulator values or imply unsupported expectations.

## Community and official signals

Accessed October 27, 2026:

- Reddit / r/dcsworld — “How the hell did a gunner kill the pilot, but the plane was perfectly fine?” (September 26, 2026). The thread compares apparently inconsistent aircraft/AI gun damage outcomes and discusses hit location, AI damage behavior, and reproducibility: https://www.reddit.com/r/dcsworld/comments/1nuyz96/how_the_hell_did_a_gunner_kill_the_pilot_but_the/
- Reddit / r/hoggit — “Why DCS AI Damage Models Feel So Inconsistent” (community discussion surfaced in current search results). The recurring signal is player difficulty separating delivery, hit registration, component damage, and AI behavior without a controlled test record: https://www.reddit.com/r/hoggit/search/?q=AI%20damage%20model&restrict_sr=1&sort=new
- Eagle Dynamics — DCS 2.9.21.19885 changelog (September 30, 2026). It records changes including increased HE fragmentation effectiveness against soft targets and warhead-value adjustments, reinforcing the need to note build context when comparing remembered results: https://www.digitalcombatsimulator.com/en/news/changelog/stable/2.9.21.19885/
- Eagle Dynamics Forum — DCS weapons and AI damage-model discussions. Forum search results show the issue spans weapon effects, target damage, AI behavior, and requests for reproducible evidence rather than isolated anecdotes: https://forum.dcs.world/search/?q=weapon%20AI%20damage%20model&quick=1

## Files

- `index.html` — complete offline app with inline CSS and JavaScript
- `README.md` — purpose, workflow, assumptions, and source context
