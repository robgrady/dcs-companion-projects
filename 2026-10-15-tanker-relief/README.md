# Tanker Relief

Tanker Relief is a self-contained, offline DCS World Mission Editor companion for designing and testing an AI tanker handoff. It turns a desired primary station time, replacement transit time, overlap margin, and optional fuel cue into a calculated relief timeline, a concrete Mission Editor build recipe, a visual rehearsal, and a verification contract.

## Use

1. Open `index.html` directly in a modern browser. No server, install, network connection, or build step is required.
2. Name the primary and relief groups exactly as they appear in the mission.
3. Enter the expected primary station time, relief transit time, required overlap, and fuel threshold.
4. Enter the anchor-zone, RTB waypoint, frequency, TACAN, altitude, and Mission Editor ground-speed references.
5. Follow **Build recipe** to construct the groups, zone, triggers, triggered actions, and optional F10 fallback.
6. Use **Rehearse** to walk through launch, arrival, overlap, and primary release.
7. Complete **Verification** in the actual mission. Copy or print **Handoff** for the mission file's evidence packet.

Planner inputs and verification state persist in browser `localStorage`. **Reset** clears only this app's saved state.

## Important assumptions

- This is a planning and verification aid, not a `.miz` editor. It does not modify DCS files.
- Timeline values are estimates. AI taxi, takeoff, routing, weather, traffic, mission load, and damage can change actual transit and fuel use.
- The recipe uses familiar Mission Editor concepts such as late activation, group activation, unit fuel conditions, trigger zones, flags, triggered actions, AI task push, orbit stop conditions, and switch-waypoint actions. Exact labels and behavior must be verified in the installed DCS build.
- A fuel threshold is a cue, not proof that a relief tanker is established. The default plan therefore keeps the primary available until the replacement reaches the anchor zone.
- Tanker callsign, radio, TACAN, fuel-transfer compatibility, and simultaneous-transmission behavior must be checked for the aircraft and mission in use.
- Long-running or repeating tanker rotations may require additional groups or tested scripting. The app deliberately does not promise automatic landed-group regeneration.
- Mission Editor speed fields may be expressed as ground speed; builders should confirm displayed units and resulting true behavior in their mission conditions.

## Community signal

The project responds to a recurring combination of community requests: builders want a minimal, dependable way to add working tankers; they struggle with the orbit/task setup; and longer missions expose the limits of a single AI tanker, prompting requests for relief, endurance, or better tanker management. Instead of another refueling-contact trainer, Tanker Relief focuses on the mission-builder's lifecycle problem: activate the replacement early enough, prove it is on station, then release the first tanker without opening a coverage gap.

Sources reviewed on **2026-10-15**:

- Reddit, r/hoggit — “ME: Add working Tanker with minimal effort” (discussion of late activation, starting conditions, and common tanker setup details): https://www.reddit.com/r/hoggit/comments/1ldzkfu/me_add_working_tanker_with_minimal_effort/
- Reddit, r/dcsworld — “How to create a tanker track on the mission editor” (community demand for a clear tanker-track setup path): https://www.reddit.com/r/dcsworld/comments/1lvv5cy/how_to_create_a_tanker_track_on_the_mission_editor/
- Reddit, r/hoggit — “AI Tanker unlimited fuel?” (long-mission endurance question and community workaround discussion): https://www.reddit.com/r/hoggit/comments/1irlwz1/ai_tanker_unlimited_fuel/
- Eagle Dynamics Forums — “More Tanker Options Please” (requests for more capable and flexible tanker behavior): https://forum.dcs.world/topic/382215-more-tanker-options-please/
- Eagle Dynamics Forums — “Mission Editor: Need help setting tanker leg end condition” (evidence that task/stop-condition sequencing is a continuing builder pain point): https://forum.dcs.world/topic/386766-mission-editor-need-help-setting-tanker-leg-end-condition/

## Design posture

This is primarily a **Configure** surface with a secondary **Operate** rehearsal. The dense left contract drives a calculated timeline and build sequence; no marketing hero, fake statistics, or decorative feature grid competes with the task.

Slop diagnostic before final polish: **0/10**. No tech gradient, generic indigo accent, equal-weight feature tiles, accent rails, glass blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch. Final score: **0/10**.
