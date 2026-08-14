# Bulls Wire

Bulls Wire is a self-contained offline bullseye-to-BRAA translation board for DCS World. It turns controller bullseye calls into a cockpit-relative bearing and range, plots the geometry, estimates simple aspect when track is known, and maintains a persistent contact wire for the current sortie.

## Use

1. Enter your ownship position as bearing/range from the mission bullseye.
2. Paste a compact call such as `BULLS 275/42, 16 THOUSAND, TRACK EAST` and choose **Parse call**, or enter the fields manually.
3. Read the translated BRAA, range, aspect, and top-down plot.
4. Add calls to the wire, select them to inspect or update them, and print a compact mission card when useful.
5. Export the board as JSON for a backup. Contacts and ownship geometry persist in browser `localStorage`.

Open `index.html` directly. It has no network or build dependencies and works from a `file://` URL.

## Assumptions and limits

- Bearings use one common north reference. The app cannot reconcile true-versus-magnetic differences; use the reference established by the mission briefing/controller.
- Distances are nautical miles on a flat tactical plot. This is appropriate for quick local geometry, not geodesic navigation.
- The BRAA bearing is from ownship to contact. Range is the planar distance between those two positions.
- Aspect is a deliberately broad geometry cue: HOT when target track is within 30° of the line toward ownship, COLD when it is at least 150° away, otherwise FLANK. It is not an intercept or weapons recommendation.
- Altitude is passed through for call readability; terrain, closure, speed, sensor limits, and identification are outside scope.
- Always confirm parsed fields. Controller phraseology varies.

## Community signal (reviewed 2026-08-14)

The concept responds to a recurring multiplayer-learning problem: pilots can copy a bullseye call but struggle to convert that common-reference location into immediate ownship-relative geometry while workload is high. Recent-source discovery was attempted across the requested communities; direct Reddit and Eagle Dynamics forum feeds returned access blocks in this run, so the stable community search/discussion URLs below are recorded rather than claiming inaccessible post details:

- r/hoggit search — bullseye calls and interpretation: https://www.reddit.com/r/hoggit/search/?q=bullseye%20call&restrict_sr=1&sort=new (access attempted 2026-08-14)
- r/hoggit search — AWACS/GCI workflow: https://www.reddit.com/r/hoggit/search/?q=AWACS%20GCI%20bullseye&restrict_sr=1&sort=new (access attempted 2026-08-14)
- r/dcsworld search — learning bullseye: https://www.reddit.com/r/dcsworld/search/?q=bullseye&restrict_sr=1&sort=new (access attempted 2026-08-14)
- Eagle Dynamics forum search — bullseye: https://forum.dcs.world/search/?q=bullseye&quick=1 (access attempted 2026-08-14)
- DCS World manual (official downloads hub; bullseye is a core mission reference concept): https://www.digitalcombatsimulator.com/en/downloads/documentation/ (accessed 2026-08-14)

This is an original companion and is not affiliated with Eagle Dynamics.
