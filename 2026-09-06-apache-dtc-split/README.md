# Apache DTC Split

A self-contained, offline allocation desk for planning the two mission files supported by the DCS: AH-64D Data Transfer Cartridge. It helps a crew decide which records belong in Mission A, Mission B, or both; checks each mission against the announced category capacities; identifies duplicate tactical labels; and creates a concise handoff for entry and verification in DCS.

## Use

1. Open `index.html` directly in a modern browser. No server, installation, account, or network connection is required.
2. Rename **Mission A** and **Mission B** for the primary/contingency task or two geographic sectors.
3. Stage each mission-relevant point, control measure, target/threat, route, line, area, zone, preset, or message.
4. Assign the record to A, B, or **Both**. A shared record consumes one category slot in each mission.
5. Watch the capacity meters and **Crew review** panel. Filter the manifest to inspect either load.
6. Use **Crew handoff** for a plain-text Pilot/CPG review, **Export JSON** for backup or transfer, and **Print brief** for paper/PDF output.

State is saved in the browser with `localStorage`. Import replaces the current desk only after confirmation. The app does not modify DCS files and does not claim to generate a cartridge compatible with DCS.

## Assumptions and limits

The app models Eagle Dynamics' published initial AH-64D DTC capacities per mission: 50 Waypoint/Hazard points, 49 Control Measures, 50 Target/Threat points, 10 routes, 15 battlefield lines, 12 engagement areas, 8 Priority Fire Zones, 8 No Fire Zones, 10 ADF presets, 10 COM presets, and 10 pre-composed text messages. Eagle Dynamics describes two separately stored missions, each with its own 149-point database and the other listed capacities. This planner treats records assigned to **Both** as separately consuming capacity in A and B. It is a pre-entry allocation/review aid, not authoritative avionics documentation; crews should verify labels, types, coordinates, and the current DCS manual before flight.

## Why this project now

Accessed **2026-09-06**:

- [Eagle Dynamics — DCS: AH-64D Improvements (2026-08-07)](https://www.digitalcombatsimulator.com/en/news/2026-08-07/) announced the helicopter's expansive DTC feature set, exact capacities, and dual-mission use for contingency tasks or splitting large operating areas.
- [DCS 2.9.29.27278 changelog (2026-08-26)](https://www.digitalcombatsimulator.com/en/news/changelog/release/2.9.29.27278/) documents the AH-64D DTC release-era update and updated manual coverage.
- [r/hoggit — DCS Mission Planner by Combined Ops, DTC development update](https://www.reddit.com/r/hoggit/comments/1w8078r/dcs_mission_planner_by_combined_ops_dtc/) showed active community demand for mission-planning support and specifically reported AH-64D planning work across flight plans, control measures, targets/threats, lines, areas, NFZs, and PFZs.
- [ED Forums — verify datalink setup with Mission Editor and DTC](https://forum.dcs.world/topic/391993-we-need-a-way-to-verify-datalink-setup-both-with-standard-me-and-with-dtc/) showed a current need for explicit preflight verification of DTC-configured data rather than assuming configuration is correct.

Those signals favor a focused allocation and crew-review instrument rather than another general mission-card builder.

## Privacy

Everything runs locally. Project data stays in the browser unless the user explicitly exports or prints it.
