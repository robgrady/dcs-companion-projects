# Log Scope

Log Scope is a self-contained, offline DCS World log-triage workbench. It opens a local `dcs.log` or pasted log text, parses common DCS line structure, groups errors and warnings, detects evidence clusters, lets the user inspect surrounding lines, and creates a privacy-redacted incident brief for a squadron mate, forum post, or support ticket.

## Use it

1. Open `index.html` directly in a modern browser. No server, installation, account, network connection, or build step is required.
2. Immediately after a DCS problem, locate the current log at `%UserProfile%\Saved Games\DCS\Logs\dcs.log`.
3. Drop the file on **Open evidence**, choose it with the file picker, or use **Paste log**.
4. Record the case name, observed symptom, and the most recent patch, mod, driver, setting, or hardware change.
5. Review **Detected signals**. Selecting a signal opens its first matching line, surrounding context, and conservative next checks.
6. Filter by severity or component, search the complete loaded text, and inspect the last visible issue.
7. Add investigator notes as controlled tests are completed.
8. Keep redaction enabled when sharing. **Copy brief** or **Export brief** removes Windows usernames, IPv4 addresses, and email addresses from generated text.
9. Use **Load safe demo** to learn the interface without exposing a real log.

Keyboard shortcuts outside form fields: `/` focuses search, `E` filters errors/alerts/fatal lines, `W` filters warnings, `I` filters info lines, and `Esc` resets filters.

## Design and behavior

This is a **Command / Inspect** surface. Intake and case context establish the evidence set; severity/component filters reduce it; the central line table supports rapid scanning; and the right inspector keeps the selected line, nearby context, and next checks together. It intentionally avoids a dashboard composition and decorative metrics.

The app runs entirely in the browser. Log contents are held only in the current tab and are not written to `localStorage`. Case fields, redaction preference, and investigator notes are saved locally so an interrupted investigation can resume. The maximum accepted file size is 20 MB, and the table renders at most 3,000 matching rows at once for responsiveness while retaining the complete loaded log for search and export.

## Important assumptions

- Log Scope is a heuristic evidence organizer, not an Eagle Dynamics diagnostic engine and not proof of root cause.
- A crash marker such as `C0000005`, renderer term such as `DXGI_ERROR_DEVICE_REMOVED`, or mod path is a lead that requires context and controlled reproduction.
- DCS log formats, component labels, and messages can change. Unparsed lines remain searchable and visible as `OTHER`.
- The parser looks for recurring categories: crash/dump markers, graphics/render paths, memory/allocation language, Saved Games mod paths, Lua/script failures, authorization language, network components, and missing-file errors.
- Redaction targets common Windows user paths, IPv4 addresses, and email addresses. The user should still review any report before publishing because mission names, server names, paths, tokens, or other identifying text may remain.
- The app does not upload, repair, delete, move, or modify DCS files. It does not read a file until the user explicitly selects or drops it.
- A current `dcs.log` captured immediately after the event is more useful than an old or repeatedly overwritten log. Preserve DCS crash archives separately when they exist.
- Suggested A/B checks should be performed one controlled variable at a time. Do not treat repair, cleanup, driver replacement, BIOS changes, or hardware purchases as justified by one log line.

## Community signal

Sources accessed **2026-09-22**:

- [DCS Log Analyzer — r/hoggit](https://www.reddit.com/r/hoggit/comments/1we4j4i/dcs_log_analyzer/) announced an online analyzer that accepts `dcs.log` and crash files and highlighted common community demand for understandable log interpretation. Log Scope addresses the same demand with a local-only, no-upload workflow and a deliberately conservative evidence model.
- [DCS crashes after launching a second mission in multiplayer — Eagle Dynamics forums](https://forum.dcs.world/topic/391437-dcs-crashes-after-launching-a-second-mission-in-multiplayer/) shows a recent multiplayer crash report accompanied by `dcs.log` and diagnostic attachments. The case fields and incident brief are designed to preserve this reproduction context instead of sharing isolated error lines.
- [Constant crashes, different causes; requesting help with log interpretation — Eagle Dynamics forums](https://forum.dcs.world/topic/390018-constant-crashes-different-causes-requesting-help-with-log-interpretation/) is a direct recent request for help interpreting changing crash evidence. That signal shaped the grouped signatures, line context, and explicit warning against declaring a cause from the final line alone.
- [Weekly Questions Thread: Mar 02 — r/dcsworld](https://www.reddit.com/r/dcsworld/comments/1v1dk2v/weekly_questions_thread_mar_02/) directs users seeking technical help to include their `dcs.log`, reinforcing the need for a clean, shareable incident brief.
- [How to provide useful logs and crash reports — Eagle Dynamics Support](https://www.digitalcombatsimulator.com/en/support/faq/repair/#543/) identifies `dcs.log` and crash archives as central troubleshooting artifacts and documents their Saved Games location. Log Scope uses that official path in the intake guidance while leaving the original files untouched.

## Privacy and portability

Log Scope contains no analytics, remote fonts, external runtime dependencies, or network calls. All CSS and JavaScript are inline in `index.html`, so the app works from Dropbox via `file://`. Generated briefs are plain text and remain under the user's control.
