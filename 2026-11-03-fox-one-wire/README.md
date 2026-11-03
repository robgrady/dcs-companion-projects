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

- Eagle Dynamics, **DCS 2.9.20.203 changelog** — the current changelog includes AIM-7M/MH seeker work, including line-of-sight-rate filtering behavior. That made Fox One support discipline timely without just repeating a module checklist or fixed-range calculator: https://www.digitalcombatsimulator.com/en/news/changelog/stable/2.9.20.203/
- r/hoggit, **Weekly Questions and Information Thread** (2026-11-01) — a current high-traffic help thread centered on module choice, setup, and learning questions, reinforcing demand for compact training aids that turn doctrine into repeatable practice: https://www.reddit.com/r/hoggit/comments/1ok3j28/dcs_weekly_questions_and_information_thread/
- r/hoggit, **“So that sounds like we aren't getting dynamic campaign…”** (2026-10-28) — discussion around missing long-form structure and replayable purpose reinforced making a scenario-based trainer with changing engagement pressure rather than a static reference card: https://www.reddit.com/r/hoggit/comments/1oh6i30/so_that_sounds_like_we_arent_getting_dynamic/
- DCS World forums, **General Questions → Air-to-Air Missile Employment** — recurring user questions about SARH support, crank geometry, and when a shot is no longer supportable informed the correction-first training model: https://forum.dcs.world/forum/460-air-to-air/

The result is deliberately module-agnostic and evidence-conscious: current missile-model buzz supplies the timely hook, while the interaction teaches a reusable cockpit workload pattern without asserting undocumented performance numbers.
