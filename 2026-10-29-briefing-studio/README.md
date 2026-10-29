# Briefing Studio

**Briefing Studio** is a self-contained, offline authoring companion for building a concise DCS World mission brief before moving the final material into the simulator. It combines a sequenced page editor, local image board, route/threat/target/friendly markers, a full-screen rehearsal deck, completeness gates, and a portable text/JSON handoff.

Open `index.html` directly in a modern browser. No server, installation, account, network connection, or build step is required.

## How to use it

1. Set the mission name, aircraft/role, map/area, and package/callsign.
2. Edit the starter sequence: Situation, Objective, Route, Threats, Comms, and Contingency. Add, delete, or reorder pages as needed.
3. Load a local map, Mission Editor screenshot, target image, or diagram on any page. Images are downscaled in the browser and stored locally; they are never uploaded.
4. Choose a mark type, enter a short label, select **Arm click**, then click the visual. Route marks connect in placement order.
5. Open **Rehearse** and use the arrow keys or deck controls to walk the flight through the brief. The side panel shows missing core answers.
6. Open **Package** to copy, download, or print the text handoff. Export JSON to preserve the complete project, including local images and marks.

## Important assumptions and boundaries

- Briefing Studio is a content-authoring and rehearsal tool. It does not edit `.miz` files, inspect a mission, or import pages directly into DCS.
- All coordinates, frequencies, ROE, threat claims, imagery, and operational details are user-authored and must be verified in the installed DCS build and the actual mission.
- The starter sequence is a communication scaffold, not a mandatory military briefing format. Pages can be renamed, reordered, or replaced.
- Local images are converted to JPEG and limited to 1600×900 before storage. A browser may still reach its local-storage quota after several image-heavy briefs; export JSON before clearing data.
- Browser clipboard permissions vary for `file://` pages. Download and print remain available when direct copy is blocked.
- Reset deletes the browser's saved working state for this app.

## Community signal and sources

Accessed **2026-10-29**:

- Eagle Dynamics announced **Mission Briefing 2.0** on October 28, 2026, highlighting expanded briefing information and support for custom mission images. This created a timely need for a disciplined way to prepare the content and visual sequence before authoring the final mission brief: https://www.digitalcombatsimulator.com/en/news/2026-10-28/
- A recent r/hoggit question asks how to add images or backgrounds to DCS briefings, showing practical friction around briefing visuals rather than a lack of interest in them: https://www.reddit.com/r/hoggit/comments/1p43xpk/briefing_backgroundsimages_help/
- A recurring r/hoggit discussion asks whether mission briefings have become a thing of the past, with comments emphasizing that players often skip or fail to absorb them. That signal favors shorter pages, one decision per page, and rehearsal rather than a single wall of text: https://www.reddit.com/r/hoggit/comments/1kgoq3h/mission_briefings_a_thing_of_the_past/
- A r/hoggit discussion about Mission Editor improvements explicitly includes more dynamic briefing information among desired mission-authoring capabilities: https://www.reddit.com/r/hoggit/comments/1m61sgm/what_mission_editor_improvements_would_you_like_to/

Briefing Studio answers the signal without pretending to replace DCS: it helps a mission author shape a readable sequence, mark locally supplied visuals, test whether the flight can retell the plan, and carry a compact handoff into the native briefing workflow.

## Design posture

This is primarily a **Configure** surface, with **Explore** as a secondary surface for image annotation and deck rehearsal. The composition uses a page sequence, selected-page editor, and large visual board instead of a marketing hero or dashboard. A muted paper-and-operations palette separates authoring controls from the presentation artifact.

**Anti-slop audit before repair:** 0/10. No tech gradient, generic indigo, equal-weight feature grid, accent rail, glass blur, monument statistic, icon topper, center stack, default Inter/system typography, or surface mismatch fired. **Final audit:** 0/10; no compositional repair was required.
