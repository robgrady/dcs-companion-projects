# Wind Ledger

Wind Ledger is a self-contained offline weather translation desk for DCS World. It turns the three wind layers commonly shown in the static-weather Mission Editor into a conventional aviation wind-from brief, evaluates both ends of a runway, calculates headwind/tailwind and crosswind components, estimates density altitude, converts QNH and cloud-base units, and produces a printable/copied mission card.

## Use

1. Open `index.html` directly in a modern browser; no server or internet connection is required.
2. Enter the runway magnetic heading and your planning crosswind limit.
3. Copy the DCS wind speed (m/s) and direction into each layer. Wind Ledger treats those direction values as **where the wind blows toward**, then rotates them 180° for the aviation wind-from display.
4. Add QNH, field elevation, temperature, cloud base, and an optional pilot note.
5. Read the favored runway and components, then copy or print the brief. Save snapshots to retain multiple recovery pictures; current inputs and snapshots persist in `localStorage`.

## Important assumptions

- This is a planning aid, not an aircraft performance authority. Aircraft manual limits, mission ATIS, windsock indications, controller instructions, and current conditions take precedence.
- Runway heading is entered in magnetic degrees. Wind is assumed to use the same reference for component calculations.
- The DCS static-weather Mission Editor convention is treated as a direction wind blows **to**, unlike the aviation convention of reporting where wind comes **from**. Mission scripts, third-party weather injectors, dynamic weather, or module displays may behave differently; verify in the mission.
- Surface speed conversion is `1 m/s = 1.94384 kt`. Crosswind and headwind use standard vector components. The favored runway is whichever of the entered heading or its reciprocal has the larger headwind component.
- Density altitude is an approximation: pressure altitude from QNH plus `120 ft × (OAT − ISA temperature)`. It is for orientation, not TOLD certification.
- Layer delta values are the magnitude of the horizontal wind-vector change between adjacent entered layers; they are not a turbulence or windshear forecast.

## Community signal and sources

Research accessed **2026-08-15** found a recurring need to translate DCS weather into cockpit-useful information:

- An r/hoggit discussion, **“Reading weather,”** specifically describes confusion caused by DCS presenting wind differently from normal aviation reporting: <https://www.reddit.com/r/hoggit/comments/gsb4t2/reading_weather/>
- An r/dcsworld discussion, **“Questions about rudder uses in DCS,”** highlights practical uncertainty around crosswind technique and runway alignment: <https://www.reddit.com/r/dcsworld/comments/13edzos/questions_about_rudder_uses_in_dcs/>
- The Eagle Dynamics forum thread **“Wind Data for TOLD?”** (started 2025-11-29) asks where reliable current in-mission wind data can be obtained for takeoff and landing calculations: <https://forum.dcs.world/topic/382196-wind-data-for-told/>
- The Eagle Dynamics forum thread **“How to properly set up weather”** (started 2025-12-05) records continued confusion around presets versus dynamic weather behavior: <https://forum.dcs.world/topic/382636-how-to-properly-set-up-weather/>
- A longstanding Eagle Dynamics Mission Editor discussion documents the compatibility implications of the editor’s wind-direction convention: <https://forum.dcs.world/topic/206337-wind/>

These signals led to a narrow operational tool rather than another general mission planner: translate the values pilots already have, expose the convention clearly, and produce a runway decision card without network access.

## Privacy and portability

All data remains in the browser on the local device. There are no external runtime dependencies, analytics, network requests, or build steps. Use **Reset** to restore defaults and **Clear** to remove saved snapshots.