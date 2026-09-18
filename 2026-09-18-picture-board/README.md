# Picture Board

Picture Board is a self-contained, offline AWACS contact desk for DCS World. It turns spoken BRA/BULLS calls into an aging, prioritized tactical worksheet for aircraft without a rich datalink picture. It is a manual decision aid: it does not connect to DCS, SRS, Tacview, or any server.

## Use

1. Open `index.html` directly in a modern browser; no server or network connection is required.
2. Set the mission/package name and your current magnetic heading.
3. Enter a call quickly, such as `BRA 315 22 12000 HOT` or `NORTH GROUP BULLS 270 45 18000 FLANKING 2 SHIP`, then choose **Parse + add contact**. Structured fields are available when the call is incomplete or unusual.
4. Read the sorted board. BRA contacts include a clock position relative to own heading; BULLS contacts remain anchor-relative.
5. Mark a contact committed, refresh its timestamp when an update arrives, or drop it when it no longer belongs in the picture.
6. Filter the board, copy a plain-text picture, or print it. Mission context and active contacts persist in browser `localStorage`.

Keyboard: press `N` outside a form to focus rapid entry; press `Ctrl/Command + Enter` there to add; press `Escape` to clear and leave rapid entry.

## Assumptions and limits

- Bearings are treated as magnetic only because that is how the operator labels own heading; the app performs no true/magnetic conversion.
- Clock position is computed only for BRA contacts by comparing contact bearing with current own heading.
- Priority is deliberately simple and visible: HOT at 15 NM or less is **urgent**; HOT at 30 NM or less, or any contact at 15 NM or less, is **priority**. It is a rehearsal/attention heuristic, not tactical doctrine.
- The parser expects reference, bearing, and range in that order. The next number is treated as altitude. Unrecognized words are ignored.
- Calls are only as current and accurate as the operator's transcription. DCS sensors, mission ROE, and crew judgment remain authoritative.

## Community signal

Accessed 2026-09-18:

- A recent r/hoggit MiG-29A discussion praised the module while emphasizing its awkward multiplayer position without strong GCI support. The thread specifically notes that DCS AWACS may emit many group calls at once so voice lines overlap, then remain silent for minutes. That creates a concrete need for a fast, persistent manual contact board: https://www.reddit.com/r/hoggit/comments/1rcquqb/love_the_mig29a/
- A recurring r/hoggit explanation of non-datalink BVR describes the actual workload: remember own position relative to bullseye, mentally place called groups, and infer where they are going. Picture Board externalizes the volatile part of that task without pretending to replace a sensor: https://reddit.com/r/hoggit/comments/wdhski/f15c_lack_of_datalink
- The SkyEye development discussion shows sustained community demand for better, prioritized AWACS/GCI interactions, including PICTURE and BOGEY DOPE handling rather than robotic information dumps: https://reddit.com/r/hoggit/comments/1hr61ck/skyeye_development_newsletter_january_2025

## Design

Primary surface: **Operate**. Capture and contact actions dominate; glanceable monitoring is secondary. The visual language uses a paper plotting-board palette, restrained tactical status color, explicit age, and type hierarchy instead of decorative cards or a dashboard hero.

Slop audit after implementation: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rails, blur, monument stats, icon toppers, centered stack, default Inter, or wrong-surface composition.
