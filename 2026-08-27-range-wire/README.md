# Range Wire

Range Wire is a self-contained, offline DCS World training-range pass sequencer. It turns a range brief into an ordered live wire of targets, delivery descriptions, attack headings, altitude gates, escape directions, restrictions, required radio calls, and pass notes—without inventing aircraft-specific weapon parameters.

## Use

1. Open `index.html` directly in any modern browser; no server, install, account, or network connection is required.
2. Enter the range/event, callsign, range frequency, and the mission's wind/weather note.
3. Add each planned pass using the limits and procedures from the mission briefing or squadron range SOP.
4. Click a queued pass to make it active. During the pass, tap each required call as it is transmitted, record notes, then complete the pass.
5. Reorder passes, print a compact range card, or export the complete wire as JSON. Import restores a previously exported wire.

The current wire persists in browser `localStorage`. All data stays local unless the operator explicitly exports a JSON file.

## Important assumptions

- Range Wire is a workflow aid, not a source of weapon envelopes, minimum safe altitudes, range boundaries, attack headings, or clearance. Those values must come from the current mission briefing, published range procedure, instructor, and applicable module documentation.
- The included first pass is a dry familiarization pass and deliberately says “Per mission brief” where no universal value is safe or accurate.
- Marking a radio call records cockpit workflow only; it does not transmit into DCS, SRS, or voice chat.
- Browser printing is intended for a conventional paper/PDF card. JSON is the editable backup format.

## Community signal (researched 2026-08-27)

- Eagle Dynamics forum discussion for **Digital Kneeboard Simulator (DCS Mission Card Creator)**: the author reports that the `RANGE PLAN` tab is “easily the most common question,” while users ask for a completely filled example and simplified kneeboard layouts. This supplied the strongest direct signal for a smaller, self-explaining range-plan tool rather than another broad mission planner: <https://forum.dcs.world/topic/377954-digital-kneeboard-simulator-dcs-mission-card-creator/>
- Eagle Dynamics forum request to put radio and ADF information on the kneeboard: replies emphasize that cockpit access to programmed frequencies would be “HUGE.” That informed the persistent range-frequency header and live radio-call wire: <https://forum.dcs.world/topic/379757-wish-add-radio-and-adf-channels-to-kneeboard/>
- Stormbirds’ 2026-08-21 DCS news recap highlights the community-built Digital Kneeboard Simulator and its route, loadout, comms, threats, targets, DTC, and debrief workflow, confirming active interest in practical mission cards and post-flight records: <https://stormbirds.blog/2026/08/21/dcs-f-100d-post-launch-progress-eight-new-currenthill-assets-and-new-kneeboard-system/>

All URLs were accessed 2026-08-27.
