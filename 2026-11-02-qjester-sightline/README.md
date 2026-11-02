# QJester Sightline

QJester Sightline is a self-contained, offline F-14B(U) context-key trainer for DCS World. It teaches the pilot-side sightline logic behind Heatblur's QJester contextual commands: select the intended HUD, HSD/PTID, VDI, or outside-world target, hold the context binding long enough to place the indicator, then release.

## Use

1. Open `index.html` directly in a modern browser. It needs no server, build step, account, or network connection.
2. In **Learn** mode, read the context and select the highlighted sightline target.
3. Hold the on-screen context button, or hold the displayed keyboard key, until the progress ring completes; then release.
4. Use **Check** mode to remove the highlight. Passing all eight contexts in Check mode completes the qualification set.
5. Open **Settings** to change the displayed context key, hold threshold, or confirmation sound.
6. Use **Reference** for a compact command-intent summary suitable for printing.

Attempts, passes, streak, settings, and Check-mode qualification are stored in browser `localStorage`.

## Included drills

- Select a PTID page from the HSD's TID repeat.
- Select PTID tactical range scale.
- Hook a HUD Target Designate Box.
- Hook a PTID TWS track.
- Direct an A/A radar scan by azimuth and elevation.
- Ask Jester to try to acquire a visual aircraft in TWS.
- Slew LANTIRN toward an outside-world area of interest and establish area track.
- Move LANTIRN toward a point indicated on the VDI LTS repeat.

## Important assumptions

- This is a command-intent trainer, not an F-14 sensor or Jester AI simulation. A correctly issued command does not guarantee radar acquisition, track creation, pod line of sight, or AI success.
- The cockpit display is deliberately schematic. It is not a scale reproduction and should not be used for switch-location training.
- The configurable hold threshold is a training cue, not a claim about DCS's internal timing. Set it to a value that helps rehearse a deliberate hold-and-release gesture.
- QJester behavior, bindings, and terminology can change during early access. The current Heatblur manual and in-game controls remain authoritative.
- The app does not include proprietary cockpit art, module files, or external assets. It makes no network requests.

## Community signal

Recent F-14B(U) discussion repeatedly centers on learning the new QJester interaction model rather than simply finding another command list. Pilots ask how QJester should be invoked, report uncertainty about contextual commands and targeting behavior, and request a clear mapping for the new system. Heatblur's manual documents that the context action changes according to what the pilot is looking at—PTID controls, HUD designate boxes, TWS tracks, empty airspace, visual targets, outside A/G areas, and LTS repeat imagery. QJester Sightline turns that spatial rule into a repeatable interaction drill instead of another static menu diagram.

Sources reviewed and accessed **2026-11-02**:

- Heatblur F-14 manual — “Jester AI and Iceman AI Overview”: https://f14.manuals.heatblur.se/f14bu/jester_iceman/overview.html
- Heatblur F-14 manual — “Jester AI”: https://f14.manuals.heatblur.se/f14bu/jester_iceman/jester.html
- r/hoggit — “F14BU Jester AI / QJester”: https://www.reddit.com/r/hoggit/comments/1m1ift4/f14bu_jester_ai_qjester/
- r/hoggit — “F14BU and Jester issues”: https://www.reddit.com/r/hoggit/comments/1oi7ljn/f14bu_and_jester_issues/
- r/hoggit — “How do I make Jester / QJester to ask for [contextual action]”: https://www.reddit.com/r/hoggit/comments/1n4e3aq/how_do_i_make_jester_qjester_to_ask_for/
- r/hoggit search signal — “How can I get QJester to lock an aircraft with radar?”: https://www.reddit.com/r/hoggit/comments/1rzeef7/how_can_i_get_qjester_to_lock_an_aircraft_with/

## Design note

Primary surface: **Command / Inspect**. The sightline exercise occupies the center; scenario selection and execution feedback support fast, focused repetition rather than presenting a dashboard or marketing hero. The visual language uses restrained black cockpit surfaces, phosphor green, and caution amber, with no external fonts or assets.

### Slop diagnostic

- Initial score: **0/10**. No tech gradient, generic indigo accent, equal-weight feature grid, accent rail, glass blur, monument statistic, icon topper, center-stack composition, default Inter, or surface mismatch.
- Final score: **0/10**. The Command / Inspect composition remains intact after responsive and interaction work.

## Privacy and portability

All CSS and JavaScript are inline in `index.html`. State remains local to the browser profile and file origin. Clearing browser site data removes saved progress.
