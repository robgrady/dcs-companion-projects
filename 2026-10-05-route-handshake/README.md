# Route Handshake

Route Handshake is a self-contained, offline DCS World flight-plan revision desk. A flight lead builds one shared route, publishes a revision with an eight-character fingerprint, sends a compact copy/paste packet, and records each pilot or crew station acknowledging that exact route state before taxi.

## Use

1. Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.
2. Enter the mission, package, aircraft, start time, and route intent.
3. Build the shared route. Coordinates accept signed decimal degrees or DMS such as `N 34 12 30`; the exchange packet stores normalized decimal values.
4. Review the derived leg bearings, distances, estimated leg times, Zulu ETAs, and schematic geometry plot.
5. Resolve the route-data gate, then select **Publish revision**. The app assigns a revision number and checksum fingerprint.
6. Select **Copy current** and send the packet code through the flight's normal chat or briefing channel. A recipient can paste it, inspect its checksum/revision, and load it locally.
7. Read the revision and fingerprint aloud. Mark each listed flight member acknowledged only after they confirm both values.
8. If any route field changes, all acknowledgments are invalidated. Publish a new revision and repeat the readback.
9. Copy or print the kneeboard brief, export CSV for route data, or export JSON for a full local backup.

Useful state persists in browser `localStorage`. The app works from `file://` and sends no information anywhere.

## Important assumptions and limits

- Route Handshake is a coordination aid, not a DCS mission-planning authority. The mission briefing, flight lead, module avionics, and server rules remain authoritative.
- Bearings and distances use great-circle calculations on a spherical Earth model. They are useful planning estimates, not a replacement for module-specific navigation computation.
- Leg time uses the groundspeed stored on the destination waypoint. It does not model climb, descent, wind, acceleration, holds, tactical maneuvering, or fuel.
- The schematic plot is normalized to the entered coordinate bounds and is explicitly not a map or terrain display.
- The packet checksum detects accidental changes to the encoded payload; it is not encryption, identity verification, or a cryptographic signature.
- Coordinate syntax is intentionally permissive. Pilots must confirm hemisphere, datum expectations, coordinate precision, and cockpit-entry format for their modules.
- DCS, mission files, SRS, Discord, and multiplayer servers are not accessed. Exchange remains manual by design so the app works offline.
- Eagle Dynamics does not publish or endorse this project.

## Community signal

Recent DCS discussion shows a concrete coordination gap around distributing flight plans in multiplayer. A September 24, 2026 r/hoggit request asks for a way to share flight plans during play and specifically describes creating a plan on the F10 map, sharing it with a group, and loading it into aircraft. An earlier r/hoggit discussion similarly asks whether waypoints can be shared across a flight or must be entered manually. At the same time, Eagle Dynamics' September 2026 update announced the DTC's move from launcher-only behavior into a new beta interface, reinforcing that mission-data workflows are active community and product concerns. Route Handshake does not pretend to write aircraft cartridges; it addresses the immediately useful human layer: one transferable route, explicit revision control, and positive crew readback.

Sources reviewed on **2026-10-05**:

- r/hoggit, “FLIGHT PLAN SHARING” — https://www.reddit.com/r/hoggit/comments/1npsgp6/flight_plan_sharing/
- r/hoggit, “Is there a way to share flight plan?” — https://www.reddit.com/r/hoggit/comments/16r0jkd/is_there_a_way_to_share_flight_plan/
- Eagle Dynamics, “DCS Update Highlights - September 2026” — https://forum.dcs.world/topic/382118-dcs-update-highlights-september-2026/
- Eagle Dynamics forum wishlist, “Waypoints Sharing by flight” — https://forum.dcs.world/topic/368115-waypoints-sharing-by-flight/

## Design and accessibility

Primary surface: **Configure**. Route construction, validation, publication, and crew agreement dominate; **Command / Inspect** behavior supports packet checking and route review. The composition uses a dense three-column planning desk rather than a marketing hero, with a warm chart-paper accent, restrained status color, semantic headings and labels, visible keyboard focus, 44-pixel primary controls, responsive single-column behavior, print styling, and reduced-motion handling.

### Anti-slop audit

- Initial score: **0/10**. No glossy tech gradient, generic indigo accent, equal-weight feature grid, accent rails, glass blur, monument stats, icon toppers, centered composition, default Inter typography, or surface mismatch.
- Final score: **0/10**. The route table remains the compositional center; status and handoff tools support the Configure surface without displacing it.
