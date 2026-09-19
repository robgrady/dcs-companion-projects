# Button Check

Button Check is a self-contained, offline DCS World radio-call interpreter and preset trainer. It turns terse calls such as “Uniform button 3” into a repeatable identify → confirm → cross-check → fallback workflow, then generates a compact printable kneeboard card from the pilot’s own mission data.

## Use

1. Open `index.html` directly in a modern browser; no server, installation, or network connection is required.
2. In **Preset map**, replace the clearly marked fictional training channels with the aircraft and mission presets from the current briefing or kneeboard.
3. In **Live desk**, decode the requested radio and button, enter its mapped frequency, and check the call. Response time, score, and recent history stay in browser `localStorage`.
4. In **Kneeboard**, edit the fallback contract, copy a plain-text card, print the compact card, or export the entire profile as JSON.
5. Use **Import JSON** to restore or move a profile to another browser.

## Assumptions and limits

- The six included channels are fictional training data, deliberately labeled as such. They are not valid presets for any DCS module, campaign, mission, or server.
- Radio labels vary by aircraft and mission. For training, Button Check maps `UHF` to Uniform / COM 1 phrasing and `VHF` to Victor / COM 2 phrasing; always follow the actual cockpit and briefing.
- A preset number is only a channel selector. The mission or data cartridge determines the frequency assigned to it.
- The app does not inspect `.miz` files, DTC files, or DCS state. The user owns verification against the current mission briefing.
- Manual frequency entry is presented as a recovery habit, not a substitute for module-specific radio procedures.

## Community signal

Built on 2026-09-19 after reviewing current DCS community reports showing that radio shorthand, preset loading, and campaign trigger recovery remain recurring friction points:

- [Mission 0 Fly to Guam — radio channels not working](https://forum.dcs.world/topic/385007-mission-0-fly-to-guam-radio-channels-not-working/) — a 2026 campaign support thread documents a wrong UHF preset, the need to manually tune `251.0`, and a DTC comm-partition workaround. Accessed 2026-09-19.
- [Sentry Pacific 2025 Campaign](https://forum.dcs.world/topic/383629-sentry-pacific-2025-campaign/page/2) — 2026 replies explicitly explain that “button” means preset channel and distinguish COM 1 / Uniform from COM 2 / Victor, illustrating real player confusion around radio call syntax. Accessed 2026-09-19.
- [Mission “Lights, camera, action”](https://forum.dcs.world/topic/385599-mission-lights-camera-action/) — players report missing mission flow after tuning or interpreting the wrong radio/task sequence, reinforcing the need for an at-a-glance call and agency cross-check. Accessed 2026-09-19.
- [I understand why lots of people give up on DCS early now](https://www.reddit.com/r/dcsworld/comments/1wbgcdf/i_understand_why_lots_of_people_give_up_on_dcs/) — a recent r/dcsworld discussion describes vague training instructions, acronym overload, hard-to-hear calls, silent failure after a missed action, and the burden of simultaneous tasks. Accessed 2026-09-19.
- [Learning DCS Without Feeling Overwhelmed](https://www.reddit.com/r/dcsworld/comments/1v9xvtl/learning_dcs_without_feeling_overwhelmed_or_why/) — a recent community guide identifies fragmented training and cognitive overload as beginner traps and advocates focused, repeatable practice. Accessed 2026-09-19.

These signals favored a narrow radio-language rehearsal tool over another general mission planner or checklist builder.

## Data and privacy

All state is stored locally under the browser key `buttonCheck.v1`. Export occurs only when requested. The app makes no network requests and includes no external runtime dependencies.
