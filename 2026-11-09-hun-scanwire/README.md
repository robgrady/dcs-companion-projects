# Hun Scanwire

Hun Scanwire is a self-contained, offline F-100D custom-dashboard scan trainer for DCS World. It turns the module's nine-digit Custom Dash ID into an interactive instrument layout, lets the pilot define phase-specific scan sequences, and records timed twelve-call location drills against the exact saved layout.

## Use

1. Open `index.html` directly in a modern browser. No server, account, installation, or network connection is required.
2. Paste the Custom Dash ID from Grinnelli Designs' official Dash Creator, or choose one of the published developer presets.
3. Select a phase and click gauges to build its scan sequence. Click one gauge and then another compatible gauge to swap their positions.
4. Use **Rehearse sequence** to walk the active scan in order. Use **Start drill** for a randomized twelve-call instrument-location test.
5. Training history, best time, layout, and scan sequences persist in browser `localStorage`. **Export data** downloads a JSON backup; **Print card** produces a paper/PDF layout-and-scan reference.

## Important assumptions

- This is an independent training aid, not an official Eagle Dynamics or Grinnelli Designs product.
- Gauge identities, slot groups, Custom Dash ID structure, and developer preset IDs were transcribed from the official Grinnelli Designs Dash Creator on 2026-11-09.
- The ID validator follows the official creator's current constraint: gauges 1–7 swap only among the seven main positions; gauges 8–9 swap only between the two auxiliary positions.
- The cockpit graphic is an original schematic training representation. It deliberately does not reproduce proprietary cockpit art or gauge faces.
- Default scan sequences are editable practice prompts, not authoritative procedures. The app makes no claims about aircraft limits, emergency procedures, or weapons employment.
- Browser data is local to the browser/profile and file origin. Export before clearing site data or moving to another machine.

## Community signal

The idea combines two visible 2026 community signals: unusually strong interest in the F-100D's movable instrument panel, and continued demand for compact references that help pilots learn newly released modules.

Sources reviewed on 2026-11-09:

- Grinnelli Designs, **F-100D Customization Options** discussion in r/hoggit — community response highlighted the custom instrument panel layout as a standout module feature and asked for similar quality-of-life features elsewhere: https://www.reddit.com/r/hoggit/comments/1tf0cca/dcs_f100d_customization_options/
- Grinnelli Designs, **F-100D Customization Options** discussion in r/dcsworld — pilots specifically reported already making preferred dash layouts: https://www.reddit.com/r/dcsworld/comments/1tf0du1/dcs_f100d_customization_options/
- Goldwolf, **Quick Reference Guide — Next update** in r/hoggit — the September 2026 update added the F-100D and drew strong engagement plus comments about using compact references in the kneeboard: https://www.reddit.com/r/hoggit/comments/1wshufs/quick_reference_guide_next_update/
- Goldwolf, the matching r/dcsworld Quick Reference Guide update, confirming the same F-100D learning demand across a second DCS community: https://www.reddit.com/r/dcsworld/comments/1wshvd5/quick_reference_guide_next_update/
- Goldwolf, **Beginner's Guide — Next release** in r/hoggit — the August 2026 guide added the F-100D and described its purpose as answering common DCS learning questions: https://www.reddit.com/r/hoggit/comments/1vfcmqc/beginners_guide_next_release/
- Eagle Dynamics community changelog discussion for DCS 2.9.27.24969 — recorded the F-100D's June 12, 2026 introduction and linked the official manual: https://www.reddit.com/r/dcsworld/comments/1u46unl/20260612_dcs_change_log_292724969/
- Grinnelli Designs official F-100D page — confirms the customizable core-gauge dash and randomized authentic layouts: https://grinnellidesigns.com/f-100d/
- Grinnelli Designs official Dash Creator — source of gauge names, group rules, IDs, and published presets: https://grinnellidesigns.com/dash-creator/
- Grinnelli Designs official online manual — reference entry point for the released DCS module: https://grinnellidesigns.github.io/f-100d-manual/

## Technical notes

- Single-file HTML/CSS/JavaScript application; no external runtime dependencies.
- Designed to work from `file://` and at desktop, tablet, and phone widths.
- Keyboard support: `Enter` applies an ID; `Space` or `Right Arrow` advances a sequence rehearsal; `Escape` stops an active drill/rehearsal.
- Accessibility includes semantic regions, explicit labels, live drill cues, 44px primary controls, visible focus treatment, and reduced-motion support.
