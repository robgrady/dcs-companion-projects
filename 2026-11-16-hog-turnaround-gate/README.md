# Hog Turnaround Gate

Hog Turnaround Gate is a self-contained, offline A-10C II post-repair navigation rebuild and proof desk for DCS World. It turns a risky “repair, restart, and hope” cycle into four observable phases: secure the aircraft, protect the repair event, rebuild navigation, and prove cockpit cues before taxi or weapon employment.

## Use

1. Open `index.html` directly in any modern browser; no server, account, network connection, or build step is required.
2. Name the sortie/slot and start the run timer when requesting repair.
3. Work the four phase tabs in order. Mark a task only when its condition has been observed.
4. Record the alignment readout exactly as shown in the cockpit. The app deliberately does not invent a numeric accept/reject threshold.
5. Set the four cockpit-evidence gates and mark any remaining symptoms.
6. Save an evidence run for local history, export all saved runs as JSON, or print a compact proof card.

State and saved runs remain in the browser via `localStorage` for this local file. Clearing browser site data, changing browsers, or moving to another machine does not transfer the history; use **Export JSON** first.

## Important assumptions

- This is a simulation companion, not an official checklist and not real-world aviation guidance.
- Cockpit switch actions and acceptable indications must come from the current Eagle Dynamics A-10C II manual and the user’s current checklist.
- The app uses a conservative first-break method: preserve the first bad cue, identify the earliest unproven gate, and avoid simultaneous fixes that destroy diagnostic evidence.
- “Ready” means only that the user marked every app gate and reported no active symptom. It does not replace normal start, taxi, weapons, server, or squadron procedures.
- The workflow is intentionally weapon-independent. It asks for a non-release plausibility check rather than prescribing a delivery profile.

## Why this exists

Recent DCS community discussions continue to show confusion between a valid alignment, a merely visible “ready” cue, GPS availability, TACAN indications, present-position errors after landing elsewhere, and weapon/navigation symptoms. The current signal is broader than one airframe: pilots frequently need a disciplined way to separate what they observed from what they assume, especially after shutdown, repair, rearm, or restart. Hog Turnaround Gate applies that recurring demand to the A-10C II while grounding its alignment language in the official module manual.

Sources reviewed on **2026-11-16**:

- r/dcsworld, “Does anyone know why my F-18 won’t fully align?” (2026-11-04). A recent discussion where a completed alignment, GPS reception under cover, and changing navigation indications were conflated: https://www.reddit.com/r/dcsworld/comments/1xnh43k/does_anyone_know_why_my_f18_wont_fully_align/
- Eagle Dynamics Forums, “INS Alignment after rearming” in the A-10C Warthog forum (2025-12-25). The thread shows how post-service alignment and stores-state symptoms are easily conflated, supporting a separate evidence gate for unrelated changes: https://forum.dcs.world/topic/383486-ins-alignment-after-rearming/
- r/dcsworld, alignment follow-up (2026-02-06). Replies distinguished a completed alignment from a moving TACAN indication, reinforcing the need to test independent cockpit cues: https://www.reddit.com/r/dcsworld/comments/1qx4bvs/update_i_have_followed_instructions_in_previous/
- r/hoggit, “How do you prevent the F-16’s INS drift?” (2025-11-11). The thread repeatedly separates seeing a ready indication from allowing the required alignment state to complete: https://www.reddit.com/r/hoggit/comments/1ou9vmo/
- r/hoggit, “F-18 HUD drifts to one side after a while” (2026-04-03). The discussion separates mission-era/GPS conditions from alignment and cue-caging questions, another example of why independent observations matter: https://www.reddit.com/r/hoggit/comments/1sb0j7g/f18_hud_drifts_to_one_side_after_a_while/
- Eagle Dynamics, **DCS: A-10C II Tank Killer Flight Manual**. The official manual documents EGI ground alignment, the requirement that the aircraft not move, alignment status indications, NAV-ready annunciation, and transition to NAV: https://www.digitalcombatsimulator.com/en/downloads/documentation/dcs-warthog_2_flight_manual_en/

## Design notes

This is primarily an **Operate** surface, with a secondary inspection function. Phase actions, evidence, and release state dominate; there is no marketing hero or decorative dashboard. The interface is responsive, keyboard accessible, printable, and respects reduced-motion preferences.
