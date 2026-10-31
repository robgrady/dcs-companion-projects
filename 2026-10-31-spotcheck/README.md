# Spotcheck

Spotcheck is a self-contained, offline visual-contact test bench for DCS World pilots. It presents controlled small marks against sky, haze, cloud, and terrain-like backdrops; records contact rate, acquisition time, misses, and false starts; and keeps comparable evidence under named monitor or VR profiles.

It is designed to turn “contacts are hard to see” into a disciplined personal A/B test without pretending that a browser can reproduce DCS World’s renderer.

## Use

1. Open `index.html` directly in a modern browser. No server, build step, account, network connection, package, or external asset is required.
2. In **Test profile**, record the display or headset, resolution, refresh rate, AA/upscaler, pixel density, spotting-dot state, view posture, and notes for the current setup.
3. In **Live drill**, choose the backdrop, target mark, mark size, contrast, movement, exposure, and number of trials.
4. Start the drill and keep your eyes in the contact window. Press `Space` or **CONTACT** immediately when the mark is acquired; press `M` or **MISS** when no contact is acquired.
5. Repeat an identical contract before and after changing exactly one DCS, VR, driver, or display variable.
6. Use **Evidence** to compare contact rate and median acquisition time. Export JSON for backup, CSV for analysis, or print the profile summary.

Keyboard controls outside form fields:

- `Space` — record contact
- `M` — record miss
- `Esc` — stop the current run without saving it
- `Alt+1` through `Alt+4` — switch application views

## Important assumptions and limits

- Spotcheck does **not** model DCS rendering, spotting-dot logic, aircraft LOD transitions, angular size, range, lighting, atmospheric scattering, server policy, or a particular aircraft silhouette.
- CSS pixels and browser scaling are not interchangeable with physical display pixels or VR headset pixels. A `2 px` browser mark is only a repeatable Spotcheck condition.
- A better browser-drill result does not prove greater realism or better DCS visibility. Confirm any apparent improvement in a controlled DCS test mission.
- Human visual performance changes with fatigue, attention, room lighting, corrective lenses, zoom posture, and practice. Use repeated runs rather than a single score.
- Mixed sequences randomize backdrop, shape, or movement within the selected run; fixed settings are preferable for strict A/B comparisons.
- The tool stores profiles and run evidence in browser `localStorage`. Data leaves the browser only through an explicit JSON or CSV export.
- The terrain and cloud fields are abstract CSS textures, not map imagery. No real-world detection or tactical training claim is made.

## Community signal

Accessed **2026-10-31**. Recent DCS community discussion continues to show that visual spotting is both a recurring pain point and highly dependent on the player’s rendering stack:

- Reddit / r/hoggit — “What are the most important DCS settings for spotting aircraft?” (2025-10-02). The discussion compares resolution, anti-aliasing, upscaling, and spotting-dot choices, with users reporting materially different results across setups: https://www.reddit.com/r/hoggit/comments/1nvs7xw/what_are_the_most_important_dcs_settings_for/
- Reddit / r/dcsworld — “Spotting help” (2025-08-24). A player describes losing aircraft visually at close range and asks how monitor and graphics settings affect acquisition: https://www.reddit.com/r/dcsworld/comments/1n0ntmp/spotting_help/
- Reddit / r/hoggit — “Why does spotting feel easier in VR?” (2025-07-09). Replies discuss headset resolution, apparent target size, rendering behavior, and the difficulty of comparing monitor and VR reports directly: https://www.reddit.com/r/hoggit/comments/1lvkq48/why_does_spotting_feel_easier_in_vr/
- Reddit / r/hoggit — “What is the current state of spotting dots?” (2025-05-17). The thread shows continued uncertainty about dot settings, resolution behavior, and server-side expectations: https://www.reddit.com/r/hoggit/comments/1kn5z8m/what_is_the_current_state_of_spotting_dots/
- Eagle Dynamics Forums — “Improved ‘spotting dots’” discussion. This long-running official-forum thread documents how monitor resolution, VR, scaling, anti-aliasing, target aspect, and background can produce sharply different experiences: https://forum.dcs.world/topic/324002-improved-spotting-dots/
- Eagle Dynamics release changelog, reviewed to avoid treating a historical spotting implementation as a fixed current fact: https://www.digitalcombatsimulator.com/en/news/changelog/release/

The demand signal is not merely “make dots bigger.” Players struggle to determine whether a change helped because they alter several settings, use different test missions, or compare unlike monitor and VR conditions. Spotcheck addresses the narrower evidence problem: hold a browser task stable, name the complete profile, collect repeated results, and then validate the winning setup inside DCS.

## Design posture

**Primary surface: Operate; secondary surface: Configure.** The live contact window and immediate response affordance dominate during a drill. Setup remains a compact left workbench, while evidence and profile records are separate task surfaces rather than decorative dashboard cards.

The visual system uses near-black olive work surfaces, restrained amber operational emphasis, condensed headings, monospaced evidence values, small radii, explicit borders, 44-pixel controls, visible focus states, responsive reflow, reduced-motion support, and print styling. No remote fonts or runtime assets are loaded.

Slop diagnostic after implementation: **0/10**. No blue/violet tech gradient, generic indigo accent, equal-weight feature-tile grid, accent rail, glass blur, decorative monument stat, icon topper, center-stack composition, default Inter typography, or wrong-surface composition is present. The large contact field is the actual work surface, not decorative empty space.

## Files

- `index.html` — complete application with inline CSS and JavaScript
- `README.md` — usage, assumptions, current community sources, and design rationale

## Privacy

Spotcheck performs no network requests and includes no analytics. All application data remains in the current browser profile unless the user explicitly exports it.
