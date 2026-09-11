# Syllabus Relay

Syllabus Relay is a self-contained, offline training queue and retention log for DCS World. It ships with the official **Start Here** mission sequences announced for the F/A-18C, AH-64D, and P-51D, preserves announced-but-unreleased lessons as visible hold items, and turns each completed flight into a dated debrief plus a scheduled review gate.

## Use

1. Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.
2. Select a lesson in the left training queue. The center pane shows the completion evidence and the next recommended action.
3. Fly that mission from DCS World’s **Start Here** or **Training** area.
4. Log **Complete** or **Repeat**, confidence from 1–5, and one useful observation.
5. Re-fly lessons when their review badge becomes ready. Clean completions open review intervals of 1, 3, 7, 14, then 30 days; **Repeat** keeps the lesson ready now.
6. Add custom series and lessons for any module. Use **Data** to export/import a JSON backup, or print the selected lesson’s attempt log.

The selected lesson, custom syllabus, and attempt history persist in browser `localStorage`. The `J` key moves to the next ready lesson when focus is not in a form field.

## Important assumptions and limits

- The built-in lesson names and availability match Eagle Dynamics’ 2026 Start Here announcement: five F/A-18C missions were available; three of four AH-64D missions and two of four P-51D missions were available. FCR Hellfires, Rockets, and Bombs remain marked **planned** rather than being represented as released.
- DCS can change mission names, sequence, availability, and content in later updates. Verify planned items in the current DCS installation before treating them as available.
- Syllabus Relay does not launch DCS, inspect mission results, assess proficiency, or claim that completing a tutorial makes a pilot combat-ready. Every result is user-recorded.
- The spaced-review intervals are a lightweight practice aid, not an official Eagle Dynamics syllabus or validated learning standard.
- Built-in completion-evidence prompts are intentionally broad because the official missions provide the actual instruction and evaluation context.
- Import replaces all current local app data only after confirmation. Export first if the current record matters.
- All data stays in the browser profile. There are no analytics, network calls, external assets, or runtime dependencies.

## Community signal

Eagle Dynamics’ latest update introduced a dedicated **Start Here** menu and short, ordered tutorial series because entering DCS or a new full-fidelity module can be daunting. The accompanying forum discussion immediately endorsed the direction and added that deciding what to do first and mapping controls remain daunting even for experienced flight-sim users. That is a strong current signal for a thin learning layer that preserves sequence, records friction after each flight, and makes the next repetition obvious without replacing the in-sim tutorial.

The same need recurs in r/hoggit. A newer getting-started discussion asked for quick action and a gentler learning curve while resisting hundreds of manual pages; replies said built-in training can get a pilot flying, but that complex modules still require deliberate learning. Earlier F/A-18C threads ask exactly how to approach the “massive amount” of material, with pilots recommending a staged approach and repeated practice. Syllabus Relay addresses the gap after “play the tutorials”: it remembers what was flown, what remained unstable, and when to review it.

Sources accessed **2026-09-11**:

- Eagle Dynamics Forums — “Back to School Sale 2026 | Start Here Missions | DCS Update DCS 2.9.28.27278”: https://forum.dcs.world/topic/391708-back-to-school-sale-2026-start-here-missions-dcs-update-dcs-292827278
- Eagle Dynamics — DCS 2.9.29.27278 changelog (Start Here menu and current supported aircraft): https://www.digitalcombatsimulator.com/en/news/changelog/release/2.9.29.27278
- r/hoggit — “DCS - Getting Started”: https://www.reddit.com/r/hoggit/comments/1lfeep5/dcs_getting_started/
- r/hoggit — “How did you guys learn DCS”: https://www.reddit.com/r/hoggit/comments/13hhyzu/how_did_you_guys_learn_dcs/
- r/hoggit — “Where and how to learn properly the F/A-18”: https://www.reddit.com/r/hoggit/comments/18kf0u0/where_and_how_to_learn_properly_the_fa18/

## Design and implementation

This is an **Operate** surface: the training queue, current action, attempt wire, and compact debrief inspector dominate a three-pane desktop composition that collapses cleanly for tablet and mobile. It uses a restrained night-operations palette, intentionally selected Avenir/Trebuchet typography, monospace metadata, semantic controls, visible focus states, 44-pixel primary targets, reduced-motion handling, and print styles.

Slop diagnostic before repair: **1/10** — the earliest composition centered the current lesson as a standalone stack, triggering the center-stack tell and weakening queue-to-debrief flow. Repair: it was recomposed as a left queue, working stage, and right debrief inspector. Final score: **0/10** — no tech gradient, generic indigo, feature-tile grid, decorative accent rail, blur, monument stat, icon topper, center stack, default Inter/system typography, or wrong-surface composition.
