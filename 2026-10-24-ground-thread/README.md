# Ground Thread

Ground Thread is a self-contained, offline DCS World ground-operations planner. It turns a taxi route into an ordered visual thread, forces explicit hold-short and runway-crossing gates, and generates a cockpit step-through rehearsal with controlled-field, self-announce, or silent/AI-workaround calls.

## Why this project

Recent community discussion showed three related signals:

1. DCS pilots continue to describe the stock ATC system as immersion-breaking or unreliable, while improved ATC remains a frequently requested feature.
2. Players specifically report taxi-route uncertainty, weak or missing ground-direction support, and AI runway behavior that can disrupt otherwise workable missions.
3. A recent Eagle Dynamics update added a Mission Editor AI runway-lineup option and related runway-behavior changes, making ground sequencing and runway-entry discipline timely for mission builders and pilots.

Ground Thread does not attempt to replace DCS ATC or provide authoritative airfield charts. It provides a compact, user-authored ground plan that remains usable when mission scripting, server procedures, AI behavior, or radio support differ.

## Use

1. Open `index.html` directly in a modern browser. No server, installation, network access, or build step is required.
2. Enter the airfield, flight callsign, active runway, frequency or preset, and operating posture.
3. Click the schematic from origin to destination. Add a point at each meaningful turn, hold line, runway crossing, runway entry/exit, or parking destination.
4. Select points to rename them, assign their operational type, mark clearance gates, and add cockpit cues.
5. Resolve red and amber items in **Gate Check**.
6. Use **Cockpit Rehearsal** or the left/right arrow keys to walk the route in order. The call shown at each point adapts to the selected operating posture.
7. Export the plan as JSON for backup or handoff, import it later, or print a compact route card.

All working state is saved locally in the browser with `localStorage`.

## Important assumptions

- This is a simulation companion and planning aid, not real-world aeronautical guidance.
- The user is responsible for confirming the current mission runway, taxi signs, traffic, server rules, frequencies, clearances, and any airfield-specific restrictions.
- The schematic is intentionally not georeferenced. It records decision points and route order rather than claiming chart accuracy.
- Generated radio text is a concise rehearsal scratch call, not a complete national or military phraseology standard.
- A marked clearance gate means “stop and verify authorization before passing”; it cannot detect or grant in-game clearance.
- DCS AI and ATC behavior can vary by mission, map, scripting, and game version.

## Community and official signals

Accessed October 24, 2026:

- Reddit / r/hoggit — “Can we all agree that better ATC should be the next priority for ED?”: https://www.reddit.com/r/hoggit/comments/1k0ci0o/can_we_all_agree_that_better_atc_should_be_the/
- Reddit / r/dcsworld — “AI taxiing to runway” discussion of ATC/AI ground behavior: https://www.reddit.com/r/dcsworld/comments/1patlps/ai_taxiing_to_runway/
- Reddit / r/hoggit — “Does DCS plan to improve the awful ATC system?”: https://www.reddit.com/r/hoggit/comments/1g6op97/does_dcs_plan_to_improve_the_awful_atc_system/
- Eagle Dynamics forum — “ATC Taxi instructions” wishlist discussion: https://forum.dcs.world/topic/338186-atc-taxi-instructions/
- Eagle Dynamics forum — user reports covering ATC radio bugs and runway-access behavior: https://forum.dcs.world/topic/370227-bugs-with-atc-radio-communications/
- Eagle Dynamics — DCS update changelog announcing the Mission Editor “Runway lineup” AI takeoff option and related runway-behavior changes: https://www.digitalcombatsimulator.com/en/news/changelog/

## Files

- `index.html` — complete app with inline CSS and JavaScript
- `README.md` — usage, assumptions, and source context
