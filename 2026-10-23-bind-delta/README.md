# Bind Delta

Bind Delta is a self-contained, offline comparator for DCS World control-profile (`.diff.lua`) files. It is aimed at pilots moving bindings between aircraft variants, modules, devices, or installations—especially the F-14A/B to F-14B(U) transition—who want to see which custom overrides transferred before launching a sortie.

## Use

1. Open `index.html` directly in a modern browser. No server or installation is required.
2. Drop a known-good source `.diff.lua` profile into the left side.
3. Drop the target profile for the same physical device into the right side.
4. Review **Missing**, **Target only**, **Changed**, and **Matched** commands. Search by command, internal ID, or button; filter axes separately from buttons/keys.
5. Export a tab-separated text audit or print the filtered comparison.
6. Make actual binding changes in DCS Controls, not in this app.

The **Load demo** button supplies a small synthetic Tomcat comparison so the complete workflow can be tested without personal files. The app remembers loaded profile text locally in that browser via `localStorage`; nothing is transmitted.

## Important assumptions and limits

- A DCS `.diff.lua` records differences from module defaults, not a complete control map. “Missing” means the source override is absent from the target file; the target module may still provide a usable default.
- Commands are matched using their DCS section (`axisDiffs` or `keyDiffs`) and internal command ID. A changed ID is treated as a different command even if the display names look alike.
- The parser targets standard DCS input-profile table structure and reads command names plus `added`/`removed` key values. It does not execute Lua.
- Compare profiles for the same physical device. Joystick, throttle, pedals, keyboard, and button boxes normally have separate files.
- Back up `Saved Games\DCS\Config\Input` before changing or importing profiles. Modifier device IDs can also require attention after hardware or PC migration.
- This is an independent community utility and is not affiliated with Eagle Dynamics or Heatblur Simulations.

## Why this project

Recent community traffic showed a concrete, repeated binding-migration problem rather than a hypothetical need:

- A July 22, 2026 r/hoggit thread about upgrading to the F-14B(U) drew pilots who dreaded rebinding, discussed loading old `.diff.lua` files, asked what happens to controls that no longer exist, and warned about unexpected axis assignments. Accessed 2026-10-23: https://www.reddit.com/r/hoggit/comments/1v3s94d/quick_tip_for_anyone_upgrading_from_the_f14_to/
- A July 24, 2026 r/dcsworld discussion reported reset Thrustmaster HOTAS bindings and no ready-made control preset after installing the F-14B(U). Accessed 2026-10-23: https://www.reddit.com/r/dcsworld/comments/1v5e0ao/how_are_all_of_you_liking_the_f14_bu/
- An October 12, 2026 r/dcsworld PSA described bindings becoming unusable after moving the DCS Input folder because device IDs in `modifier.lua` were stale, and specifically pointed users to `reformers` entries in old `.diff.lua` files. Accessed 2026-10-23: https://www.reddit.com/r/dcsworld/comments/1x3yk4r/psa_when_you_move_dcs_configinput_folder_to_a_new/
- The Eagle Dynamics F-14B(U) forum stated that existing A/B bindings can be copied and B(U)-specific bindings then added, making a post-copy audit useful. Accessed 2026-10-23: https://forum.dcs.world/topic/390218-keybinding-compatibility/
- The July 22, 2026 DCS update introduced the F-14B(U), added hundreds of requested Tomcat bindings, and included input fixes—exactly the kind of large command-set change where a before/after comparator helps. Accessed 2026-10-23: https://www.reddit.com/r/hoggit/comments/1v3iofs/dcs_292826283_introducing_dcs_f14bu_by_heatblur/
- Heatblur’s current manual documents the F-14B(U) as a distinct upgrade variant with substantial system changes. Accessed 2026-10-23: https://f14.manuals.heatblur.se/f14bu.html

## Design and privacy

Bind Delta is an **Operate** surface: profile loading, exception scanning, and audit export dominate the composition. The palette and typography avoid generic neon-tech styling; status color is reserved for actionable comparison results. All HTML, CSS, and JavaScript are inline, all processing remains local, and there are no external runtime dependencies.
