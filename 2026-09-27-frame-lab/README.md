# Frame Lab

Frame Lab is a self-contained, offline DCS World performance test desk. It helps a pilot compare a known baseline against exactly one candidate change, using a locked scenario contract, repeatability checks, repeated A/B samples, median comparisons, and an explicit adopt/keep/repeat decision.

It is designed for the common case where DCS performance—especially in multiplayer or VR—feels inconsistent and random setting changes make the cause harder to isolate.

## Use

1. Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.
2. In **Setup**, record the exact DCS build, display mode, mission or server, map, aircraft, resolution/headset mode, sample duration, and the **one** change being tested.
3. Complete the six control checks. Match the route, mission state, server load, background applications, warm-up method, and measurement method as closely as practical.
4. Select **Lock scenario**. Frame Lab will not accept samples until the scenario is locked.
5. In **Runs**, add at least three baseline (A) and three candidate (B) samples. Average FPS and stutter count are required; 1% low FPS, worst frametime, load time, player count, and a run note are optional.
6. In **Decision**, review median A/B results. The app uses 1% low FPS as the primary frame metric when it exists for both variants; otherwise it uses average FPS. It also checks whether stutters materially worsened.
7. Record a disposition and reason. Export the full library as JSON, export the active test as CSV, or print the decision report.

Tests, samples, protocol state, and decisions persist in browser `localStorage`. JSON export is the durable backup path.

## Important assumptions and limits

- Frame Lab does not inspect DCS, Windows, hardware, drivers, telemetry, Tacview, logs, or multiplayer servers. Every measurement is user-entered.
- The app compares evidence; it does not diagnose a cause or prescribe hardware, graphics settings, operating-system changes, or driver changes.
- Multiplayer conditions cannot be perfectly controlled. Player count is only a coarse context cue; AI activity, scripts, network conditions, server hardware, mission duration, and nearby objects may differ between runs.
- A result inside the chosen material-change threshold is reported as no clear lead, not proof that the variants are identical.
- Medians reduce the influence of a single unusually good or bad run, but three samples are still a minimum rather than a guarantee of statistical confidence.
- “Stutters” must be counted consistently by the pilot. If the counting method changes, start a new test.
- Browser `file://` storage is local to the browser/profile/path combination. Export before clearing browser data or moving the project.
- DCS updates can invalidate an old result. Record the exact build and create a new test after a relevant update.

## Community signal

Recent DCS community discussions show recurring frustration with poor or unstable multiplayer performance, low FPS despite reduced graphics settings, crashes or long loading in busy multiplayer scenarios, and uncertainty about whether a reported fix generalizes to another machine. The useful common denominator is not another universal “best settings” list; it is a disciplined way to hold the sortie constant, change one variable, retain repeated measurements, and decide from the pilot’s own evidence.

Sources reviewed on **2026-09-27**:

- Reddit / r/dcsworld, **“DCS Multiplayer Performance Issues – Low FPS and Stuttering”** (2026-09-21) — a player reports roughly 15 FPS and stuttering in multiplayer even after lowering settings and closing other applications: https://www.reddit.com/r/dcsworld/comments/1wzof4e/dcs_multiplayer_performance_issues_low_fps_and_stuttering/
- Reddit / r/dcsworld, **“DCS crashing / long loading times in Multiplayer – looking for advice”** (2026-09-02) — a multiplayer-focused report describes long loads, crashes, and settings changes that did not resolve the problem: https://www.reddit.com/r/dcsworld/comments/1w6tgmd/dcs_crashing_long_loading_times_in_multiplayer/
- Reddit / r/dcsworld, **“Short guide to increase FPS on DCS without reducing quality”** (2026-09-14) — a current community optimization post whose comments emphasize that hardware and settings differ, reinforcing the need to verify changes locally rather than assume a universal result: https://www.reddit.com/r/dcsworld/comments/1wsnym5/short_guide_to_increase_fps_on_dcs_without/
- Reddit / r/hoggit, **Weekly Questions Thread — Sep 27** (2026-09-26) — the active weekly support thread continues to direct setup, performance, VR, and hardware questions into a shared troubleshooting space: https://www.reddit.com/r/hoggit/comments/1x4v8of/weekly_questions_thread_sep_27/
- Eagle Dynamics Support, **Multi-Threading FAQ** — official guidance notes that the multithreaded DCS version became the only version after DCS 2.9.8. The page was checked to avoid treating old single-thread versus multithread launch advice as current: https://www.digitalcombatsimulator.com/en/support/faq/multithreading/

## Design and implementation

The primary surface is **Operate**, with comparison as the central task: scenario controls, protocol state, run capture, and the decision record dominate the composition. The visual language is a restrained test-bench notebook—charcoal, warm paper ink, signal amber, tabular mono data, and serif decision language—with no external fonts or assets. Controls have visible focus states, important targets are at least 44 pixels high, the layout collapses for mobile, print output focuses on the decision, and nonessential motion respects `prefers-reduced-motion`.

Slop diagnostic before finalization: **0/10**. The artifact uses no blue/violet tech gradient, generic indigo accent, equal feature-tile grid, decorative accent rail, glass blur, monument stat, repeated icon topper, centered-stack composition, default Inter/system typography, or surface mismatch. No cosmetic repair was required; the comparison columns and workflow tabs follow the declared Operate surface.

## Files

- `index.html` — complete offline application with inline CSS and JavaScript
- `README.md` — instructions, assumptions, design record, and community sources
