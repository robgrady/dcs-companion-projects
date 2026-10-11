# Sweep Contract

**Sweep Contract** is a self-contained, offline F-14 pilot/Jester radar-search planning and evidence desk for DCS World. It turns an expected target sector into a repeatable search contract, plots the geometry, produces a short Pilot↔Jester run card, and records paired baseline-versus-mission observations.

Open `index.html` directly in a browser. No server, install, network connection, or build step is required.

## Why it exists

Recent community discussions continue to show a practical gap between knowing that the Tomcat radar works and building a repeatable solo-pilot search:

- A March 2026 r/hoggit discussion described radar-elevation management as requiring too many Jester menu steps and target acquisition lagging visual acquisition.
- An August 2026 Eagle Dynamics forum request asks for stable control over radar azimuth, elevation, and bar settings through Jester, including concern that selected scan settings are reset.
- A July 2026 r/dcsworld discussion praised the F-14B(U) context command for pointing Jester and the radar at datalink targets, showing that the new workflow is valuable but important enough to rehearse deliberately.
- Heatblur’s F-14B(U) documentation describes the context command as situation-dependent and documents pilot-visible A/A target data on VDIG-R. The app therefore treats cockpit context and visible acknowledgment as evidence to record, not assumptions.

## Use

1. Enter own altitude, expected target altitude bracket, range, target bearing, own heading, and expected azimuth spread.
2. Select a planning pattern. The app calculates line-of-sight look angles and checks whether the expected horizontal bracket fits the chosen planning width.
3. Follow the generated run card. Confirm the actual current Jester command path in the cockpit/manual.
4. Run a controlled **Baseline** and then the problem **Mission**. Record contact result, acknowledgment, unexpected pattern changes, timing, and visible evidence.
5. Compare the latest pair. Change only one variable on the next run.
6. Save snapshots, export/import a JSON backup, or print the contract as a kneeboard/reference sheet.

All useful state is saved in browser `localStorage`.

## Important assumptions and limits

- Angles are pure line-of-sight geometry: `atan2(target altitude − own altitude, slant-range approximation)` using 6,076.12 feet per nautical mile.
- The app does **not** model AWG-9 performance, antenna limits, scan timing, beam/bar geometry, clutter, look-down penalties, target aspect, jamming, datalink quality, mission scripting, damage, or Jester AI logic.
- The ±20°/4-bar and ±40°/2-bar labels are user-selected planning shorthand, not a promise that DCS or Jester will maintain that exact scan.
- Bearing inputs are treated as true bearings for relative-azimuth planning. Use a consistent reference.
- VDIG-R, TID repeater, Jester voice/subtitles, and weapon cues are observation choices; availability depends on aircraft state, mode, options, and current implementation.
- This is a simulator companion, not real-world aviation guidance.

## Community and official sources

Accessed **2026-10-11**:

- Reddit r/hoggit — “Opinion needed about Bombcat vs Phantom and Jester…”: https://www.reddit.com/r/hoggit/comments/1rxcmw1/opinion_needed_about_bombcat_vs_phantom_and/
- Reddit r/dcsworld — “How are all of you liking the F-14 B/U?”: https://www.reddit.com/r/dcsworld/comments/1v5e0ao/how_are_all_of_you_liking_the_f14_bu/
- Eagle Dynamics Forums — “Let us change radar azimut, elevation, bars with Jester…”: https://forum.dcs.world/topic/391119-let-us-change-radar-azimut-elevation-bars-with-jester-or-prevent-him-for-resetting-it-please/
- Heatblur F-14B(U) manual — Jester & Iceman overview / Quick Jester: https://f14.manuals.heatblur.se/f14bu/jester_iceman/overview.html
- Heatblur F-14B(U) manual — VDIG-R Air-to-Air modes: https://f14.manuals.heatblur.se/f14bu/weapons/air_to_air/vdigr_aa.html


## Privacy

The app makes no network requests. Contracts, snapshots, and run history remain in the local browser profile unless explicitly exported as JSON.
