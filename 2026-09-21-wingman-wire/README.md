# Wingman Wire

Wingman Wire is a self-contained, offline command-and-recovery desk for DCS World single-player pilots flying with an AI wingman. It makes the command loop explicit: check tasking gates, stage an intent, record acknowledgment and observed behavior, watch unresolved task age, and choose a recovery action before ambiguity becomes separation or fuel loss.

## Use it

1. Open `index.html` directly in a modern browser. No server, installation, network connection, or build step is required.
2. Open **Mission setup** and record the aircraft, fuel floor, radio/PTT reminder, and any module-specific command-path note.
3. Set the current mission phase, wingman state, and reported fuel.
4. Complete the four tasking gates before attack commands when practical: intent, deconfliction, fuel, and communications.
5. Select one of the six command families. Edit the displayed menu path to match the aircraft, mission, bindings, and current DCS menu.
6. Put the command on the wire, then record **Affirm**, **No response**, and finally **Complete** when the observed outcome closes the loop.
7. Use the recovery monitor when task age rises or acknowledgment is absent. Rejoin, cover-me, and RTB actions are always one selection away.
8. Export a JSON run log for debrief/backup or print the current command card and log.

Keyboard shortcuts outside form fields: `1`–`6` stage command families, `A` records an affirmation, `N` records no response, and `C` closes the active task.

## Design and behavior

This is an **Operate** surface rather than a dashboard or reference page. The central command board and live task dominate; wingman state and tasking gates sit to the left, while aging and recovery cues remain visible on the right. The app stores mission setup, current state, gates, active task, and log in browser `localStorage`.

## Important assumptions

- Wingman Wire does not connect to DCS, press radio keys, inspect mission state, or guarantee an AI response. It is a pilot-side intent and evidence tool.
- DCS radio menus and available commands vary by aircraft, coalition, mission, radio selection, easy-communications setting, bindings, and simulator version. The supplied paths are editable orientation labels, not guaranteed exact key sequences.
- “Affirm” means the pilot heard or otherwise confirmed an acknowledgment; “Complete” should be used only after observing the intended result or deliberately terminating the loop.
- The four gates are decision prompts, not a substitute for aircraft procedures, mission rules, weapons employment limits, or tactical judgment.
- Fuel values are intentionally unit-agnostic because DCS modules report fuel in different formats. The pilot defines and interprets the fuel floor.
- A 30- or 60-second task-age warning is an attention cue, not a universal tactical limit.
- Browser storage is specific to the browser/profile and local file origin. JSON export is the portable record.

## Community signal

Sources accessed **2026-09-21**:

- [Current state of AI — r/hoggit](https://www.reddit.com/r/hoggit/comments/1o5u1ag/current_state_of_ai/) describes AI wingmen failing to follow commands, consuming fuel, crashing, or disappearing after tasking. That recurring uncertainty shaped the explicit acknowledgment, task-age, observed-result, and recovery loop.
- [Wingman ignores orders — Eagle Dynamics forums](https://forum.dcs.world/topic/386346-wingman-ignores-orders/) reports a wingman acknowledging commands without reliably executing them. Wingman Wire therefore separates the radio acknowledgment from observed completion instead of treating “copy” as success.
- [AI Wingman Issues — r/hoggit](https://www.reddit.com/r/hoggit/comments/1oc8hsf/ai_wingman_issues/) reflects continuing player difficulty getting wingmen to engage and uncertainty about correct radio/menu use. The app keeps the menu path editable and preserves the actual command path used with each log entry.
- [DCS 2026 roadmap discussion — r/hoggit](https://www.reddit.com/r/hoggit/comments/1qsnb06/dcs_2026_and_beyond_roadmap/) highlights community attention on planned AI command-and-control and behavior improvements. A version-independent command/debrief record remains useful while behavior evolves.
- [DCS update 2.9.22.18362 changelog](https://www.digitalcombatsimulator.com/en/news/changelog/stable/2.9.22.18362/) includes AI aircraft fixes involving waypoint behavior, refueling, and fuel-related logic. This supports treating wingman behavior as changing software that should be observed and debriefed rather than assumed.

## Privacy and portability

Wingman Wire contains no analytics, external runtime dependencies, fonts, or network calls. All CSS and JavaScript are inline in `index.html`; data stays in the local browser unless the user exports or prints it.
