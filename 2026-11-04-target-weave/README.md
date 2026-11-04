# Target Weave

Target Weave is a self-contained, offline DCS World Mission Editor companion for assigning AI strike flights to distinct targets. It makes ownership explicit, warns about duplicate primary tasking and overloaded flights, generates per-flight build cards, and provides a small execution board for recording failed targets and exposing reserve-shooter decisions.

Open `index.html` directly in a modern browser. It has no external runtime dependencies, requires no account or build step, and works through `file://`.

## How to use it

1. Add each AI flight or group, its role, and the maximum number of primary target tasks you intend to test.
2. Add targets using their exact Mission Editor names. Choose the DCS task family you intend to use and mark whether each target is required.
3. Click cells in the assignment weave to cycle between **Unassigned**, **Primary**, and **Reserve**.
4. Resolve inspector warnings for missing owners, accidental duplicate primaries, reserve-only targets, or flight overload.
5. Open **Build cards** for a per-flight Mission Editor handoff and print them if useful.
6. During a controlled test, use **Execute** to record target outcomes. Missed or unavailable targets expose the planned reserve action—or the lack of one.
7. Export the plan as JSON for backup or transfer. Useful state is also retained in localStorage.

The optional **Load demo** action creates a clearly labeled example with two flights and three targets. **New plan** clears all stored app state after confirmation.

## Design and implementation

This is an **Operate** surface: flights, targets, assignment state, conflicts, and the next corrective action dominate. It deliberately avoids a marketing hero, generic feature cards, invented telemetry, and decorative aviation imagery.

Everything is inline in `index.html`: semantic HTML, responsive CSS, and dependency-free JavaScript. Controls have visible focus states and mobile-sized targets. The layout collapses from a three-column planning desk to a single-column mobile workflow, and print mode produces clean build cards.

### Slop diagnostic

- Initial score: **0/10**. No tech gradient, generic indigo accent, equal feature-tile grid, accent rails, blur, monument stats, icon toppers, centered composition, default Inter typography, or wrong-surface composition.
- Final score: **0/10** after implementation review; no compositional tells fired.

## Important assumptions

- Target Weave is a planning and test-record aid. It does not edit `.miz` files, issue simulator commands, or guarantee that DCS AI will perform a selected task.
- The task-family labels are user-selected Mission Editor intentions, not automatic recommendations. Their availability and behavior depend on aircraft, role, weapon, target type, waypoint geometry, mission state, and the installed DCS version.
- A declared flight task capacity is a planning constraint set by the user, not a simulator limit.
- A reserve assignment has no effect in DCS by itself. The mission designer must still create and verify the relevant stop conditions, triggers, route changes, flags, or alternate tasks.
- The generated cards intentionally call for a short controlled proof run before more mission complexity is added.
- This is a simulation design aid, not real-world tactical guidance.

## Community signal and sources

Accessed **2026-11-04**:

- Eagle Dynamics forums, **AI pilots are useless** — a current Mission Editor thread describes AI flights repeatedly attacking the same target and asks how to make different aircraft attack separate targets. That is the direct demand signal for a visible target-to-flight assignment matrix and duplicate-owner warnings: https://forum.dcs.world/topic/390983-ai-pilots-are-useless/
- r/hoggit, **AI Following Attack Group Commands in Mission Editor** — a mission builder reports AI attacking unintended or previously assigned targets despite explicit waypoint tasking, reinforcing the need to record intent, isolate one task at a time, and retain test evidence: https://www.reddit.com/r/hoggit/comments/1l90zi4/ai_following_attack_group_commands_in_mission/
- Eagle Dynamics forums, **How can I get my wingman to attack the same ground target** — recurring confusion around Flight/Group/Wingman attack commands shows that target ownership and command scope remain difficult to reason about: https://forum.dcs.world/topic/351250-how-can-i-get-my-wingman-to-attack-the-same-ground-target/
- Eagle Dynamics forums, **AI Aircraft Tasking** — Mission Editor users continue to report aircraft ignoring, repeating, or mis-sequencing attack tasks; the thread supports an evidence-first build-and-proof workflow rather than a promise that a valid-looking task will execute reliably: https://forum.dcs.world/topic/277998-ai-aircraft-tasking/
- r/hoggit, **Long time BMS fan, tried DCS for the first time** — recent community comparison again highlights single-player AI behavior and mission outcomes as central pain points, supporting a tool focused on making AI intent inspectable and testable: https://www.reddit.com/r/falconbms/comments/1wvpp53/long_time_bms_fan_i_tried_out_dcs_for_the_first/

The project is intentionally distinct from a general trigger debugger or task-sequence editor: its narrow job is target ownership across multiple AI flights, pre-launch deconfliction, and reserve reflow after a failed result.
