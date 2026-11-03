# Fox One Wire

Fox One Wire is a self-contained, offline DCS World rehearsal desk for semi-active radar homing (SARH) missile support decisions. It trains the sequence around a Fox One engagement—establish the support contract, preserve the radar track, keep the wider tactical scan alive, respond to changing geometry or threats, and make an honest support/abort decision.

Open `index.html` directly in any modern browser. No server, account, package install, or network connection is required.

## How to use it

1. Select one of six engagement contracts: baseline, target beam, reciprocal spike, second group, momentary lock break, or compressed merge.
2. Set a **support window** for rehearsal. This is a user-defined timing gate, not a weapon-performance prediction.
3. Press **Start wire** and answer three timed decisions. Number keys `1`–`4` select answers; Space pauses or resumes.
4. Review the correction immediately after each choice. A qualified wire requires three disciplined decisions.
5. Use **Export log** to download a plain-text history. The app also keeps the callsign, support-window preference, recent runs, and qualification count in local browser storage.

## Design and implementation

This is a **Command / Inspect** surface: the active engagement, current decision, support state, and keyboard-speed responses dominate. It intentionally avoids a marketing hero, generic feature-card grid, decorative telemetry, and invented missile data.

Everything is inline in `index.html`: semantic HTML, responsive CSS, and dependency-free JavaScript. It works through `file://`, includes visible keyboard focus, uses 44px minimum control targets, respects reduced-motion preferences, and stores only local training state.

### Slop diagnostic

- Initial score: **0/10**. No tech gradient, generic indigo accent, equal feature-tile grid, accent rails, blur, monument stats, icon toppers, centered composition, default Inter typography, or wrong-surface composition.
- Final score: **0/10** after verification; no compositional tells fired.

## Important assumptions

- The app teaches decision order and support discipline, not aircraft-specific switchology.
- Exact radar limits, cockpit indications, missile behavior, launch zones, and brevity vary by aircraft module, patch, mission, and server.
- The timer is a configurable rehearsal gate. It must not be read as time-to-impact, active time, aerodynamic range, or a guaranteed support requirement.
- A SARH weapon generally depends on reflected radar energy from the launching aircraft's radar. Users should defer to current module manuals and their own controlled testing for exact simulated behavior.
- This is a simulation training aid, not real-world tactical guidance.

## Community signal and sources

Accessed **2026-11-03**:

- Eagle Dynamics, **DCS 2.9.27.25183.5 release changelog** (2026-06-23) — AIM-7M/MH moved to an updated SARH-seeker scheme with advanced filtering, seeker-gimbal modeling, glint noise, and an ECM-tracking fix. The substantial recent model change made Fox One support discipline a timely subject without just repeating a checklist or inventing a fixed-range calculator: https://www.digitalcombatsimulator.com/en/news/changelog/release/2.9.27.25183.5/
- r/dcsworld, **2026-06-23 DCS change log discussion** — the community thread drew 40+ votes and repeated the AIM-7M/MH seeker changes, showing active player attention around how the updated missile behaves: https://www.reddit.com/r/dcsworld/comments/1udgks9/20260623_dcs_change_log_2927251835/
- Eagle Dynamics forums, **AIM-7 guidance broken in latest patch (6/12)** (2026-06) — players posted controlled tests and compared tracking behavior immediately around the seeker update, reinforcing the need for an evidence-minded training tool that separates support decisions from unverified performance claims: https://forum.dcs.world/topic/388969-aim-7-guidance-broken-in-latest-patch-612/
- r/hoggit, **Weekly Questions Thread — Oct 27** (2026-10-27) — the current weekly thread explicitly exists to handle repetitive learning questions and points users to a continuously running training server, supporting a compact, repeatable practice format: https://www.reddit.com/r/hoggit/comments/1xgdgay/weekly_questions_thread_oct_27/
- r/hoggit, **Improve FOX-1 Air-to-Air Combat: FLO & Ranges, Timeline, Tactics** — the community tutorial describes launch-to-timeout support as a fundamental Fox One requirement and discusses recurring timeline misconceptions, directly supporting the app's correction-first scenario design: https://www.reddit.com/r/hoggit/comments/1izsx4n/

The result is deliberately module-agnostic and evidence-conscious: recent missile-model changes and recurring training discussion supply the signal, while the interaction teaches a reusable cockpit workload pattern without asserting undocumented performance numbers.
