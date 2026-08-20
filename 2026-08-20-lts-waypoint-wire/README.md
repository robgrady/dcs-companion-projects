# LTS Waypoint Wire

An offline F-14B(U) RIO workbench for staging LANTIRN target fixes before entering or checking them in the aircraft. It parses decimal and degrees–minutes–seconds coordinates, normalizes them for readback, tracks LTS designation capacity, warns on negative HAE, calculates true bearing/range between sequential fixes, builds a Pilot–RIO crew brief, and includes short integrity drills.

## Use

1. Open `index.html` directly in a modern browser; no server, account, package, or network connection is required.
2. Enter a fix identifier, source, latitude, longitude, and HAE altitude. Both signed decimal and DMS coordinates are accepted.
3. Review the integrity message, then add the fix to the wire. Select a row to inspect its next leg and crew readback; double-click a row (or press `E` while not typing) to edit it.
4. Reorder fixes with **Up/Down**, export/import a JSON backup, or print a compact route card. The wire and drill score persist in `localStorage`.
5. Treat every output as a planning/rehearsal aid. Verify coordinates, altitude, sequence, magnetic/true conventions, and aircraft behavior against the current DCS build and Heatblur manual before employment.

## Important assumptions and limits

- Bearings are great-circle **true** bearings; the app does not apply magnetic variation.
- Distances use a spherical-earth haversine estimate in nautical miles.
- The app treats an LTS-marked list as having 20 available designations. In line with the Heatblur manual, a further waypoint can be created but does not receive the LTS designation.
- Negative Height Above Ellipsoid (HAE) is not silently corrected. The app flags it because the Heatblur manual says a negative HAE calculated during LANTIRN waypoint creation may transfer an incorrect altitude and must be manually corrected in the CDNU.
- This is not a replica of the CDNU/PTID and does not teach switchology. It is deliberately a pre-entry integrity and crew-coordination tool.

## Why this project now

The F-14B(U) arrived in July 2026, and current community coverage is centered on learning its modernized navigation and precision-strike workflow rather than merely cataloging its feature list. Heatblur’s manual documents the practical LANTIRN/CDNU handoff details that can create mission errors: a 20-point LTS list, direct creation of flight-plan waypoints from target designations, and the negative-HAE transfer caution. The official ED forum FAQ and active community discussion around upgrade scope and the new precision-strike/navigation workload reinforce the need for a narrow rehearsal aid. Direct Reddit feeds for r/hoggit and r/dcsworld were queried during research but returned Reddit’s network-policy block from this environment, so no inaccessible Reddit claim is represented as evidence here.

### Sources reviewed (accessed 2026-08-20)

- Heatblur F-14 manual, **F-14B Upgrade**: https://f14.manuals.heatblur.se/f14bu.html
- Heatblur manual, **LANTIRN Targeting System** (waypoint list, designation transfer, HAE caution): https://f14.manuals.heatblur.se/f14bu/systems/lantirn/lantirn_targeting_system.html
- Eagle Dynamics forum, **DCS: F-14B(U) Frequently Asked Questions**: https://forum.dcs.world/topic/388826-dcs-f-14bu-frequently-asked-questions/
- Stormbirds, **The DCS: F-14B(U) pre-order begins** (article and community comment thread discussing upgrade scope and learning priorities): https://stormbirds.blog/2026/06/05/the-dcs-f-14bu-pre-order-begins/
- Simulation Daily, **New DCS World Update Introduces F-14B(U), Aircraft & Map Updates, and More** (22 July 2026 release signal): https://simulationdaily.com/news/dcs-world-update-f-14bu-tomcat/

## Privacy

All route data stays in the browser’s local storage unless you explicitly export it. The app has no analytics, external scripts, remote fonts, or runtime network requests.
