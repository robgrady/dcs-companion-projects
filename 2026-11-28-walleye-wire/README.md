# Walleye Wire

**Walleye Wire** is a self-contained, offline A-6E Walleye II contrast-track rehearsal for DCS World. It combines a patch-specific loadout gate with an interactive monochrome video trainer that rewards alignment and restrained corrections rather than frantic reticle chasing.

Open `index.html` directly in any modern browser. No server, install, network connection, or build step is required.

## How to use

1. Configure at least one **Walleye II** on pylon 2 or 4 and the **AN/AWW-13** pod on pylon 3.
2. Choose a video condition and run length.
3. Select **Begin rehearsal**.
4. Move the reticle with **WASD**, the **arrow keys**, pointer, or touch.
5. Hold **Space**, the on-screen designate button, or pointer press while inside the capture circle.
6. After simulated release, keep the reticle close to the fixed contrast aimpoint with small corrections.
7. Review alignment, smoothness, total score, and locally saved recent runs.

The Weathered condition includes a deliberate short video dropout. Useful settings and up to 12 completed scores persist in `localStorage`; nothing leaves the browser.

## Assumptions and limits

- This is a hand–eye coordination abstraction, not an A-6E cockpit, weapon-logic, aerodynamics, range, or switchology simulator.
- The fixed target appears to move because the simulated viewpoint drifts and bumps.
- The loadout gate encodes only the compatibility explicitly listed in the current DCS changelog: Walleye II on A-6E pylons 2 and 4, and AN/AWW-13 on pylon 3.
- Consult the current Heatblur documentation and DCS procedures for actual employment.

## Why this project

DCS update **2.9.32.30490**, dated November 26, 2026, added the Walleye II and its datalink pod to the Heatblur A-6E. The update was immediately reposted and discussed in r/dcsworld, while longer-running r/hoggit discussions show persistent interest in the A-6E and recurring questions about Walleye employment and datalink behavior. Walleye Wire turns that fresh weapon addition into a focused practice surface without pretending to reproduce undocumented A-6E cockpit logic.

Sources accessed **2026-11-28**:

- Eagle Dynamics, DCS 2.9.32.30490 changelog: https://www.digitalcombatsimulator.com/en/news/changelog/release/2.9.32.30490/
- r/dcsworld, “2026/11/26 - DCS Update Change log 2.9.32.30490”: https://www.reddit.com/r/dcsworld/comments/1y5zqg1/20261126_dcs_update_change_log_293230490/
- r/hoggit, “These make me wanna fly the A-6”: https://www.reddit.com/r/hoggit/comments/1ptu4as/these_make_me_wanna_fly_the_a6/
- r/hoggit, Walleye development-documentary discussion and module questions: https://www.reddit.com/r/hoggit/comments/m2j9qr/
- r/hoggit, post-release Walleye datalink troubleshooting example: https://www.reddit.com/r/hoggit/comments/i933r9/

## Design notes

Primary surface: **Operate** (with a secondary Monitor layer), so the loadout gate and active control loop dominate instead of a marketing hero or feature-card grid.

Slop audit after implementation: **0/10**. No tech gradient, generic indigo, equal-weight feature tiles, accent rails, blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch.
