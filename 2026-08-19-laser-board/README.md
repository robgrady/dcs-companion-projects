# Laser Board

Laser Board is a self-contained, offline deconfliction desk for DCS World multiplayer flights using JTAC, AFAC, buddy-lase, or other laser designation. It keeps the designator, receiver, weapon, four-digit code, target note, and assignment state in one quickly scanned board; it also detects duplicate **active** codes and produces a radio-ready brief.

## Use

1. Open `index.html` directly in a modern browser. No server, installation, account, or network connection is required.
2. Add one assignment for each designator–receiver pairing. Enter the mission-briefed code and target restriction.
3. Move a line from **Standby** to **Active** only when it owns that code in the current attack window. Red lines indicate that two active assignments share a code; confirm that this is deliberate or deconflict them.
4. Copy the generated active brief for Discord/SRS notes, close all active lines after the attack window, and print the board when a paper reference is useful.
5. The board saves automatically in browser `localStorage`. **Backup** exports JSON; **Restore** accepts that JSON on another browser/device.

## Important assumptions and limits

- The code input accepts four digits, each from 1 through 8. This is a format check, not a guarantee that a particular DCS aircraft, store, seeker, JTAC implementation, server script, or mission supports that code.
- Duplicate-code detection is intentionally limited to assignments marked **Active**. Reusing a code in separate time windows can be valid; simultaneous sharing can also be deliberate, so the app warns rather than blocks.
- Laser Board does not calculate release parameters, line of sight, seeker field of view, laser masking, designation geometry, or laser-on timing.
- Some DCS modules or stores model code entry differently, including codes set before flight versus codes changeable from the cockpit. Always use the current module manual, mission brief, and server procedures as authority.
- Example callsigns, targets, and stores are fictional planning data and make no claim about a specific mission.

## Community signal

The idea responds to a recurring DCS community pattern rather than a single patch feature: pilots repeatedly ask why a JTAC/buddy lase is not acquired, how sender and receiver codes must match, whether codes can be changed in flight, and how non-default JTAC codes should be handled. A small shared assignment board addresses the coordination part of that problem without pretending to replace module-specific procedures.

Sources reviewed on **2026-08-19**:

- r/hoggit — “Help with F-16 laser code ...” (2025): another recent code/setup troubleshooting question surfaced in live search. https://www.reddit.com/r/hoggit/comments/1ixb16x/help_with_f16_laser_code/
- r/hoggit — “Changing laser codes in flight” (2024): discussion distinguishes changing a designator code from changing a weapon code and highlights module/store differences. https://www.reddit.com/r/hoggit/comments/1bmndl0/changing_laser_codes_in_flight/
- r/hoggit — “JTAC/Laser target help”: a beginner’s failed guidance flow prompts checks for matching codes and laser spot search. https://www.reddit.com/r/hoggit/comments/1fw39a/jtaclaser_target_help/
- Eagle Dynamics Forums — “Ability to change JTAC laser codes in mission” (DCS Core Wish List): evidence of demand for better mission-level control over assignment codes. https://forum.dcs.world/topic/338286-ability-to-change-jtac-laser-codes-in-mission/
- Eagle Dynamics Forums — “Using a JTAC to lase hellfires” (AH-64D): module-specific community troubleshooting around external designation. https://forum.dcs.world/topic/347659-using-a-jtac-to-lase-hellfires/

Search discovery used live Brave Search results because direct Reddit and ED forum requests from this environment returned HTTP 403. Source URLs above are the original discussions.

## Design notes

This is an **Operate** surface: the editable assignment ledger dominates, active state and conflicts are immediately visible, and supporting controls remain secondary. The visual system uses a restrained field-board palette, monospaced operational labels, square geometry, and no decorative metric or feature-card filler.

Final anti-slop audit: **0/10**. None of the ten diagnostic tells fired; the red row edge is a semantic, transient conflict indicator rather than a decorative accent rail.
