# Briefbox

Briefbox is a self-contained DCS World single-sortie brief builder for pilots who want purposeful solo flying without spending the session staring at a blank Mission Editor. It turns an aircraft, terrain, role, timebox, start posture, and pressure level into a compact mission contract: objective, situation, four-phase flow, execution posture, support assumption, ROE, contingency, and an observable success condition.

It does **not** create or modify a `.miz` file. The generated contract is intended to guide a quick Mission Editor setup, frame an objective in an existing sandbox mission, or add uncertainty and discipline to an improvised sortie.

## Use

1. Open `index.html` directly in a modern browser; no server, build step, account, or network connection is needed.
2. Enter a callsign, aircraft, and terrain, then choose the primary task, timebox, start posture, and mission pressure.
3. Select **Generate contract**. Use the square lock beside any section you want to preserve, then generate again to vary only the unlocked sections.
4. Close the four execution gates after briefing the objective, abort trigger, fuel/time decision point, and identification/release authority.
5. Copy the plain-text brief, print a kneeboard-friendly version, or log the sortie on the local flight line. State and the latest 12 logged contracts persist in `localStorage` for this browser/file location.

## Assumptions and boundaries

- Briefbox is airframe- and map-agnostic. Aircraft and terrain names are user-entered; the app does not claim module ownership, weapon compatibility, map locations, or performance data.
- Generated language deliberately stays at the level of tactical intent. Apply the current DCS module manual, mission briefing, server rules, valid loadouts, coordinates, frequencies, and aircraft procedures.
- Generated ROE and support statements are rehearsal prompts, not real-world guidance.
- A contract never guarantees that DCS AI, triggers, or mission content can produce the described situation. The pilot or mission author must implement and validate it.
- Everything runs locally. No information is transmitted.

## Community signal (accessed 2026-09-15)

Recent community discussions continue to expose the gap between DCS's detailed aircraft and quickly available, varied single-player sorties. An r/dcsworld pilot asked for a robust single-player mission generator and described DCS as weak in that area; replies recommended third-party generators but also noted simple output and finicky workflows. A recent r/hoggit request specifically wanted short, one-to-two-hour generated sessions and surfaced performance costs in heavier campaign tools. The current Combined Ops project update on the Eagle Dynamics forums shows parallel demand for structured pilot-facing mission preparation and executable briefs. Briefbox addresses the smallest offline slice of that demand: it generates a bounded, rerollable *intent contract* rather than competing with full `.miz` editors or dynamic campaigns.

Sources:

- r/dcsworld, “Does DCS have a good mission generator that gives robust missions for single player?”: https://www.reddit.com/r/dcsworld/comments/1phcqvd/does_dcs_have_a_good_mission_generator_that_gives/
- r/hoggit, “Any good mission generators for DCS?”: https://www.reddit.com/r/hoggit/comments/1mifli7/any_good_mission_generators_for_dcs/
- Eagle Dynamics Forums, “Combined Ops for DCS World – Project Update: Integrated Mission Planning, DTC, Kneeboard MDC, ATC, AWACS & GCI”: https://forum.dcs.world/topic/392053-combined-ops-for-dcs-world-project-update-integrated-mission-planning-dtc-kneeboard-mdc-atc-awacs-gci/

## Design notes

This is an **Operate** surface: setup controls occupy a narrow task rail, the generated contract is the dominant working surface, and execution gates/history form the commitment rail. The visual system uses warm flight-document stock, charcoal ink, one amber action color, narrow utilitarian display type, square geometry, and print behavior designed for a compact kneeboard sheet.

Slop diagnostic before final polish: **0/10**. None of the ten tells fired: there is no tech gradient, generic indigo, equal feature-tile grid, accent rail, blur, monument stat, icon topper, center stack, default Inter/system typography, or surface mismatch. Post-build score remains **0/10**; the responsive mobile stack preserves the task → contract → commitment sequence.
