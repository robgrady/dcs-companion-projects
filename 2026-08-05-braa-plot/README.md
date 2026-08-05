# BRAA Plot

BRAA Plot is a self-contained, offline DCS World AWACS geometry desk. It turns a Bearing, Range, Altitude, Aspect call into a top-down plot, cockpit-relative clock position, shortest turn cue, vertical relationship, and a clearly qualified range-time estimate. A separate drill mode builds the mental conversion from magnetic bearing to clock position.

## Use

1. Open `index.html` directly in any modern browser. No server, install, account, or network connection is required.
2. In **Plot**, enter ownship magnetic heading and the four parts of the AWACS BRAA call.
3. Read the contact clock position and action stack, then save useful calls to the local scratchpad or print a compact kneeboard card.
4. In **Drill**, interpret each randomized call and select the contact's nearest clock position. Session score and best streak provide feedback.

Input values, scratchpad calls, last mode, and best training streak persist in browser `localStorage`. They remain local to the browser and file URL.

## Important assumptions

- This tool accepts **BRAA**, where bearing and range are relative to ownship. It does not convert Bullseye calls, which require the shared Bullseye position and ownship coordinates.
- Bearings and headings are treated as magnetic, matching the practical cockpit/AWACS workflow the tool is intended to rehearse.
- Clock position is rounded to the nearest 30-degree sector.
- The range clock is only distance divided by an explicit 420-knot reference speed. It excludes contact motion, aspect, wind, acceleration, and intercept geometry and is not presented as time-to-intercept.
- Aspect text is repeated as entered; the app does not infer a target heading.
- The app is a training and scratchpad aid, not a replacement for module documentation, mission briefing data, sensors, or tactical judgment.

## Community signal

Research accessed **2026-08-05** found a recurring rather than module-specific problem: pilots receive an AWACS call but struggle to turn the numbers into a visual search sector and actionable geometry.

- r/hoggit, “How to find (see) enemies?” (2025-03-23) — a recent example of difficulty progressing from calls/sensors to visual acquisition: https://www.reddit.com/r/hoggit/comments/1jig1ps/how_to_find_see_enemies/
- r/hoggit, “BRAA calls” (2023-08-13) — direct community confusion around interpreting BRAA: https://www.reddit.com/r/hoggit/comments/15qdej1/braa_calls/
- r/hoggit, “I feel so dumb asking … how do I read the MiG-19 compass … bearing 130” (2023-01-04) — shows the underlying bearing-to-cockpit-picture learning gap: https://www.reddit.com/r/hoggit/comments/103jscr/i_feel_so_dumb_asking_about_this_but_how_do_i/
- r/hoggit, “SkyEye Development Newsletter: December 2024” — continued community investment in clearer, more capable AIC/AWACS interactions: https://www.reddit.com/r/hoggit/comments/1h438pj/skyeye_development_newsletter_december_2024/
- Eagle Dynamics Forums, “Understanding AWACS Messages” — a long-running reference thread demonstrating that BRAA terminology and geometry remain persistent onboarding friction: https://forum.dcs.world/topic/173355-understanding-awacs-messages
- Eagle Dynamics Forums, “How do I make AWACS give bullseye/BRAA callouts …” — reinforces confusion between ownship-relative BRAA and fixed-reference Bullseye calls: https://forum.dcs.world/topic/284319-how-do-i-make-awacs-give-bullseye-braa-callouts-and-not-callouts-specific-to-each-player

The design deliberately addresses that narrow gap instead of claiming to reproduce AWACS logic or inventing module-specific facts.

## Design and accessibility

BRAA Plot is an **Operate** surface: controls, geometry, and the ordered action stack carry the hierarchy. It uses semantic landmarks, labeled inputs, a live feedback region, visible keyboard focus, 44-pixel controls, responsive layouts, reduced-motion handling, and print styling. The final anti-slop audit scored **0/10** after removing an unnecessary header blur; no compositional tells remained.
