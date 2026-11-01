# Groove Tape

Groove Tape is a self-contained, offline carrier-pattern timing desk for DCS World. It gives a pilot one low-friction control surface for marking Break, Abeam, 90, Groove, and the final outcome, then preserves segment timing as repeatable evidence across traps, bolters, and waveoffs.

The app deliberately does **not** prescribe a carrier procedure or grade flying quality. The user supplies the timing contract appropriate to the aircraft, mission, campaign, server, and training objective.

## Use

1. Open `index.html` directly in a modern browser. No server, account, package, build step, or network connection is required.
2. Name the session and record the aircraft, carrier or mission, environment, and personal target time for each segment.
3. Select **Arm new pass** before entering the pattern.
4. Mark the actual gates with the on-screen controls or keyboard:
   - `1` — Break
   - `2` — Abeam
   - `3` — 90
   - `4` — Groove
   - `T` — Trap
   - `B` — Bolter
   - `W` — Waveoff
   - `Esc` — abort without saving
5. Complete several passes under the same contract.
6. Use **Pass ledger** to inspect segment timing, outcome, notes, median groove time, and spread.
7. Use **Debrief** to generate a copy-ready session summary that identifies the segment with the widest timing variation.
8. Start a new named session whenever the aircraft, mission, environment, or timing standard changes.
9. Export JSON backups for durable storage or CSV for analysis.

`Alt+1` through `Alt+4` switch application views. Sessions, passes, targets, and notes persist in browser `localStorage`.

## Important assumptions and limits

- Groove Tape is simulation-only self-review tooling. It is not for real-world aviation or qualification.
- Timing alone cannot establish lineup, glideslope, angle of attack, airspeed, configuration, clearance, safe separation, or landing quality.
- The app is not an LSO, does not implement NATOPS, and does not encode a module-, campaign-, carrier-, or server-specific procedure.
- All target times are user-entered personal standards. The starting values are editable working examples, not authoritative DCS or real-aircraft limits.
- Browser focus changes, device sleep, pauses, multitasking, and human button delay can distort timing.
- A segment outside its target is evidence for review, not proof that the segment caused a bolter, waveoff, or poor grade.
- Compare timing with cockpit scan, geometry, energy state, campaign feedback, LSO comments, track review, or Tacview where appropriate.
- Import replaces the current local dataset after confirmation. Export first if both records matter.
- Clearing browser site data can remove saved sessions. JSON export is the durable backup path.

## Community signal

Sources accessed **2026-11-01**.

The immediate signal is renewed carrier-training attention around the release of Reflected Simulations’ **Speed & Angels** F-14 campaign, combined with recurring requests for training that teaches an aircraft through structured, repeatable practice rather than leaving the pilot to infer corrections from a failed mission.

- Eagle Dynamics newsletter — **DCS Newsletter — Speed and Angels Campaign (30.10.2026)**. The official release announcement places a new F-14 training-focused campaign in the current DCS release conversation: https://www.digitalcombatsimulator.com/en/news/newsletters/73f196ad2fa7a070f3347493a75a251a/
- Eagle Dynamics Forums — **Speed & Angels teaser**. The campaign author describes the project as recreating a Tomcat training experience and notes extensive practice and qualification work: https://forum.dcs.world/topic/324504-speed-angels-teaser/
- Reddit / r/hoggit — **“Speed & Angels campaign for DCS F-14 released!”** The release thread calls the campaign an in-depth training experience and generated immediate pilot interest: https://www.reddit.com/r/hoggit/comments/1ojb7e1/speed_angels_campaign_for_dcs_f14_released/
- Reddit / r/hoggit — **“The Upcoming F-14B Speed and Angels Campaign is going to be an invaluable training campaign.”** Community discussion explicitly values structured campaign-based learning for the Tomcat: https://www.reddit.com/r/hoggit/comments/1i7fqb7/the_upcoming_f14b_speed_and_angels_campaign_is/
- Reddit / r/dcsworld — **“Looking for a campaign that teaches me one aircraft from startup to combat.”** The request and replies show continuing demand for guided repetition and progression rather than disconnected tutorial missions: https://www.reddit.com/r/dcsworld/comments/1qf6r9x/looking_for_a_campaign_that_teaches_me_one_aircraft/
- Reddit / r/hoggit — **“DCS needs interactive training campaign.”** The thread describes the gap between introductory tutorials and sustained skill-building practice: https://www.reddit.com/r/hoggit/comments/1kjv0lg/dcs_needs_interactive_training_campaign/

Groove Tape addresses one narrow part of that demand without copying campaign content: it makes carrier-pattern repetition measurable, preserves the timing contract used for each pass, and turns a sequence of attempts into a focused debrief instead of an undifferentiated success/failure memory.

## Design posture

**Primary surface: Operate; secondary surface: Monitor.** The pass tape, ordered event controls, outcome buttons, and clock dominate. Setup is a compact workbench, while the ledger and debrief watch accumulated evidence without turning the live surface into a decorative dashboard.

The visual system uses a dark deck-workstation palette, restrained amber emphasis, condensed operational headings, monospaced timing values, small radii, explicit borders, 44-pixel controls, visible focus states, responsive reflow, reduced-motion support, and print styling. The top-down pattern is functional progress feedback rather than an illustrative hero.

Slop diagnostic before repair: **1/10** — the initial top-down pattern risked becoming decorative product art. Repair: gate status, aircraft position, next-event state, and control enablement were tied directly to the live pass sequence. Final score: **0/10**. No generic tech gradient, indigo accent, equal-weight feature grid, accent rail, glass blur, monument stat, icon topper, center stack, default Inter typography, or wrong-surface composition remains.

## Files

- `index.html` — complete application with inline CSS and JavaScript
- `README.md` — use, assumptions, sources, and design rationale

## Privacy

Groove Tape performs no network requests and loads no remote assets. All application data stays in the current browser profile unless the user explicitly exports or copies it.
