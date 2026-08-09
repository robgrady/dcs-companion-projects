# Hun Final

Hun Final is a self-contained, offline landing-pattern desk for the DCS: F-100D Super Sabre. It turns a pilot-supplied book final speed and runway wind into a five-phase landing contract, keeps the critical manual gates visible, and records short circuit debriefs locally.

## Use

1. Open `index.html` directly in a modern browser. No server, install, or network connection is required.
2. Enter the current manual/book final speed for the aircraft's actual weight and configuration. Enter runway magnetic heading and reported wind.
3. Review the calculated crosswind, head/tailwind component, and wind speed addition.
4. Work left-to-right through **Initial**, **Config**, **Final**, **Flare**, and **Rollout**. Check each action as it is completed.
5. Grade the pass, optionally capture touchdown speed, and write one change for the next circuit.
6. Print the current contract or export the circuit log as JSON. Inputs, phase progress, checks, and logs persist in `localStorage` on that browser.

## Assumptions and limits

- This is a training aid, not a substitute for the current Grinnelli Designs manual, DCS training missions, weather briefing, or pilot judgment.
- The app deliberately does **not** derive base approach speed from gross weight. The pilot must enter the published speed for the actual configuration; `165 KIAS at 24,000 lb` is loaded only as the manual's worked example.
- Wind correction follows the manual language: add one-half crosswind component plus one-half gust factor. Components are calculated from entered magnetic directions and rounded to the nearest knot.
- The crosswind alert reflects the manual's instruction to use a no-flap landing when crosswind component exceeds 25 knots. This app does not provide the separate no-flap procedure.
- Manual gates represented here include gear below 230 KIAS, pattern 20 KIAS above final, the 1 NM / 300 ft AGL final gate, 2.5–3° glidepath, 83–87% example approach RPM, and the preference to slow below 150 KIAS before drag-chute deployment. Always verify against the current module documentation.
- All data stays in the browser except a JSON file the user explicitly exports.

## Why this project

The F-100D released in June 2026 and Eagle Dynamics described it as an aircraft that challenges even skilled virtual pilots. Current community search showed that landing technique quickly became a focused support topic: an active Eagle Dynamics forum thread is specifically titled **“Landing Tutorial Vid”**, while a companion forum thread points new owners to the newly available manual. That combination—fresh module attention, a demanding landing model, and pilots circulating dedicated landing instruction—was the clearest current signal for a focused pattern-rehearsal tool rather than another generic checklist.

Sources reviewed on **2026-08-09**:

- Eagle Dynamics, “Release The Hun!” — module release announcement and feature summary: https://www.digitalcombatsimulator.com/en/news/2026-06-12/
- Eagle Dynamics Forums, “Landing Tutorial Vid” — active F-100D landing-technique discussion: https://forum.dcs.world/topic/389141-landing-tutorial-vid/
- Eagle Dynamics Forums, “The manual is available for the DCS F-100D!” — community documentation signal: https://forum.dcs.world/topic/388854-the-manual-is-available-for-the-dcs-f-100d/
- Grinnelli Designs, DCS F-100D Manual, “Landing” — source for procedures, gates, worked-speed example, wind correction, porpoise response, and rollout cautions: https://grinnellidesigns.github.io/f-100d-manual/Procedures/Normal/landing.html
- r/hoggit, “F100D Super Sabre – Report: The Road to Realism” — longer-running community interest that preceded release: https://www.reddit.com/r/hoggit/comments/19amkon/f100d_super_sabre_report_the_road_to_realism_by/

## Design and accessibility

Hun Final is an **Operate** surface: setup and action state have priority over decoration. It uses semantic sections, visible keyboard focus, labeled controls, 42–44 px touch targets, responsive single-column behavior, print styling, reduced-motion respect, and live status text. The artifact is fully self-contained with inline CSS and JavaScript and no external runtime dependencies.
