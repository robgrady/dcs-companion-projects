# Airwork Wire

Airwork Wire is a self-contained, offline DCS World fundamentals practice coach. It gives a pilot a timed, repeatable cadence for basic aircraft-control work and records which variable—altitude, heading, or airspeed—broke the declared tolerance first at each gate.

## Use

1. Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.
2. Choose one of six profiles: Straight & Level, Level Turns, Climb / Descent, Speed Change, Steep Turn, or Pattern Stability.
3. Enter an airframe note and set personal altitude, heading, and airspeed tolerances. Set the gate duration and number of gates.
4. Click **Arm new run**, establish the maneuver in DCS, then start the timer. Airwork Wire supplies one scan or control cue per gate and sounds a short tone when time expires.
5. At each gate, record exactly one primary result: Clean, Altitude, Heading, or Airspeed. Use the buttons or keyboard keys `1`–`4`; use Space to start or pause.
6. Review the live event wire and recurring first-break diagnosis. Add one next-run correction, save it, repeat the same contract, and compare evidence.
7. Completed runs persist in browser `localStorage`; export all saved gate evidence as CSV or print a compact debrief.

## Important assumptions

- This is a practice-cadence and self-debrief aid, not a DCS telemetry connection, flight instructor, flight-model analyzer, control-tuning tool, or source of aircraft limitations.
- The included cues are general training prompts, not module-specific procedures. The pilot must use the applicable DCS manual, training material, squadron standards, and aircraft limitations.
- Tolerances are deliberately user-defined. The defaults are starter values, not official standards and not a claim that every aircraft or maneuver should meet them.
- A “Clean” result means the pilot judged all three tracked variables inside the declared personal contract. Airwork Wire cannot independently verify that judgment.
- Log the first meaningful deviation, not the largest late symptom. The resulting diagnosis is only as useful as the pilot’s observation discipline.
- The timer continues only while the page is active and the run is unpaused. Browser throttling or sleeping the computer can affect timing.
- Audio depends on browser support and may require a user interaction before the first tone.
- Exported CSV files and printed debriefs may contain personal notes. Review them before sharing.

## Why this exists

Current DCS community discussion shows a repeated gap between learning cockpit systems and being able to control the aircraft comfortably enough for those systems to become useful. A November 2026 beginner described difficulty staying level, banking, and landing even after training; replies emphasized basic repetition, trimming, control setup, traffic-pattern practice, and making flying sufficiently automatic before adding targeting workload. Nearby discussions likewise recommend learning by doing, practicing known skills until they are routine, and adding one skill at a time. Airwork Wire turns that broad advice into a small repeatable practice contract without pretending to replace in-game instruction or a human coach.

Sources reviewed on **2026-11-19**:

- r/dcsworld, **“Even after training I am still really bad at flying…”** (2026-11-10). The pilot specifically reports difficulty staying level, banking, and landing; responses emphasize control-axis checks, trim-dependent flying, traffic patterns, repeated practice, and making basic flying subconscious before adding systems workload: https://www.reddit.com/r/dcsworld/comments/1xsz63p/even_after_training_i_am_still_really_bad_at/
- r/dcsworld, **“F16 training”** (2026-11-08). Replies repeatedly recommend beginning with basic flying and in-game training, learning by doing, practicing focused tasks, and using small personal checklists rather than trying to absorb an entire manual first: https://www.reddit.com/r/dcsworld/comments/1xqtsnw/f16_training/
- r/dcsworld, **“Help with dcs”** (2026-11-03). Community guidance includes “practice what you know until it’s boring then add another skill,” reinforcing progressive, repeated skill blocks: https://www.reddit.com/r/dcsworld/comments/1xn3jql/help_with_dcs/
- r/hoggit, **“Weekly Questions Thread Nov 17”** (2026-11-17). The current recurring beginner thread points pilots toward a continuously available training server and dedicated practice ranges, evidence that structured repetition remains an active community need: https://www.reddit.com/r/hoggit/comments/1xy5j3g/weekly_questions_thread_nov_17/
- r/dcsworld, **“Learning DCS”** (2026-09-26), reviewed 2026-11-19. A new pilot directly asks for practice and training methods, adding to the recurring demand for a usable learning process rather than more reference material: https://www.reddit.com/r/dcsworld/comments/1wqdd8z/learning_dcs/

## Design notes

This is primarily an **Operate** surface with a secondary **Learn** function: the pilot arms and runs a timed practice session, records one result per gate, and inspects a live debrief. Action state, cadence, and evidence dominate; there is no marketing hero or decorative dashboard. The visual system uses restrained cockpit-field neutrals, amber for action, green for clean evidence, instrument-category color only where it improves scanning, deliberate condensed typography, visible focus states, responsive mobile controls, keyboard operation, reduced-motion handling, and print styling.

### Anti-slop audit

- Initial score: **0/10**. No tech gradient, generic indigo, feature-tile grid, accent rail, unearned blur, monument stat, icon topper, center stack, default Inter, or wrong-surface composition fired.
- Final score: **0/10** after implementation review. The Operate composition remains dominant; the circular timer is functional session state rather than decorative data, and no compositional tell required repair.
