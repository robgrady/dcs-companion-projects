# Cargo Witness

Cargo Witness is a self-contained, offline DCS World logistics proof desk for recording a cargo manifest, capturing whole-manifest checkpoints, marking the first observable cargo discrepancy, and producing a compact evidence packet for server administrators or bug reports. It runs directly from `index.html` with no server, installation, network access, or external runtime dependencies.

## Why this exists

Recent DCS community discussion has again centered on logistics sorties being undermined by cargo that disappears, becomes unavailable for unloading, desynchronizes, or is destroyed without an obvious pilot action. The useful response is not another speculative root-cause checklist: it is a disciplined client-side witness record that says what cargo was expected, when it was confirmed aboard, when it was last stable, and what the client observed at the first break.

## Use

1. Open `index.html` directly in a modern browser.
2. Enter the mission/server, airframe, and crew or callsign.
3. Add every cargo item using its exact in-game object name, load type, weight, and intended destination.
4. Start the sortie clock and press **Briefed** before loading.
5. Update each cargo status and press the checkpoint buttons as the sortie progresses: **Loaded**, **En route**, **On station**, and **Delivered**.
6. Use **Mark stable** after meaningful proof points. If cargo disappears or cannot be unloaded, use **Mark cargo loss** immediately, then add the visible symptom and context.
7. Copy the proof packet, export the full JSON record, or print the report.

Useful state is stored in browser `localStorage`. Starting a new sortie replaces the active local record, so export important evidence first.

## Assumptions and limits

- Cargo Witness records what the user can observe; it does not read DCS telemetry, mission files, tracks, logs, or server state.
- A recorded discrepancy is evidence of an observed state transition, not proof of the underlying cause.
- Cargo names should match DCS or server naming exactly. Duplicate names are allowed but warned against because they weaken report precision.
- Status and checkpoint accuracy depend on the operator recording evidence promptly.
- The CH-47F guide documents external cargo selection through the communications menu and identifies cargo by Mission Editor object name and weight; it also describes the normal hook-release sequence. Cargo Witness uses those observable identifiers without attempting to replace the aircraft procedure.

## Community signal and references

Accessed 2026-11-13:

- Reddit r/hoggit, “DCS has a structural dependency issue” (2026-11-10). A highly active discussion identifies disappearing, desynchronized, and terrain-spawned cargo as recurring logistics-breaking behavior affecting transport gameplay: https://www.reddit.com/r/hoggit/comments/1xsmnrp/dcs_has_a_structural_dependency_issue/
- Eagle Dynamics Forums, “Loaded cargo gets randomly destroyed in MP (no track file yet)” (opened 2026-07-05). Reports describe cargo becoming destroyed or unavailable in multiplayer in both CH-47F and C-130J-30 operations: https://forum.dcs.world/topic/389921-loaded-cargo-gets-randomly-destroyed-in-mp-no-track-file-yet/
- Reddit r/dcs, “Multiplayer Server Desyncs when anyone interacts with cargo” (2025-09-05). A server group reports severe multiplayer divergence associated with vanilla cargo interactions: https://www.reddit.com/r/dcs/comments/1n8qs5t
- Eagle Dynamics, DCS CH-47F Early Access Guide. The guide describes cargo discovery by Mission Editor name and weight, the two-kilometer cargo list, sling-load pickup, and normal release workflow: https://www.digitalcombatsimulator.com/upload/iblock/0fd/n8rej5yziyy44qo42m81aluvij05fsk0/DCS%20CH-47F%20Early%20Access%20Guide%20EN.pdf
- Eagle Dynamics, “CH-47F Development Report” (2026-04-17). ED stated that multi-point sling loading was a forthcoming development focus, reinforcing active work and attention around transport operations: https://www.digitalcombatsimulator.com/en/news/newsletters/b15d470095084f8dbb31c82d4bb90acf/
- Reddit r/dcsworld, DCS 2.9.30.28738 changelog repost (2026-10-06). The cited core fixes included dynamic cargo not being created and unload-list population, showing cargo-system defects remained a current patch concern: https://www.reddit.com/r/dcsworld/comments/1wzczxd/20261006_dcs_293028738_change_log/

## Design posture

This is an **Operate** surface: the active manifest, checkpoint controls, event wire, and incident output carry the hierarchy. It intentionally avoids a marketing hero, generic feature tiles, ornamental gradients, glass effects, and invented operational metrics.
