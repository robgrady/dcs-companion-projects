# Spin Gate

Spin Gate is a self-contained, offline F-100D Super Sabre departure-recovery rehearsal tool for DCS World. It turns the module manual's spin-recovery procedure into a timed, altitude-aware blind drill: choose the next immediate action, absorb a penalty for incorrect sequencing, and make the published 10,000-foot AGL ejection decision.

## Use

1. Open `index.html` directly in a modern browser. No server, installation, account, or network connection is required.
2. Set entry altitude, spin direction, development, external load, and aircraft configuration.
3. Select **Begin blind drill**.
4. Choose each immediate action in order. The action labels remain hidden until completed; incorrect selections cost time and simulated altitude.
5. Review the result and repeat. The most recent 12 attempts remain in `localStorage` on that browser.

Keyboard shortcuts: number keys `1`–`6` select an action; `R` repeats the configured scenario.

## Assumptions and limits

- The checklist order and 10,000-foot AGL decision floor follow the current DCS F-100D manual's Spin Recovery page.
- The altitude-loss rates, error penalties, and control-response timing are deliberately simplified training abstractions. They do **not** model the DCS flight model and must not be used to predict an actual recovery envelope.
- Configuration choices only add or remove applicable checklist actions; they do not claim to reproduce aerodynamic differences.
- This is a simulation-only memory and decision aid. The current module manual remains authoritative.

## Why this project

Current community conversation around the released F-100D repeatedly centers on departure behavior, flat spins, limited altitude, and the unusual type-specific recovery controls. A recent r/hoggit flat-spin discussion specifically debated whether recovery would be practical before the manual's 10,000-foot AGL ejection floor, while broader F-100D BFM discussion warned that low-speed maneuvering can lead to snap-roll/spin departures. The r/dcsworld early-access launch discussion likewise called out spin risk, and Eagle Dynamics reported continuing F-100D development based on community feedback. Together, those signals suggested a focused procedural rehearsal tool rather than another general checklist.

Sources reviewed on **2026-11-20**:

- Grinnelli Designs, **DCS F-100D Manual — Spin Recovery**: https://grinnellidesigns.github.io/f-100d-manual/Procedures/Emergency/spin.html
- r/hoggit, **DCS F-100D Flat Spin — This Vintage Fighter Has No Safety Net**: https://www.reddit.com/r/hoggit/comments/1uedf2q/dcs_f100d_flat_spin_this_vintage_fighter_has_no/
- r/hoggit, **How will the F-100D BFM performance be compared to its peers?**: https://www.reddit.com/r/hoggit/comments/1thx791/how_will_the_f100d_bfm_performance_be_compared_to/
- r/dcsworld, **DCS: F-100D SUPER SABRE | Early Access Launch**: https://www.reddit.com/r/dcsworld/comments/1u4l6yd/dcs_f100d_super_sabre_early_access_launch/
- r/dcsworld, **2026/06/12 DCS Change log 2.9.27.24969** (F-100D introduction and known issues): https://www.reddit.com/r/dcsworld/comments/1u46unl/20260612_dcs_change_log_292724969/
- Eagle Dynamics, **DCS: F-100D Development Report**: https://www.digitalcombatsimulator.com/en/news/2026-08-22/

## Privacy and portability

Spin Gate sends no data anywhere. Attempt history is stored only in the browser's local storage. To reset it, use **Clear history**. The app has no external runtime dependencies and works from a `file://` URL.
