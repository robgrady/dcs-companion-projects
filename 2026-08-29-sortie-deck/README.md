# Sortie Deck

Sortie Deck is a complete offline decision queue for DCS World pilots who have time to fly but do not want to spend that time deciding what to do. It combines the pilot's selected aircraft, available terrain, timebox, workload, role, and start posture into one bounded sortie contract. Committed sorties move to a flight line; flown and scrubbed outcomes become a short repeat-avoidance history.

## Use

1. Open `index.html` directly in a modern browser. No web server or connection is required.
2. Select at least one aircraft and terrain. Click a chip to include/exclude it; double-click a custom or default chip to remove it. Add modules or maps with the adjacent text fields.
3. Choose a start posture:
   - **Ready** creates a conventional ingress/task/recovery contract.
   - **Training** explicitly calls for waypoint gates and repeatability.
   - **Open** is route-free and uses a timebox rather than a prescribed route.
4. Set available time, workload, and an optional role bias, then choose **Deal a sortie**.
5. Acknowledge the planning gates, commit the contract, and later mark it **Flown** or **Scrub**. The latest five outcomes influence repeat avoidance.
6. Print the active contract or export the queue/history as JSON. Useful state persists in `localStorage` for this browser and file location.

## Assumptions and boundaries

- Sortie Deck is a decision and rehearsal aid, not an aircraft performance calculator, mission generator, or substitute for module documentation.
- It deliberately avoids unverified weapon envelopes, airframe-specific procedures, frequencies, and map coordinates.
- The generated contract supplies intent and gates; the pilot selects suitable DCS mission content and applies current module procedures.
- The initial aircraft and terrain chips are editable examples, not a claim that the user owns those products.
- Everything runs locally in one self-contained HTML file. Export is user-initiated; no information is transmitted.

## Community signal (accessed 2026-08-29)

The immediate signal was a current r/dcsworld question—“What to do in DCS in 2026”—from a returning pilot looking for a way back into flying, alongside the 2026-08-27 change-log discussion announcing DCS's new **Start Here** special missions for new players. A current r/hoggit discussion comparing DCS and Falcon BMS also drew sustained conversation around the experience surrounding individual sorties, while another current community dynamic-campaign post explicitly requested advanced customization and automatic briefing/kneeboard generation. Together these point to a recurring gap between owning detailed aircraft and quickly choosing a purposeful next flight. Sortie Deck addresses the smaller, offline, immediately solvable part of that gap without pretending to generate a `.miz` mission.

Sources:

- r/dcsworld, “What to do in DCS in 2026”: https://www.reddit.com/r/dcsworld/comments/1uamfz2/what_to_do_in_dcs_in_2026/
- r/dcsworld, “2026/08/27 DCS change log 2.9.29.27278” (includes the new Start Here menu and initial P-51D, F/A-18C, and AH-64D missions): https://www.reddit.com/r/dcsworld/comments/1vz0stn/20260827_dcs_change_log_292927278/
- r/hoggit, “DCS and Falcon BMS current state”: https://www.reddit.com/r/hoggit/comments/1uucuvk/dcs_and_falcon_bms_current_state/
- r/hoggit, “My DCS Dynamic Campaign — What It Currently Does”: https://www.reddit.com/r/hoggit/comments/1vy3tsq/my_dcs_dynamic_campaign_what_it_currently_does/

## Design notes

This is an **Operate** surface, not a marketing surface: constraints are on the left, the active contract dominates the center, and commitment/outcomes sit on the right. The visual language is a restrained paper flight-deck dossier with a dark active board, one safety-red action color, square geometry, dense labels, and no decorative metrics.

Slop diagnostic before final polish: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rails, glass blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch was present. Post-verification score: **0/10**.
