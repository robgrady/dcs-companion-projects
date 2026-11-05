# Ramp Reply

Ramp Reply is a self-contained, offline DCS World ground-crew call and fault-isolation desk. It helps a pilot distinguish four different questions that are often collapsed into “the ground crew does not work”: whether the communications menu opened, whether the requested service was available, whether an acknowledgment was heard, and whether service activity was actually observed.

## Use

1. Open `index.html` directly in a modern browser. No web server or network connection is required.
2. Enter the aircraft, requested service, environment, and intended voice path.
3. Confirm the four pre-call condition families: parking, voice path, aircraft state, and mission/location support.
4. Transmit once, then mark **Acknowledged** or **No reply**. If acknowledged, separately record visible service activity.
5. On failure, follow the single controlled next test rather than changing several conditions or repeating the same request.
6. Close the run to save it locally. Use **Export** for a JSON backup or **Print proof card** for a compact reference.

Useful state and up to 40 completed runs persist in browser `localStorage` under `rampReply.v1`.

## Important assumptions

- DCS modules, crew stations, carriers, FARPs, mission scripts, coalition ownership, Easy Communications, and multiplayer server rules can change what services are available and what cockpit state is required.
- Ramp Reply deliberately does **not** claim one universal ground-crew procedure. The module manual, mission briefing, and current DCS behavior remain authoritative.
- The application is an evidence and controlled-testing aid. Its recommendations isolate categories of conditions; they do not modify DCS or inspect the simulator.
- Timing records begin when **Transmit request** is pressed and stop when the result is recorded.

## Community signal

Built after reviewing current DCS community discussions on 2026-11-05:

- A recent r/hoggit weekly questions thread included a Hornet pilot who could not get ground crew to respond for refueling after landing; the discussion identified the cockpit intercom/hot-mic path as the missing condition. This is the immediate signal for a small, repeatable call-path diagnostic instead of another aircraft-specific checklist: https://www.reddit.com/r/hoggit/comments/1wyo9pz/weekly_questions_thread_oct_06/ (accessed 2026-11-05).
- A recent r/dcsworld weekly thread continued to collect recurring setup and “what am I missing?” questions, including module-specific behavior that worked in one context but not another. That reinforces the need to preserve context and compare one variable at a time: https://www.reddit.com/r/dcsworld/comments/1wy12p1/weekly_thread_20261005_questions_on_dcs_pcs/ (accessed 2026-11-05).
- Eagle Dynamics’ 2026-10-02 update shipped a wide range of module and campaign changes. The continuing update cadence is a reason to record a known-good condition set instead of treating remembered behavior as permanent: https://www.digitalcombatsimulator.com/en/news/newsletters/a83eff3b8516b7d0a392c2a219e704c8/ (accessed 2026-11-05).

## Files

- `index.html` — complete application, with inline CSS and JavaScript.
- `README.md` — usage, assumptions, and source record.
