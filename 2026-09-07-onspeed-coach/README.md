# On-Speed Coach

An offline, responsive F/A-18C approach-cue trainer for DCS World. It helps a pilot separate three problems that are often mixed together during landing configuration: aircraft configuration, angle of attack, and flight path. The app is intentionally cue-led rather than speed-led because approach speed changes with aircraft weight.

## Use

1. Open `index.html` directly in a browser; no server, account, or network connection is required.
2. In **Observe the jet**, select the landing configuration, AOA indexer cue, velocity-vector relationship to the E-bracket, flight-path trend, and current stick pressure.
3. Follow the ordered diagnosis. Reconfigure the inputs as the aircraft settles.
4. Add an optional note and log the observation. A clean run requires gear/full flaps, on-speed AOA, centered bracket, stable path, and relaxed stick pressure.
5. Use **Quick drill** to rehearse control-role decisions. Export the last 30 observations as JSON or print the current brief and log.

Selections, drill score, and the practice log persist in browser `localStorage`. **Reset** resets the current observed state but preserves the log and score; **Clear log** removes only observations.

## Assumptions and limits

- This is a training aid for the DCS F/A-18C simulation, not real-world flight instruction.
- The model uses the cockpit AOA indexer and E-bracket as decision cues. It does not reproduce cockpit artwork or aircraft dynamics.
- The coaching contract is: configure first; trim toward hands-off on-speed AOA; once stabilized, use power primarily for flight path; use brief stick inputs to control transients.
- It deliberately gives no fixed approach airspeed or exact trim duration. Aircraft weight, state, and pilot technique affect those values.
- Confirm procedures against the current Eagle Dynamics manual after DCS updates.

## Community signal

Accessed **2026-09-07**:

- A recent r/dcsworld beginner discussion describes being overwhelmed by DCS, struggling to make smooth turns, and seeing the F/A-18C dip after selecting gear and full flaps while trim appears ineffective. That specific confusion—what to learn and which control solves which approach problem—drove this cue-diagnosis trainer: <https://www.reddit.com/r/dcsworld/comments/1n7l6vr/another_noob_overwhelmed_a_discussion/>
- A recurring Eagle Dynamics forum thread captures the same failure mode: the E-bracket appears displaced after gear/flaps, pilots chase it, and the aircraft then drops rapidly. Replies emphasize controlling the configuration transient, trimming to on-speed AOA, and using power for flight path: <https://forum.dcs.world/topic/180025-fa-18c-carrier-landingrecovery-pro-tips-wanted/page/3>
- Eagle Dynamics’ current F/A-18C guide is the authoritative module reference used to constrain terminology and the simulated-aircraft scope: <https://www.digitalcombatsimulator.com/en/downloads/documentation/dcs-hornet_early_access_guide_en/>

## Design note

The artifact uses a **Configure** surface: observations and validation lead, with a compact instrument cue model beside an ordered diagnosis. It avoids a marketing hero, generic feature cards, decorative statistics, remote fonts, and runtime dependencies.
