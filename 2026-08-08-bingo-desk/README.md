# Bingo Desk

Bingo Desk is a self-contained, offline fuel-contract builder for Digital Combat Simulator missions. It turns user-tested fuel-flow figures into a planned ramp load, protected bingo and joker values, a phase-by-phase fuel-gate timeline, and a compact printable mission card. It is intentionally airframe-agnostic: the app does not pretend that one generic performance table can model every DCS module, loadout, altitude, weather state, or pilot technique.

## Use

1. Open `index.html` directly in a browser. No server, install, account, or network connection is required.
2. Enter a usable capacity, recovery cruise flow, and recovery groundspeed taken from your own test flight or squadron standard.
3. Build the sortie from fixed-burn, timed, and distance-based phases.
4. Define the recovery contract: decision-point distance, approach allowance, minimum touchdown fuel, joker margin, contingency, and start/taxi allowance.
5. Read the live ramp, bingo, joker, capacity warning, and fuel gates in the right-hand contract.
6. Use **Profiles** to save repeatable airframe/loadout baselines, export or import a JSON backup, and use **Print card** for a kneeboard-friendly hard copy.

The current plan and note persist in `localStorage`. Saved profiles are also local to the browser and file origin. Export profiles before clearing browser data or moving between browsers.

## Calculation model and assumptions

- **Fixed phase:** entered value is fuel burned directly.
- **Timed phase:** `minutes ÷ 60 × entered phase flow`.
- **Distance phase:** `nautical miles ÷ recovery groundspeed × entered phase flow`.
- **Recovery burn:** `distance to recovery ÷ recovery groundspeed × recovery cruise flow`.
- **Bingo:** recovery burn + approach/pattern allowance + minimum touchdown fuel.
- **Joker:** bingo + user-entered joker margin.
- **Contingency:** entered percentage of mission-phase burn only.
- **Planned ramp fuel:** start/taxi + mission phases + contingency + bingo.

All outputs are planning estimates, not authoritative aircraft data. Distance phases deliberately use the profile's single recovery groundspeed while retaining a per-phase flow; split a leg or use a fixed figure when winds, altitude, routing, or configuration make that simplification unsuitable. Validate the contract in the relevant DCS module and against mission or squadron procedures.

## Community signal

Fuel planning remains a recurring Hoggit problem rather than a one-off question: pilots ask how to calculate bingo, request deeper fuel-planning guidance, and share third-party calculators. The live search review on **2026-08-08** also surfaced a more recent Hoggit discussion about server logistics problems, reinforcing demand for explicit, transparent resource contracts rather than opaque guesses. Bingo Desk responds with editable assumptions and visible arithmetic instead of embedding unverifiable module constants.

Sources reviewed (accessed 2026-08-08):

- r/hoggit — “How do you actually calculate bingo fuel?”: https://www.reddit.com/r/hoggit/comments/9px8oc/how_do_you_actually_calculate_bingo_fuel/
- r/hoggit — “In Depth Discussion: Fuel Planning in DCS”: https://www.reddit.com/r/hoggit/comments/f314mv/in_depth_disccusion_fuel_planning_in_dcs/
- r/hoggit — “Rocket Mission Works — Fuel Planning Calculator”: https://www.reddit.com/r/hoggit/comments/17h7eyx/rocket_mission_works_fuel_planning_calculator/
- r/hoggit — “DCS World Server Logistics Problems”: https://www.reddit.com/r/hoggit/comments/1mgn15z/dcs_world_server_logistics_problems/

## Privacy and portability

Bingo Desk makes no network requests and has no external runtime dependencies. All CSS and JavaScript are inline in `index.html`; profile backups are ordinary JSON files generated locally.
