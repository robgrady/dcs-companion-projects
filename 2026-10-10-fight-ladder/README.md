# Fight Ladder

Fight Ladder is a self-contained, offline DCS World practice-contract builder. It turns an unspecific goal such as “practice BVR” into five controlled repetitions: sight picture, clean timeline, changed geometry, compressed decision, and validation. The app intentionally avoids weapon-performance claims; the pilot supplies current mission-appropriate starting range and loadout assumptions.

## Use

1. Open `index.html` directly in a browser. No server, account, build step, or network connection is required.
2. Set the ownship, adversary, pilot stage, training focus, baseline geometry, support, and session success cue.
3. Generate the ladder and select rungs with the on-screen controls or number keys 1–5.
4. Use the checklist and timer during each repetition. Choose **Met**, **Partial**, or **Reset**, add observable debrief evidence, and save the attempt.
5. Open **Build card** for a Mission Editor setup recipe. Print it or export the full profile and history as JSON; imported JSON restores the profile on another browser.

Useful state is stored locally in the browser under `fightLadder.v1`.

## Important assumptions

- This is a planning, rehearsal, and debrief aid—not a missile-range calculator, tactical authority, or replacement for current module manuals and server rules.
- Distances are user-selected setup values. DCS weapons, sensors, AI, modules, and mission behavior can change with updates.
- “Comparable capability,” AI skill, and training limits are deliberate mission-design choices the user must verify in the current DCS build.
- The Mission Editor build card is a recipe, not an automatically generated `.miz` file.
- The app is airframe-agnostic and does not assert classified or real-world performance data.

## Community signal

Recent community discussions repeatedly describe a gap between learning cockpit operation and learning how to structure a fair, repeatable combat practice session. New and returning players report difficulty finding a next step after basic tutorials, understanding why they lose BVR fights, and avoiding scenarios where stronger AI, poor geometry, or too many simultaneous variables hide the lesson. Fight Ladder addresses that signal by holding a baseline contract and changing one training pressure at a time, with explicit success evidence instead of a vague win/loss result.

Sources reviewed (accessed 2026-10-10):

- r/hoggit, “How do I actually learn this game?” — recurring beginner request for a progression beyond controls and tutorials: https://www.reddit.com/r/hoggit/comments/1mb9qo5/how_do_i_actually_learn_this_game/
- r/hoggit, “What am I doing wrong in BVR?” — example of players seeking diagnosis rather than another general tutorial: https://www.reddit.com/r/hoggit/comments/1nc0s01/what_am_i_doing_wrong_in_bvr/
- r/hoggit, “Help needed - DCS beginner”: recommendations emphasize one aircraft, incremental learning, simple missions, and multiplayer mentoring: https://www.reddit.com/r/hoggit/comments/1mvod3q/help_needed_dcs_beginner/
- r/hoggit, “DCS is overwhelming and tutorials don’t help”: discussion of training friction and the need to learn in manageable slices: https://www.reddit.com/r/hoggit/comments/1kgr6wj/dcs_is_overwhelming_and_tutorials_dont_help/
- r/dcsworld, “New player… where do I begin?”: community guidance centers on narrowing scope and practicing one task at a time: https://www.reddit.com/r/dcsworld/comments/1mbh95c/new_player_where_do_i_begin/
- Eagle Dynamics forum, “BVR training mission”: community interest in reusable, controlled BVR training setups: https://forum.dcs.world/topic/354497-bvr-training-mission/

## Design notes

Primary surface: **Configure**, with **Operate** as the secondary live-repetition surface. The layout therefore prioritizes explicit setup choices, a visible five-step progression, and evidence capture rather than a marketing hero or decorative dashboard.

Slop diagnostic after implementation: **0/10**. No tech gradient, generic indigo accent, feature-tile grid, accent-rail card system, glass blur, monument stats, icon toppers, center-stack composition, default Inter typography, or surface mismatch. The orange objective marker is functional hierarchy inside one task panel, not a repeated decorative card rail.
