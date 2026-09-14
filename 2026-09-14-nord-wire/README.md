# NORD WIRE

NORD WIRE is a self-contained, offline manual command-to-line-of-sight (MCLOS) tracking trainer prompted by the newly detailed Nord AS-20 implementation for the upcoming DCS: G.91R. It isolates the hand-eye problem described by Eagle Dynamics—launch, visually track, and steer the missile through impact—without pretending to reproduce unreleased module behavior or weapon performance.

## Use

1. Open `index.html` directly in a modern browser; no server, build step, account, or network connection is required.
2. Select range, target behavior, and control conditions.
3. Acquire the target with the pale command reticle, then press **Launch** or **Space**.
4. Keep the simulated missile flare aligned with the target using the pointer, touch, **WASD**, or arrow keys.
5. Review terminal error, command reversals, track quality, and score. Use **New lane** to repeat or change conditions to increase workload.
6. Print the current station as a debrief record if desired. The latest 12 shots and setup choices persist in browser `localStorage`; **Clear log** removes them.

## Assumptions and boundaries

- This is a conceptual hand-eye coordination exercise, not official training material and not an IndiaFoxtEcho or Eagle Dynamics procedure.
- Range choices set exercise duration and difficulty only. Displayed “mil” error is a normalized training measure, not a validated AS-20 dispersion or sight model.
- The crosswind and gust options create command workload; they do not claim released missile aerodynamics.
- A shot passes when terminal normalized screen error is below the trainer’s fixed gate. Track quality also penalizes average error and repeated command reversals.
- The DCS: G.91R was still described as in development by the sources below on the access date. The app deliberately avoids cockpit switchology, launch-envelope numbers, and variant/loadout claims beyond those sources.

## Community signal

The September 4 development report put the G.91R back into current DCS discussion and singled out the Nord AS-20 as a demanding, unconventional weapon requiring continuous visual tracking and manual steering. The long-running developer forum thread also shows continued module anticipation, including a June 2026 reply calling it the author’s “most awaited aircraft in DCS.” Stormbirds’ same-day community coverage highlighted the manually guided Nord as one of the update’s defining period-specific weapons. Together, those signals support a focused pre-release coordination trainer rather than another generic checklist.

Sources accessed **2026-09-14**:

- Eagle Dynamics, **“G.91R Development Report”** (2026-09-04): https://digitalcombatsimulator.com/en/news/2026-09-04
- Eagle Dynamics Forums, **“DCS: G-91R”** developer/community thread, page 7: https://forum.dcs.world/topic/272980-dcs-g-91r/page/7/
- Stormbirds, **“Eagle Dynamics and IndiaFoxtEcho provide DCS: G.91 dev update”** (2026-09-04): http://stormbirds.blog/2026/09/04/eagle-dynamics-and-indiafoxtecho-provide-dcs-g-91-dev-update

## Privacy and portability

Everything runs inside one HTML file. No analytics, remote scripts, fonts, images, or APIs are used. Stored training history remains in the browser profile used to open the file.
