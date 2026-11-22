# Order Stack

Order Stack is a self-contained, offline DCS World Mission Editor companion for diagnosing why an AI group attacks the wrong target, ignores a narrow search zone, abandons a task, or enters recovery early. It turns the group's role task, enroute filters, main tasks, triggered actions, ROE, reaction-to-threat setting, and final waypoint into a visible precedence model and a short repair card.

## Use

1. Open `index.html` directly in a browser. No server, account, package, or network connection is required.
2. Pick the closest preset or model the AI group's current Mission Editor setup.
3. Select **Run audit** and repair blockers from top to bottom.
4. Use the target eligibility test to check whether one intended or excluded contact is admitted by the modeled task stack.
5. Copy or print the generated repair card, then prove the change in a minimal DCS mission before restoring complexity.

The app saves the current worksheet in browser `localStorage`. **Reset** returns to the baseline CAS-conflict example.

## Important assumptions

- Order Stack is a planning and diagnostic aid; it does not parse `.miz` files or observe DCS at runtime.
- Background/enroute attack tasks are modeled as target-permission filters that can broaden eligibility when several remain active.
- A default role task can overlap a narrower added search task. The app therefore flags the combination for isolation testing rather than claiming every overlap must fail.
- Detection, line of sight, weapon suitability, range, threat reaction, route geometry, and current DCS AI behavior still determine whether an eligible target is actually attacked.
- DCS behavior can change by build. The repair card deliberately recommends a one-group/one-target proof mission.

## Community signal and sources

Accessed **2026-11-22**:

- A same-day r/dcsworld question described a CAS group attacking SAMs and unarmed support vehicles despite an intended zone filter and “assigned only” ROE. The accepted guidance identified the retained default CAS task and a non-landing final waypoint as the key setup problems: https://www.reddit.com/r/dcsworld/comments/1y2gjet/ai_planes_disobeying_my_direct_orders/
- Eagle Dynamics' Mission Editor FAQ explains that Start Enroute Task items act as background target filters, multiple background filters are additive (OR), broad CAP can overlap Search Then Engage In Zone, and a non-landing last waypoint can move AI into arrival/landing behavior: https://forum.dcs.world/topic/391170-mission-design-tips-notes-faq/
- A recurring r/hoggit discussion illustrates the same underlying confusion: mission role, ROE, task type, target detection, and weapon behavior interact, and narrowly assigned tasks are often more predictable than broad autonomous searches: https://www.reddit.com/r/hoggit/comments/1haqx5q/
- Another r/hoggit mission-building thread recommends placing the search instruction before the target area, reducing AI choice during diagnosis, and controlling ROE/reaction-to-threat while proving the task: https://www.reddit.com/r/hoggit/comments/1c0akh8/

## Design

Primary surface: **Command / Inspect**. The composition prioritizes a left-side configuration bench, a visible five-stage order stack, findings, a single-target test, and an operational repair card. It intentionally avoids dashboard metrics, feature tiles, decorative icons, and generic tech gradients.

## Slop diagnostic

- Initial score: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rail, blur surface, monument stat, icon topper, center stack, default Inter typography, or wrong-surface composition.
- Final score: **0/10** after implementation review; no compositional repair was required.
