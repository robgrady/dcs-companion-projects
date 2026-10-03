# Pad Check

Pad Check is a self-contained, offline DCS World gamepad setup and rehearsal workbench. It helps pilots build a compact controller map, see live Gamepad API inputs, catch duplicate assignments, practice eyes-out recall, and complete an explicit in-DCS verification gate before treating a profile as ready.

## Use

1. Open `index.html` directly in a modern browser. No server, account, installation, build step, or internet connection is required.
2. In **Setup**, name the aircraft/seat and mission focus, choose the controller label set, and select the modifier you intend to configure in DCS.
3. Connect the controller and press a physical button. Select **Scan controllers** if the live monitor does not start automatically; browser privacy rules may require an initial controller input.
4. In **Map**, edit the starter actions, layers, and physical controls. Select **Listen** on a row and press a gamepad button to capture it. Resolve open flight-critical rows and unintended duplicate slots.
5. In **Rehearse**, run a 10-call eyes-out drill. With a recognized gamepad, matching button presses can grade the prompt; without one, reveal the answer and self-grade.
6. In **Preflight**, verify the plan inside the exact DCS aircraft and seat. Record mismatches, finish all six gates, and back up the actual DCS controller profile.
7. Use **Export JSON** to preserve the Pad Check planning profile and **Print card** for a compact reference.

The profile, mappings, checks, notes, and drill history persist in browser `localStorage` for this file URL.

## Important assumptions

- Pad Check is a planning, input-monitoring, and rehearsal companion. It does **not** read, generate, modify, or replace DCS `.diff.lua` controller files.
- DCS Options → Controls is authoritative for available command names, device columns, modifiers, axis behavior, context-sensitive controls, and conflict warnings.
- The starter map is deliberately airframe-agnostic. Labels such as “TDC depress,” “weapon release,” and “countermeasures” must be matched to the exact command names and HOTAS logic of the selected module.
- Browser Gamepad API button indices and labels are common conventions, not a guarantee for every device or browser. The live monitor should be used to confirm the physical control before entering the binding in DCS.
- Duplicate physical assignments are warnings, not proof of an error. Some overlaps are safe because DCS command contexts differ; verify every intentional overlap in the cockpit.
- The drill recognizes simple button-label matches. Multi-button chords, axes, hats reported as axes, and unusual driver mappings should be revealed and self-graded.
- Browser storage belongs to the browser/profile and local file origin. Export JSON before clearing browser data, renaming the folder, or moving to another computer.

## Community signal

Sources reviewed on **2026-10-03**:

- r/hoggit weekly questions thread (2026-09-01): a new player using an Xbox controller and keyboard asked whether controller inputs had been registered correctly and how to configure movement. This is a current example of the setup ambiguity Pad Check’s live input monitor and explicit verification gates address: https://www.reddit.com/r/hoggit/comments/1n5o0n5/weekly_questions_thread_sep_01/
- r/dcsworld, “Beginner DCS Player – Need Help with Controls, Training & Tips” (2026-08-24): the author reported using an Xbox controller, struggling with controls and training, and asked for must-have keybind guidance. This directly supports a priority-based starter map rather than an exhaustive command dump: https://www.reddit.com/r/dcsworld/comments/1mzodfw/beginner_dcs_player_need_help_with_controls/
- r/hoggit, “New to DCS, about gamepad controller” (2026-05-05): replies pointed a new controller pilot toward layouts built around modifiers and controller-focused schemes, reinforcing the need to make layers visible and rehearse them: https://www.reddit.com/r/hoggit/comments/1kfc1vd/new_to_dcs_about_gamepad_controller/
- r/dcsworld, “I understand why lots of people give up on DCS” (2026-09-09): the discussion highlights the broader beginner burden of controller setup, unclear training guidance, terminology, and repeated restarts. Pad Check intentionally narrows one part of that burden into a saved setup-and-proof workflow: https://www.reddit.com/r/dcsworld/comments/1wbgcdf/i_understand_why_lots_of_people_give_up_on_dcs/
- Eagle Dynamics forum, “Guide: DCS with a Gamepad” (2023-02-10, still referenced by current community answers): a long-running community guide demonstrates sustained demand for practical controller layouts and modifier techniques: https://forum.dcs.world/topic/316262-guide-dcs-with-a-gamepad/

The recurring signal is not that a gamepad needs to imitate a full HOTAS. New and space-constrained pilots need a deliberate minimum set, visible modifier layers, confirmation that the browser/device sees the intended inputs, and a short rehearsal loop before entering a demanding training mission.

## Privacy and portability

Pad Check has no analytics, network calls, external runtime dependencies, or build step. All operational data remains in browser storage unless the user explicitly exports a JSON file or prints the mapping.
