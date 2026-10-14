# Campaign Rescue

Campaign Rescue is a self-contained, offline DCS World campaign mission recovery desk. It turns an expensive, vague failure—“the next thing never happened”—into a controlled triage branch, a safe recovery ladder, a one-variable attempt log, and a copy-ready incident brief for campaign authors or community support.

## Use

1. Open `index.html` directly in a modern browser. It needs no server, account, install, network connection, or build step.
2. Record the campaign, mission, aircraft, DCS build, repeat count, and whether the problem began after an update or differs for another pilot.
3. Mark the observed symptoms and relevant conditions. Describe the exact last valid cue and the expected next event.
4. Follow the generated recovery ladder from top to bottom. Preserve evidence first and change only one variable per retry.
5. Use **Attempt log** before each new run. Record whether the failure remained, changed, or cleared.
6. Use **Report brief** to copy a structured support packet. Export the complete local case as JSON or print the active view.

Keyboard shortcuts: `Alt+1`, `Alt+2`, and `Alt+3` switch between Triage, Attempt Log, and Report Brief. Case settings and attempts persist in browser `localStorage`.

## Assumptions and boundaries

- The app provides disciplined triage, not a definitive diagnosis. Its percentage is a transparent prioritization cue based on the recorded evidence, not a statistical probability.
- It does not modify campaign progress, mission archives, scripts, DCS files, or Saved Games content.
- Back up campaign progress and any modified files before repair, reset, skip, or manual-edit actions.
- Mission logic differs by campaign and can depend on trigger zones, unit state, timing, route, altitude, radio flow, target destruction, AI survival, or score. The app therefore asks for the first broken link rather than prescribing one universal fix.
- DCS and campaign versions change. Verify current support instructions from Eagle Dynamics and the campaign author before acting on a version-specific workaround.
- All entered data stays in the browser unless the user explicitly exports or copies it.

## Community signal

Accessed **2026-10-14**.

Recent discussions show the same costly pattern across different campaigns and modules: a player repeats a long mission because an AI dependency, trigger, radio cue, or campaign state appears stuck, but the initial report lacks the exact DCS build, last valid event, controlled comparison, and repeatable sequence needed to separate mission logic from local configuration.

- A current r/dcsworld changelog lists multiple AI fixes, including runway lineup, carrier landing, crosswind, takeoff-collision, and formation behavior—evidence that campaign dependencies can change with the installed DCS build: https://www.reddit.com/r/dcsworld/comments/1wu630n/20260930_293028536_change_log/
- A recent r/hoggit discussion argues that many single-player missions make failure and unclear dependencies part of the first-run experience, with unreliable wingmen among the cited problems: https://www.reddit.com/r/hoggit/comments/1r2tjag/dcs_has_a_problem_with_single_player_missions/
- A campaign support thread reports AI aircraft parked on a runway/taxiway and unable to take off, making the mission impossible to complete: https://forum.dcs.world/topic/387627-mission-5-unable-to-complete/
- Another campaign support thread documents a taxiing AI dependency, with the author identifying a specific player position needed to activate the next trigger: https://forum.dcs.world/topic/378591-mission-8-taxiing-ai-gets-stuck/
- A current dynamic-campaign discussion describes the continuing effort required to keep AI units on mission and prevent them from becoming stuck: https://www.reddit.com/r/dcsworld/comments/1wocu5o/dynamic_campaing_wip/

Campaign Rescue responds by preserving the first failed state, prioritizing one diagnostic branch, preventing uncontrolled multi-variable retries, and producing a compact report that states the expected event, observed event, environment, and attempt history.

## Design notes

This is primarily an **Operate** surface with a secondary **Inspect** view. Incident intake remains in a sticky workbench; the active recovery card, attempt queue, and report packet occupy the main work area. The visual language uses a dark operations desk and restrained paper case file, with typography and rules doing the hierarchy work instead of generic feature cards or decorative icons.

Slop diagnostic before repair: **1/10** — a large title risked reading as a center-stack marketing hero. Repair: the title was anchored to a compact operational masthead with actions and immediately followed by the two-column work surface. Final score: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rail, unearned blur, monument stat, icon topper, center stack, default Inter typography, or surface mismatch remains.
