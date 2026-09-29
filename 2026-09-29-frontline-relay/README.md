# Frontline Relay

Frontline Relay is a self-contained, offline campaign turnboard for DCS World. It adds a lightweight persistence layer between otherwise disconnected sorties: four editable sectors hold control, friendly supply, and enemy pressure; the app turns the current weakest point into a sortie contract; and post-flight results change the next turn's theater state.

## Open and use

1. Open `index.html` directly in any modern browser. No web server, install, account, or network connection is required.
2. Name the campaign, select a map and era, then edit the four sectors to match your scenario.
3. Choose a preferred role and risk posture, or leave role on **Adaptive** so the app responds to the highest-pressure sector.
4. Generate a contract. The objective, success condition, and abort/continue rule can be copied as kneeboard text.
5. After flying, record success, partial result, or failure, plus losses, resource cost, and a short debrief note.
6. Advance the turn to apply abstract resupply and enemy pressure. Continue until your own campaign end condition is met.
7. Use **Export campaign** for a portable JSON backup. **Import**, printing, and all campaign state work offline.

Useful shortcut: `Ctrl/Cmd + G` generates a new contract.

## What is modeled

- Exactly four user-named sectors, each with control, friendly supply, and enemy pressure.
- Sortie contracts for CAP, escort, SEAD, strike, CAS, interdiction, reconnaissance, and logistics.
- Result effects that account for outcome, player losses, and resource intensity.
- Control changes when the supply-pressure balance crosses a clear threshold.
- Turn-based resupply and pressure, a persistent campaign log, printable briefs, and JSON backup/restore.

## Important assumptions

- This is a **manual narrative layer**, not a parser, mission generator, server connector, or official DCS dynamic-campaign implementation.
- Sector values are intentionally abstract. They are not real unit counts, damage estimates, aircraft performance data, or official DCS mechanics.
- A result only changes the sector assigned to the active contract. Users should edit sectors directly when an external mission or multiplayer event changes the wider theater.
- Advancing a turn applies simple deterministic pressure and resupply rules. The goal is continuity and consequential mission selection, not a full operational-level simulation.
- Generated contracts require the mission designer or pilot to select actual targets, routes, packages, weather, and rules of engagement in DCS.
- Browser storage is local to the browser/profile and file path. Export JSON before moving the folder, clearing browser data, or switching browsers.

## Community signal

The project responds to a recurring September 2026 community theme: players want sorties to connect to a changing war rather than remain isolated missions, while also recognizing that a full official dynamic campaign is a large and long-running request. A recent r/hoggit discussion about DCS 2026 explicitly centered the persistent dynamic campaign as a desired feature; another recent thread asked what happens after the current roadmap and drew renewed discussion of dynamic campaign work; and a September discussion about community-generated content highlighted demand for more substantial, replayable mission experiences. Frontline Relay does not claim to replace those systems—it offers a small, transparent campaign loop that works today with any mission or module.

Sources reviewed on 2026-09-29:

- Reddit, r/hoggit, “DCS 2026: Eagle Dynamics finally breaks silence + NEW AIRCRAFT leaked!” (dynamic-campaign discussion), accessed 2026-09-29: https://www.reddit.com/r/hoggit/comments/1n8d4q4/dcs_2026_eagle_dynamics_finally_breaks_silence/
- Reddit, r/hoggit, “Not to already look a gift horse in the mouth, but what's after the current roadmap is finished?”, accessed 2026-09-29: https://www.reddit.com/r/hoggit/comments/1nnl5fh/not_to_already_look_a_gift_horse_in_the_mouth_but/
- Reddit, r/hoggit, “DCS Community Generated Content Isn't Good Enough”, accessed 2026-09-29: https://www.reddit.com/r/hoggit/comments/1ndwn77/dcs_community_generated_content_isnt_good_enough/
- Reddit, r/hoggit, “What are currently the biggest issues DCS is facing?”, accessed 2026-09-29: https://www.reddit.com/r/hoggit/comments/1nlxn4q/what_are_currently_the_biggest_issues_dcs_is_facing/
- Eagle Dynamics Forums, “Is Dynamic Campaign dead?” (long-running official-forum demand context), accessed 2026-09-29: https://forum.dcs.world/topic/347884-is-dynamic-campaign-dead/

## Privacy and portability

All data stays in the browser unless the user explicitly exports a JSON file or prints. The app has no analytics, remote requests, external libraries, or runtime dependencies.
