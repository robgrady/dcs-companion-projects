# TOT Wire

TOT Wire is a self-contained, offline DCS World package-timing desk. It works backward from a desired time on target (TOT) through editable route gates, distances, planned groundspeeds, and holds to produce a push time and every intermediate gate time. A live wire shows time remaining, an on-time tolerance band, and the actual target-crossing delta.

## Use

1. Open `index.html` directly in a browser; no server or network connection is required.
2. Enter the desired target time and, if the mission clock differs from the computer clock, a clock offset in seconds.
3. Build the route from push to target. Distances are nautical miles, speeds are **groundspeed in knots**, and holds are minutes.
4. Fly the generated gate times. At target crossing, press **Stamp crossing now** to record early/late performance.
5. Save automatically in the browser, print a compact card, or export/import the mission as JSON.

## Assumptions and limits

- Each leg time is `distance ÷ groundspeed`, plus the hold entered on that row.
- The first row normally represents push/departure and may have zero distance; the last row should be the target.
- Times wrap across midnight. The live countdown chooses the nearest occurrence within 12 hours.
- Wind and climb effects are not modeled directly: enter the expected **groundspeed** for each leg.
- This is a planning and training aid, not an aircraft-specific navigation-computer emulator. Validate all numbers against the mission, aircraft procedures, and flight lead's contract.

## Community signal

DCS pilots repeatedly ask how to establish and use TOT in the mission editor and aircraft, and recent forum traffic still reports confusion or broken behavior around built-in TOT functions. A second recurring thread asks what current mission-planning tools are available. That combination suggested an airframe-agnostic, file-local fallback that makes the timing contract visible and gives a flight a simple post-run delta.

Sources reviewed on **2026-08-12**:

- Eagle Dynamics Forums — [Time on Target broken](https://forum.dcs.world/topic/386986-time-on-target-broken/)
- Eagle Dynamics Forums — [Current Mission Planning Tools](https://forum.dcs.world/topic/374602-current-mission-planning-tools/)
- Eagle Dynamics Forums — [Time on target question](https://forum.dcs.world/topic/344914-time-on-target-question/)
- r/hoggit — [Time on target](https://www.reddit.com/r/hoggit/comments/d8mxii/time_on_target/)
- r/hoggit — [Mission Editor question: time over target](https://www.reddit.com/r/hoggit/comments/gj8el0/mission_editor_question_time_over_target/)
- r/hoggit — [DCS World Liberation takeoff time and time on target](https://www.reddit.com/r/hoggit/comments/q7lelf/dcs_world_liberation_40_take_off_time_and_time/)

Direct Reddit and forum page requests were blocked by their network policies during this run; the URLs and titles above were discovered and cross-checked through live Yahoo/Bing search results.

## Design note

Surface: **Operate**. The layout is a compact timing desk rather than a dashboard or marketing page. Slop audit after implementation: **0/10** — no gradient, generic tech hue, feature-tile grid, accent rail, blur, monument stat, icon toppers, center stack, default Inter, or wrong-surface composition.
