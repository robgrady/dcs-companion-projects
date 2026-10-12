# Trigger Trace

**Trigger Trace** is a self-contained, offline preflight logic bench for DCS World mission builders. It lets you model a compact chain of Mission Editor-style conditions and actions, drive event signals and time, watch flags/groups/messages change, and inspect a chronological trace before rebuilding and testing the logic in DCS.

Open `index.html` directly from Dropbox in a modern browser. It requires no server, install, network connection, package, or build step.

## Why it exists

A current r/hoggit mission-building thread described the Mission Editor as a separate skill to learn, specifically recommending that builders inspect triggers “from left to right.” A current r/dcsworld beginner question likewise needed the three-part **ONCE → condition → message action** structure explained for a simple escort call. Other recent reports show how troubleshooting still tends to depend on adding temporary message actions and manually checking trigger-zone setup. Together, those discussions point to a recurring need: a readable, low-cost place to rehearse the state logic before loading a mission repeatedly.

This project is deliberately narrower than a mission generator. It is a scratch bench for understanding and communicating trigger intent.

## Use

1. Rename the mission bench at the top.
2. Review the seeded CAP example. Every trigger reads left to right: **type/name → conditions → action → run state**.
3. Advance the mission clock. At `00:01`, evaluate a pass to arm Flag 10.
4. Toggle `PLAYER_IN_PUSH_ZONE`, then evaluate. The example activates `CAP_RED` and sets Flag 20.
5. Toggle `CAP_RED_DEAD`, then evaluate. The completion message fires.
6. Add or edit triggers to match the mission logic you intend to build. Supported sandbox conditions are event on, flag equals, elapsed time, and always; supported actions are set/increase flag, show message, and activate/deactivate group.
7. Use **Trace** to inspect evaluation and action order. Use **Diagnostics** to find flag readers without writers, multiple flag writers, missing event signals, and empty action targets.
8. Export the bench as JSON for backup or handoff, and print the trigger list as a build card for the DCS Mission Editor.

The mission name, triggers, events, flags, groups, messages, and trace persist in browser `localStorage`.

## Important assumptions and limits

- Trigger Trace is **not** a parser or editor for `.miz` archives, `mission` Lua tables, MIST, MOOSE, or DCS scripting files.
- Its sequential evaluation pass is a teaching/debugging model chosen for readability. It does not claim to reproduce DCS's internal scheduler, event timing, trigger polling, AI behavior, scripting environment, or multiplayer synchronization.
- The condition and action vocabulary is intentionally small. Translate the result into the current Mission Editor using the exact trigger types, conditions, actions, groups, zones, flags, and values required by the mission.
- A structural diagnostic is not proof that a mission will work. Validate the built mission in DCS, and add visible debug messages where useful.
- **Once**, **Switched condition**, and **Continuous action** are modeled as practical rehearsal behaviors: fire once, fire on a false-to-true transition, or fire on every passing evaluation while true.
- This is a simulator companion, not real-world aviation guidance.

## Community and official signals

Accessed **2026-10-12**:

- Reddit r/hoggit — “Looking for help with creating missions in DCS.” (October 11, 2026). The discussion calls the Mission Editor a substantial learning task and recommends understanding trigger construction from left to right: https://www.reddit.com/r/hoggit/comments/1x3bcyn/looking_for_help_with_creating_missions_in_dcs/
- Reddit r/dcsworld — “Can someone teach me how to make a specific trigger in the editor? Is it even possible?” (October 9, 2026). Replies break a simple escort message into a named ONCE trigger, a zone condition, and a message action: https://www.reddit.com/r/dcsworld/comments/1x1dxy6/can_someone_teach_me_how_to_make_a_specific/
- Reddit r/hoggit — “Trigger zones not working” (August 5, 2026). Troubleshooting advice recommends a visible message action to establish whether the trigger itself fired before diagnosing the downstream action: https://www.reddit.com/r/hoggit/comments/1vghpur/trigger_zones_not_working/
- Reddit r/hoggit — “Looking for the best way to trigger AI troop loading with the stock Mission Editor” (July 8, 2026). The thread shows how stock-editor sequences quickly become flag, triggered-action, and stop-condition state problems: https://www.reddit.com/r/hoggit/comments/1uqypn3/looking_for_the_best_way_to_trigger_ai_troop/
- Eagle Dynamics Forums — “Request - Mission Editor mission test tools.” The long-running request specifically asks for manual trigger activation and live flag/trigger-state visibility: https://forum.dcs.world/topic/346483-request-mission-editor-mission-test-tools/
- Eagle Dynamics Forums — “Mission editor play test mode.” A separate recurring request asks for a faster test loop from the Mission Editor: https://forum.dcs.world/topic/224391-mission-editor-play-test-mode/
- Eagle Dynamics release changelog. The October 6, 2026 release is current, while 2026 entries continue to include Mission Editor and trigger fixes—evidence that final behavior must still be verified in the live simulator: https://www.digitalcombatsimulator.com/en/news/changelog/release/

## Privacy

The app makes no network requests. Bench data remains in the local browser profile unless explicitly exported as JSON.
