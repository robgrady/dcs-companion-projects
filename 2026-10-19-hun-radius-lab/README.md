# Hun Radius Lab

Hun Radius Lab is a self-contained offline F-100D range-calibration and mission-radius tool for DCS World. Instead of embedding a fragile generic range figure, it turns the pilot's own repeatable test legs into observed fuel-per-mile and fuel-per-minute evidence, then builds a reserve-protected equal-leg mission-radius card.

## Use

1. Open `index.html` directly in a browser; no server, install, account, or connection is required.
2. Fly a stable test leg in the current DCS build and exact loadout. Record elapsed minutes, ground distance, and cockpit fuel at the beginning and end.
3. Add the run to the calibration ledger. Include stores, altitude, speed, weather, and technique notes so unlike tests are not mistaken for equivalent evidence.
4. Assign one measured run to **Outbound** and one to **Home**. A reciprocal pair is preferable when wind matters.
5. Enter brake-release fuel, start/taxi/climb allowance, protected landing reserve, desired combat/hold time, and a planning margin.
6. Select measured burn-rate evidence for combat/hold time. Read, copy, export, or print the generated radius card.

All useful state persists in `localStorage`. **Export data** creates a portable JSON backup; **Import** restores one. The printable view includes the calibration ledger and range card.

## Calculation model and assumptions

For each measured run:

- observed burn = start fuel − end fuel
- route burn rate = observed burn ÷ ground distance, in pounds per nautical mile
- time burn rate = observed burn ÷ elapsed minutes, in pounds per minute
- observed specific range = ground distance ÷ observed burn × 1,000, in nautical miles per 1,000 pounds

For the mission card:

- fuel after fixed costs = brake-release fuel − start/climb allowance − protected landing reserve
- combat/hold burn = selected run's pounds per minute × planned combat/hold minutes
- planning margin is removed from the remaining fuel before the route is solved
- equal-leg radius = route fuel ÷ (outbound pounds per mile + home pounds per mile)

This is an empirical planning aid, not an authoritative F-100D performance table. Results are only comparable when DCS version, stores, tank state, altitude, weather, throttle technique, and route direction are controlled. The app deliberately does not supply default fuel capacity, reserve, range, or fuel-flow claims. Validate every card in the current simulation build and against squadron procedures.

## Community signal

A current r/hoggit weekly questions discussion included a direct request from an F-100 pilot for a range planner that could answer practical loadout/radius questions; the replies noted that reliable public range data was still thin and suggested building a personal rule of thumb from measured fuel burn. A separate current quick-reference-guide discussion shows active demand for compact, cockpit-usable F-100 aids. The official Grinnelli Designs manual documents the simulated fuel system, while the DCS product page identifies the module as early access; together those signals favor a transparent calibration lab over invented constants.

Sources reviewed on **2026-10-19**:

- r/hoggit — Weekly Questions Thread (F-100 range-planner request and measured-rule-of-thumb discussion): https://www.reddit.com/r/hoggit/comments/1wa8obj/weekly_questions_thread_sep_08/
- r/hoggit — F-100D Quick Reference Guide next-update discussion: https://www.reddit.com/r/hoggit/comments/1wshufs/quick_reference_guide_next_update/
- Grinnelli Designs — F-100D manual, Fuel System: https://grinnellidesigns.github.io/f-100d-manual/Fuel/fuel.html
- Eagle Dynamics — DCS: F-100D Super Sabre product page: https://www.digitalcombatsimulator.com/en/products/planes/f-100d/

## Privacy and portability

Hun Radius Lab makes no network requests and has no external runtime dependencies. All CSS and JavaScript are inline in `index.html`; all saved data stays in the browser until the user exports it.