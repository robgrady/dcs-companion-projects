# Pod Orbit Board

**Pod Orbit Board** is a self-contained, offline rehearsal desk for DCS: F-14B(U) pilots working a LANTIRN target with Jester. It turns airspeed, bank, orbit direction, and starting heading into a top-down orbit visualization, then lets the pilot rehearse a deliberately simplified search-to-designate crew contract without leaving the browser.

Open `index.html` directly in a modern browser. No server, build step, account, or network connection is required.

## What it does

- Computes estimated level-turn radius, turn rate, and orbit period from true airspeed and bank angle.
- Animates a top-down left- or right-hand orbit around a named target.
- Tracks a four-item pre-turn contract covering aircraft/pod mode, target identification, clear airspace, and crew intent.
- Provides a four-state **SEARCH → AREA → POINT → DESIGNATE** context rehearsal.
- Runs randomized cue-response drills for stable geometry, wrong-object rejection, track discipline, and traffic conflicts.
- Saves the current contract, checks, score, and the latest 12 rehearsal records in browser `localStorage`.
- Exports the complete local record as JSON and produces a compact print card.

## Use

1. Set true airspeed, bank angle, orbit side, starting heading, and target label.
2. Select **Apply contract** and review the estimated geometry. The displayed radius is the radius of a coordinated, level turn—not slant range to the target.
3. Complete the four pre-turn checks only after confirming them in the mission.
4. Select **Start orbit** to animate one orbit period and practice maintaining a predictable turn.
5. Use **Context tap** to walk the training abstraction from search through designation. Read the live DCS cue before every real input; Jester context behavior depends on aircraft mode and where the pilot is looking.
6. Use **New cue** for short judgment drills, then **Log rehearsal** to retain the setup and current state.

## Important assumptions and limits

- Turn geometry uses `radius = velocity² / (g × tan(bank))`, standard gravity, knots converted to metres per second, and a coordinated level turn. It does not model wind, altitude effects, manoeuvre transients, autopilot behavior, pod line-of-sight, masking, gimbal limits, terrain, or DCS-specific sensor behavior.
- The context contract is intentionally a memory aid, not a representation of every internal Jester or LANTIRN state. Heatblur labels the current F-14B(U) Jester documentation work in progress.
- The app does not prescribe a “correct” speed or bank. Those values depend on the mission, terrain, threats, weather, aircraft state, desired standoff, and current module behavior.
- **Abort turn** is the intended drill response to a known traffic conflict. Aircraft control, collision avoidance, mission rules, and the current official manual always override this companion.
- This project is unofficial and is not affiliated with Eagle Dynamics or Heatblur Simulations.

## Community signal

Research accessed **2026-09-13** identified a specific, current F-14B(U) learning problem rather than a generic targeting-tool request:

- An Eagle Dynamics forum thread reports pilots losing or struggling to retain a LANTIRN target after returning control to Jester. The suggested corrective pattern combines a stable, slow orbit with deliberate Jester-context transitions from area track toward point track and designation. This directly motivated the geometry display and context rehearsal: <https://forum.dcs.world/topic/390970-f14b-u-issues/>
- Heatblur’s official, work-in-progress F-14B(U) manual confirms that the context command is mode-sensitive and that holding/releasing it while looking at an area of interest can prompt Jester to slew the pod and establish an area track. This is the factual boundary for the app’s context guidance: <https://f14.manuals.heatblur.se/f14bu/jester_iceman/overview.html>
- A recent r/hoggit impressions thread calls the new Jester context menu a major improvement and highlights how central it is to single-player rear-seat cooperation. That enthusiasm, paired with forum confusion about the same interaction, supports a short rehearsal tool rather than another static checklist: <https://www.reddit.com/r/hoggit/comments/1vat1xl/f14_bu_impressions/>
- A separate recent r/hoggit compatibility discussion shows that F-14B(U) changes also disrupted some established voice-command workflows, reinforcing the value of a dependency-free practice surface that teaches the underlying crew decision rather than one external integration: <https://www.reddit.com/r/hoggit/comments/1v9kf88/dcs_f14_292826385_vaicom_issues/>

## Privacy

All state stays in the browser profile on the local machine unless the user explicitly downloads a JSON export. **Clear local data** deletes the app’s saved `localStorage` record after confirmation.
