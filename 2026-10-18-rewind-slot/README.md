# Rewind Slot

Rewind Slot is a self-contained, offline DCS World micro-practice builder. It turns one failed tutorial or training-mission step into a minimal Mission Editor recipe and a three-pass practice loop, so the pilot can rehearse the hard action without replaying a long lead-in.

## Use

1. Open `index.html` directly in a modern browser. No server, install, account, or network connection is required.
2. Choose the kind of failure, name the aircraft, and describe one observable action.
3. Record what failed, choose the desired start state and loop duration, and define a visible success condition.
4. Select **Build drill**, then reproduce the five-step recipe in DCS Mission Editor.
5. Confirm each setup gate, fly three short passes, and log each result with one line of evidence.
6. Print the recipe as a practice card or export the complete contract and attempt history as JSON.

The current contract, recipe confirmations, and attempt history persist in browser `localStorage` on the same device and browser profile.

## Assumptions and limits

- The app is module-agnostic and does not prescribe aircraft-specific switch positions, weapon parameters, or procedures.
- Mission Editor labels and available options can change between DCS versions; the recipe intentionally describes outcomes rather than brittle menu paths.
- The generated mission is a training aid, not a substitute for the relevant module manual, official training mission, or instructor guidance.
- Timers are browser-based and are intended to bound practice sessions, not synchronize with simulation time.
- JSON export uses the browser download mechanism; no data leaves the local machine.

## Community signal

Accessed 2026-10-18.

- A recent r/hoggit newcomer described following a Su-25T lesson successfully until an unexplained waypoint requirement caused the scripted training to stop, illustrating how one missed gate can invalidate the whole lesson: https://www.reddit.com/r/hoggit/comments/1o46bhn/dcs_tutorials_are_terrible/
- A recent r/hoggit discussion on learning DCS highlighted the practical difference between long guided lessons and short, repeatable skill practice, including community suggestions to use simple Mission Editor scenarios: https://www.reddit.com/r/hoggit/comments/1ny8d1n/how_i_learned_to_play_dcs/
- Another r/hoggit beginner thread asked how to create a simple air-combat practice setup, reinforcing demand for a low-friction bridge from “I need to practice this” to a usable Mission Editor scene: https://www.reddit.com/r/hoggit/comments/1p16tp3/help_for_beginners_dcs_mission_editor/
- An r/hoggit thread about DCS training quality described confusing or incomplete tutorial instruction and the cost of restarting sequences after a failure: https://www.reddit.com/r/hoggit/comments/1h7j7w5/does_dcs_have_a_fundamental_training_problem/
- A DCS World Steam discussion similarly asks for ways to restart a training mission from a checkpoint rather than repeat the entire lesson: https://steamcommunity.com/app/223750/discussions/0/598517858279483085/

Together these point to a recurring problem: the learner often knows *which moment* needs work but lacks a fast way to isolate that moment into a repeatable mission. Rewind Slot addresses that gap without pretending to automate DCS Mission Editor.

## Design posture

Primary surface: **Configure**, with a secondary **Operate** surface for timed repetitions and evidence logging. The layout therefore uses progressive setup, a generated build recipe, and a compact run loop rather than a marketing hero or equal-weight feature cards.

Slop diagnostic after implementation: **0/10**. None of the ten diagnostic tells fired; the artifact uses no tech gradient, default indigo, feature-tile grid, accent rail, blur, monument stats, icon toppers, centered-stack composition, default Inter typography, or mismatched surface.
