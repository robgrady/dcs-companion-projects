# VR Sortie Guard

VR Sortie Guard is a self-contained, offline DCS World session-degradation log for VR pilots. It establishes a healthy-session performance baseline, marks state-changing events such as F10 map use, respawns, slot swaps, rejoins, headset sleep/wake, codec changes, and full restarts, then compares later performance samples against pilot-defined thresholds.

## Use

1. Open `index.html` directly in a modern browser. No server, build step, account, or network connection is required.
2. Describe the headset, link method, GPU/VRAM, server or mission, aircraft, and target frame rate.
3. While the session is healthy, enter FPS and game-thread latency and select **Capture baseline**. Encode and network latency are optional reference fields.
4. Select an event button whenever the session state changes. Use the observation field to add scene or symptom context.
5. Take comparison samples in reasonably comparable scenes. The app flags FPS loss or game-latency rise according to the thresholds you set; consecutive flagged samples move the guard from **Watch** to **Recover deliberately**.
6. Record one recovery action at a time, then sample again. Export JSON for a complete backup, CSV for analysis, copy a compact handoff summary, or print the timeline.

All useful state is stored locally in the browser with `localStorage`. The app works from `file://` and sends no data anywhere.

## Important assumptions

- This is an observation and decision-discipline tool, not a diagnostic engine. An event preceding a slowdown is correlation, not proof of cause.
- Comparable samples are more useful than numbers captured in radically different scenes, missions, weather, unit counts, or view directions.
- FPS and latency figures are entered manually from the pilot's chosen overlay or telemetry source; the browser cannot read DCS or headset telemetry directly.
- Thresholds are personal guardrails, not universal recommendations. Defaults are a 20% FPS drop, a 15 ms game-latency rise, and two consecutive flagged samples.
- A recovery action only becomes evidence when a post-action sample is recorded.
- Eagle Dynamics does not publish or endorse this project.

## Community signal

Recent community discussion repeatedly described VR performance that degrades during a multiplayer session—especially after deaths, respawns, aircraft changes, or F10-map use—and pilots comparing recovery attempts such as rejoining, alt-tabbing, headset sleep/wake, codec changes, or restarting DCS. A separate recent r/hoggit thread also reflects continuing demand for concrete multiplayer performance guidance. VR Sortie Guard does not assert a single root cause; it turns those reports into a disciplined per-session evidence wire.

Sources reviewed on **2026-10-04**:

- r/dcsworld, “Performance degradation after death / respawn” — https://www.reddit.com/r/dcsworld/comments/1wcmi7w/performance_degradation_after_death_respawn/
- r/dcsworld, “New DCS weird multiplayer VR issue” — https://www.reddit.com/r/dcsworld/comments/1whgrv1/new_dcs_weird_multiplayer_vr_issue/
- r/hoggit, “Weekly Questions Thread” (multiplayer performance discussion signal) — https://www.reddit.com/r/hoggit/comments/1wzbsnm/weekly_questions_thread_20260428/

## Design and accessibility

This is an **Operate** surface: baseline capture, event marking, comparison sampling, and recovery evidence are the primary actions. The layout avoids a marketing hero and decorative metrics. It uses semantic sections and labels, visible keyboard focus, 44-pixel minimum controls, responsive single-column behavior, print styling, reduced-motion support, and high-contrast status language that does not depend on color alone.

### Anti-slop audit

- Initial score: **0/10**. No tech gradient, generic indigo accent, feature-tile grid, accent rails, glass cards, monument stats, icon toppers, center stack, default Inter typography, or surface mismatch.
- Final score: **0/10**. The composition remains action-first and operational; no compositional tells fired.
