# Load Balance

Load Balance is a self-contained, offline DCS World loadout mass and lateral-asymmetry desk. It turns user-supplied module data into three explicit preflight gates: launch mass, expected recovery mass, and lateral store moment. It deliberately contains no hard-coded aircraft limits or weapon weights, because those values can differ by module, loadout, mission state, and update.

## Use

1. Open `index.html` directly in a modern browser. No server, account, or network connection is required.
2. Enter the aircraft's empty/fixed mass, launch and expected recovery fuel, and approved mass/moment limits from current module documentation.
3. Build the station ledger. Assign each store to the left, center, or right; enter quantity, unit weight, and lateral arm from centerline.
4. Leave **Returns** checked for stores expected aboard at recovery. Clear it for stores expected to be expended or released.
5. Read the launch, recovery, and balance gates. A blank limit is shown as **LIMIT NEEDED**, never as a pass.
6. Record the crew decision, then copy a text summary, export the complete plan as JSON, or print a compact card.

Plans are saved automatically in browser `localStorage`. JSON import/export provides a portable backup. **Mirror left → right** rebuilds the right-side rows from the left-side ledger. The worked example is intentionally fictional and visibly labeled; replace every example value before use.

## Calculation and assumptions

- Launch gross mass = empty/fixed mass + launch fuel + all station masses.
- Recovery gross mass = empty/fixed mass + recovery fuel + returning station masses + recovery change.
- Station mass = quantity × unit weight.
- Signed lateral moment = sum of station mass × lateral arm, with left negative and right positive.
- Centerline stores have zero lateral arm.
- The balance gate compares the absolute net lateral moment with the user-entered limit.
- This tool does not calculate center of gravity, aerodynamic drag, takeoff trim, structural load category, rack restrictions, station compatibility, or fuel transfer behavior.
- “Returns” is a planning assumption, not a jettison recommendation. Operational and emergency procedures remain controlling.

This is a simulation planning aid, not certified flight data. Verify results against the current DCS loadout screen, module manual, and applicable squadron procedures.

## Community signal

The strongest current signal was demand for an all-in-one loadout planner that exposes gross weight, maximum trap weight, fuel, and load asymmetry rather than leaving those checks scattered across spreadsheets and cockpit arithmetic:

- r/hoggit, **“I made a loadout creator, flight planner, and kneeboards for the DCS Hornet, Viper, and Tomcat”** (published 2026-03-14). The author specifically lists gross/max-trap weight and load asymmetry among the planning needs; commenters praised the usefulness for solo and squadron mission planning. Accessed 2026-09-17.  
  https://www.reddit.com/r/hoggit/comments/1rt4f40/i_made_a_loadout_creator_flight_planner_and/
- r/hoggit, **“Digital Kneeboard Simulator — A web-based mission card builder for DCS”** (published 2026-01-25). Its reception supports fast, preflight mission-planning tools that supplement rather than replace the Mission Editor. Accessed 2026-09-17.  
  https://www.reddit.com/r/hoggit/comments/1qm8mad/digital_kneeboard_simulator_a_webbased_mission/
- Eagle Dynamics Forums, **“About asymmetric payload trim”**. The solved discussion notes that store weight alone is insufficient to calculate foot-pounds without station-position information. That directly motivated the explicit lateral-arm field and the refusal to invent arms. Accessed 2026-09-17.  
  https://forum.dcs.world/topic/200442-about-asymmetric-payload-trim/

## Privacy and portability

All calculations run locally. The app sends no data, loads no external scripts, and works from a `file://` URL. Browser storage is local to the browser/profile and file origin.