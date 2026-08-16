# Bindline

Bindline is a self-contained, offline DCS World control-map workbench. It turns an overwhelming command list into a mission-first control plan, then helps you rehearse that plan before entering the cockpit. It does **not** read, generate, or modify DCS `.lua` input files; it is a planning and verification companion that works directly from `index.html`.

## Use

1. Open `index.html` in a modern browser. No server, account, build step, or internet connection is required.
2. Rename the profile for the aircraft, seat, mission, and hardware combination you are mapping.
3. In **Map**, select a command and then select a physical control slot. Use the pencil button on a slot to rename it to the exact button, hat direction, axis press, or shifted layer on your hardware.
4. Filter the queue by phase, add commands using the exact labels shown in DCS, and clear or move assignments as needed. Duplicate physical-control labels are flagged.
5. In **Rehearse**, run a ten-call eyes-out recall drill against the current mapped controls.
6. In **Preflight**, complete the six checks inside DCS before treating the paper plan as ready.
7. Use **Print map** for a physical reference and **Export** for a portable JSON backup. Import restores that Bindline backup later.

The workbench autosaves the current profile, checklist, and best drill score in browser `localStorage`. Browser storage is local to the file URL and browser profile, so export JSON before clearing browser data or moving between machines.

## Important assumptions

- Starter commands are an editable, airframe-agnostic planning set—not a claim that every DCS module uses identical command names or control logic.
- DCS remains the source of truth for bindability, modifiers, axis tuning, command names, and profile export. Verify every intended input in the loaded cockpit.
- Bindline's duplicate warning compares the text labels assigned to its slots. It cannot detect collisions or red-exclamation errors inside DCS.
- A control map should be specific to an aircraft/seat and ideally to a mission role; export one JSON file per profile.
- The app intentionally avoids automatic `.lua` generation so it remains offline, portable, and safe to open from Dropbox via `file://`.

## Community signal

Accessed **2026-08-16**:

- [r/hoggit — “I built a DCS binding tool that drags commands onto a picture of your stick — X-56 for now” (2026-08-11)](https://www.reddit.com/r/hoggit/comments/1vlipkh/) reports that DCS binding can feel daunting and demonstrates current interest in visual mapping.
- [r/hoggit — “Struggling with Hotas key binding” (2026-04-08)](https://www.reddit.com/r/hoggit/comments/1sfplk0/) describes mental overload from the number of possible bindings and uncertainty about which controls matter.
- [r/dcsworld — “Lost all of my Thrustmaster Warthog Hotas settings on F-14A/B and F-14BU after getting the BU Mod” (2026-08-14)](https://www.reddit.com/r/dcsworld/comments/1voeio5/) describes missing profiles and red-exclamation conflicts after the F-14B(U) transition, reinforcing the need for an independent human-readable plan and backup.
- [r/dcsworld — “Tomcat HOTAS commands issue” (2026-08-03)](https://www.reddit.com/r/dcsworld/comments/1veo9ug/) describes recurring red-exclamation binding failures, reinforcing an explicit preflight check rather than assuming saved mappings still work.
- [r/dcsworld — “How do you play DCS as a VR pilot?” (2026-08-07)](https://www.reddit.com/r/dcsworld/comments/1vi0r9n/) and its [r/hoggit cross-post](https://www.reddit.com/r/hoggit/comments/1vi0q75/) are current signs that eyes-out control access remains a practical concern; this inspired the recall drill.

Together these discussions point to a recurring workflow problem: pilots need help deciding what deserves a reachable control, retaining that layout, and checking it after changes—not merely another exhaustive command list.
