# PID Gate

PID Gate is a self-contained, offline DCS World multiplayer identification and release-discipline trainer. It presents short, airframe-agnostic contact scenarios and asks the pilot to **hold**, **query**, or **commit** based on the evidence available, the mission corridor, and a configurable server rules contract.

## Why it exists

The November 2026 closure of the 4YA training-server network removed a familiar, casual multiplayer on-ramp. Recent community discussions show pilots looking for replacement servers, new players asking where they can learn without judgment, and first-time multiplayer pilots worrying about unwritten rules such as monitoring comms, taxi discipline, and confirming a target is not friendly. PID Gate focuses on one transferable habit that matters on every replacement server: do not let a sensor impression become a weapons decision until the required evidence and local rules agree.

This is a simulation training aid, not a real-world tactical reference. It deliberately avoids module-specific switchology and does not claim to reproduce any military rules of engagement. The active server briefing, mission designer, and human controllers always outrank this tool.

## How to use

1. Open `index.html` directly in a browser. No server, install, or network connection is required.
2. Read the current contact card and inspect the evidence ledger.
3. Choose **Hold**, **Query**, or **Commit** before the clock expires.
4. Read the debrief, then advance to the next case.
5. Open **Rules contract** to adjust the minimum independent confirmations and optional requirements for hostile declaration, corridor clearance, or visual identification.
6. Use **Review misses** to repeat failed cases, **Reset run** to begin again, or **Print card** for a compact kneeboard reference.

Keyboard shortcuts: `1` Hold, `2` Query, `3` Commit, `N` next case, `R` repeat current case, `?` shortcut help.

## Decision model and assumptions

- **Hold** is correct when the contact is not an immediate threat and required evidence is absent or conflicting.
- **Query** is correct when another call, sensor cross-check, or short delay could resolve a meaningful ambiguity.
- **Commit** is correct only when the scenario satisfies the active rules contract and no explicit friendly-risk conflict remains.
- Evidence sources are intentionally generic: declaration, onboard classification, offboard correlation, visual identification, route/corridor fit, and behavior.
- A declaration or sensor classification is represented as one input, not automatic authority to fire.
- The scenarios are fictional and use invented callsigns, tracks, ranges, and mission geometry.
- Progress, rules, and recent results are stored only in the browser's `localStorage`.

## Community signals reviewed

Accessed 2026-11-12:

- r/hoggit — “Where are y'all going after 4YA” documents pilots comparing replacement multiplayer environments after the announced November shutdown: https://www.reddit.com/r/hoggit/comments/1x1vcjm/where_are_yall_going_after_4ya/
- r/hoggit — “RIP 4YA” includes strong responses from pilots who learned multiplayer on the casual PvE/training servers and concern about losing that entry point: https://www.reddit.com/r/hoggit/comments/1wldav2/rip_4ya/
- r/hoggit — “Complete New Guy - DCS World” asks for patient, nonjudgmental beginner communities and shows continuing demand for structured onboarding: https://www.reddit.com/r/hoggit/comments/1xc96he/complete_new_guy_dcs_world/
- r/dcsworld — “Joining Multiplayer for the first time” centers on unwritten rules; replies emphasize taxi awareness, monitoring frequencies, plain-language calls, and confirming a target is not friendly: https://www.reddit.com/r/dcsworld/comments/1sp9fje/joining_multiplayer_for_the_first_time/
- Eagle Dynamics newsletter — confirms the 4YA Training Servers closed on 2026-11-01 and frames the resulting question as “Where do I go now?”: https://www.digitalcombatsimulator.com/en/news/newsletters/f9887883bb02214ecde9b9d41396c3a6/

## Privacy and portability

The app has no external runtime dependencies, analytics, requests, or accounts. Delete the browser's local site data for the file to erase saved state. Printing uses the browser print dialog.
