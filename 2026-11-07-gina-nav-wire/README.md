# Gina Nav Wire

**Gina Nav Wire** is a self-contained, offline analog-navigation rehearsal desk inspired by the DCS: G.91R development work. It turns a route into leg-by-leg wind-corrected headings, groundspeed, ETE, drift cues, an ADF-relative-bearing presentation, fix-correction rehearsals, and Morse-ident drills.

Open `index.html` directly in any modern browser. No server, account, network connection, package installation, or build step is required.

## Use

1. Enter true airspeed, magnetic variation, wind direction/speed, and the navigation source you intend to rehearse.
2. Define route points. Each row's course and distance describe the leg from that row to the next point.
3. Tune one of the editable ADF stations and verify its Morse ident in the station rack.
4. Start the navigation wire. Use the live elapsed/remaining timeline and move between legs with the buttons or arrow keys.
5. At a known fix, enter an observed true bearing and distance. Preview the correction before logging it.
6. Save locally, export a JSON backup, or print a compact route card.

Useful state is stored in browser `localStorage`. `Space` starts or pauses the wire; left/right arrow keys change legs when focus is not inside a form field.

## Important assumptions

- This is a **pre-release familiarization and planning aid**, not an official aircraft checklist, flight manual, or promise of final DCS module behavior.
- Wind calculations use a standard wind-triangle approximation: entered wind is **from** a true direction; route courses are true; displayed steering heading is wind-corrected magnetic heading after applying entered variation.
- The circular ADF presentation is a training abstraction derived from entered station bearing and calculated aircraft heading. It does not simulate signal propagation, cone of confusion, terrain masking, radio noise, or final module-specific instrument error.
- Public development material identifies the G.91R's PHI navigation system, DRA-12 Doppler/radar support, AD.722 ADF, TACAN, and navigation display work. The app deliberately avoids claiming an exact switch-by-switch cockpit procedure.
- Frequencies, bearings, ranges, routes, and stations shipped in the app are editable training examples, not real-world navigation data.
- No telemetry is read from DCS; all observations and corrections are entered by the user.

## Community signal and current module context

Research accessed **2026-11-07**:

- Eagle Dynamics' **31 October 2026 newsletter** reported continued DCS: G.91R development, described the PHI navigation system, DRA-12 navigation radar/Doppler support, AD.722 ADF coverage from 200–1700 kHz, TACAN integration, and ongoing navigation-display work. That public detail made analog-navigation familiarization a timely companion category: https://www.digitalcombatsimulator.com/en/news/newsletters/c230ab4686360b86c9b6bb645e9cf144/
- A recent r/hoggit discussion on planning a long-term return to DCS asked for perspective on the simulation's current state and highlighted interest in renewed participation after time away. A no-install, pre-release familiarization desk serves that returning-pilot pattern without requiring module ownership: https://www.reddit.com/r/hoggit/comments/1orhm2c/what_is_the_state_of_dcs_in_2025/
- A recent r/hoggit thread reported unexpectedly long DCS loading behavior. This reinforced the choice to make the tool entirely offline and dependency-free rather than adding another service, account, or build chain to a DCS session: https://www.reddit.com/r/hoggit/comments/1nu2b8k/why_does_dcs_take_so_long_to_load/
- Current community discussion around incoming aircraft also continues to emphasize learning resources and practical pre-release preparation; the official G.91 systems detail above was the strongest distinct signal not already represented in this repository's project index.

## Privacy and portability

All data remains in the browser on the local machine unless the user explicitly exports a JSON file. There are no external scripts, fonts, trackers, APIs, or runtime dependencies.
