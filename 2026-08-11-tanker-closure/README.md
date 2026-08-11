# Closure — DCS Tanker Practice Desk

**Closure** is a self-contained, offline air-to-air refueling closure trainer for DCS World. It isolates the part many pilots struggle to practice deliberately: shedding rendezvous closure early, making small speed corrections, and arriving at pre-contact already stable.

## Use

1. Open `index.html` directly in any modern browser; no server, account, build step, or network connection is required.
2. Select boom/receptacle or probe/drogue, then set tanker IAS, starting range, and initial closure—or choose a quick scenario.
3. Start the run. Use the on-screen −/+ controls or the arrow keys to change airspeed (hold Shift for 5 kt changes).
4. Satisfy progressively tighter closure gates and reach pre-contact without an overtake. Runs, stability score, and recent results persist in localStorage.
5. Print a compact reference if desired.

## Assumptions and limits

- The display is a technique trainer, not a flight-dynamics model: range changes from the difference between tanker and receiver speed in still air.
- Closure gates (40/20/10/3 kt) are conservative training targets created for this exercise, not official limits for every aircraft or tanker.
- Tanker procedures, observation/pre-contact geometry, communications, and approved speeds vary by aircraft, mission, and server. Use the applicable DCS module manual and mission brief.
- Both refueling systems share the closure exercise; the app does not claim to model boom or hose physics.

## Community signal

Accessed **2026-08-11**. Current community searches continue to surface repeated requests for help with air-to-air refueling, with discussion concentrating on difficulty holding position, pilot-induced oscillation, and learning to control closure rather than chasing the basket or boom. This tool deliberately targets that shared control problem without duplicating the repository's existing fuel-planning project.

- r/hoggit search: [air to air refueling](https://www.reddit.com/r/hoggit/search/?q=air%20to%20air%20refueling&restrict_sr=1&sort=new&t=year)
- r/hoggit search: [tanker](https://www.reddit.com/r/hoggit/search/?q=tanker&restrict_sr=1&sort=new&t=year)
- r/dcsworld search: [refueling](https://www.reddit.com/r/dcsworld/search/?q=refueling&restrict_sr=1&sort=new&t=year)
- Eagle Dynamics forum search: [air-to-air refueling](https://forum.dcs.world/search/?q=air-to-air%20refueling&quick=1)

The Reddit endpoints blocked anonymous automated page retrieval from this run's network, so the URLs above are durable live discussion searches rather than invented individual thread citations.

## Privacy

All state remains in the browser's localStorage. Nothing is transmitted.
