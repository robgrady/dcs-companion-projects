# Taskwire

Taskwire is a self-contained, offline workbench for planning and rehearsing DCS World AI task sequences before implementing them in the Mission Editor. It turns an intended behavior into an ordered route/task wire, an explicit exit-condition contract, a preflight diagnosis, and a printable implementation card.

## Use

1. Open `index.html` directly in a modern browser; no server or network connection is required.
2. In **Build**, name the AI group, select its main task and start mode, define the exit condition, and edit the sequence stages.
3. In **Rehearse**, advance through the states and fire the exit condition. The simulator jumps to a stage whose name/type contains “break,” “switch,” or “exit,” making a missing transition obvious.
4. Review **Preflight diagnosis**, then use **Recipe** as the ordered build-and-test card while working in the DCS Mission Editor.
5. **Save plan** stores the current plan in browser localStorage. Export/import JSON moves a plan between browsers. Printing produces the build card.

## Important assumptions and limits

- Taskwire plans behavior; it does **not** read or modify `.miz` files and it does not inject Lua.
- DCS menu labels, permitted advanced waypoint actions, and AI behavior depend on the aircraft/group main task and may change by simulator version. The generated recipe therefore requires an in-sim validation pass.
- The exit-condition options are contracts, not automatic DCS trigger code. The mission author owns the named flag, zone, or threshold and implements it as a Mission Editor trigger.
- The default E-2D breakaway plan is an editable worked example, not a claim that one setup is universal.
- User-authored text is escaped before being rendered. Plans remain local unless explicitly exported.

## Community signal

Accessed 2026-09-05:

- [DCS 2026 Core feature Wishlist — Eagle Dynamics Forums](https://forum.dcs.world/topic/384194-dcs-2026-core-feature-wishlist/) — mission builders ask for simplification, automation, easier linking of groups, and faster creation of complex behaviors; the thread also highlights undo and usability gaps.
- [DCS-SMS: Mission Editor Tools and AI agentic workflows — Eagle Dynamics Forums](https://forum.dcs.world/topic/387809-dcs-sms-mission-editor-tools-and-ai-agentic-workflows/) — active 2026 development and positive community response around reusable prefabs, trigger finding, mass edit, and waypoint task-list tooling show demand for reducing Mission Editor repetition.
- [RED AI Aircraft Ground Attack Help — Eagle Dynamics Forums](https://forum.dcs.world/topic/384335-red-ai-aircraft-ground-attack-help/) — a current troubleshooting thread recommends a waypoint loop so AI repeatedly reevaluates a search-and-engage task, illustrating how task order and loop structure remain non-obvious.
- [Showcasing DCS Organic Panic — r/hoggit](https://www.reddit.com/r/hoggit/comments/1d9w1b3/showcasing_dcs_organic_panic_my_new_script_for/) — mission makers describe repeated-task failures and difficulty making an E-2 leave orbit for recovery when a threat approaches. That concrete “orbit until condition, then break away” problem became Taskwire’s default worked example.

These signals support a narrow companion rather than another full mission planner: Taskwire focuses on making AI state transitions explicit and testable before the author spends time iterating inside DCS.
