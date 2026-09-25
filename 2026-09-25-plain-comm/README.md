# Plain Comm

Plain Comm is a self-contained, offline DCS World phrase decoder for players who can follow the flying but lose the thread when a tutorial, briefing, controller, or experienced wingman compresses an idea into an acronym or brevity call. It provides a searchable plain-language lexicon, a radio-call scratchpad that marks recognized terms, a recall drill, favorites, user-authored squadron terms, JSON backup, and printable reference cards.

## Use

1. Open `index.html` directly in a modern browser. No server, account, network connection, or build step is required.
2. In **Lexicon**, search by acronym, phrase, or plain-English idea. Filter by category, starred terms, or custom terms.
3. Select a term to see its plain meaning, typical DCS conversation context, and a practical “when you hear it” cue.
4. In **Decode a call**, paste or type a radio call. Plain Comm highlights exact known phrases and lists their meanings without pretending to infer the controller's tactical intent.
5. In **Recall drill**, run a ten-question recognition set. Active lexicon filters shape the drill when at least eight terms match.
6. In **My terms**, add squadron, server, campaign, or module-specific vocabulary.
7. Use **Export** and **Import** to back up or transfer favorites, custom terms, selection state, and drill history.

Saved state uses browser `localStorage`. Clearing browser site data can remove it; JSON export is the durable backup path.

## Why this project

Recent DCS community discussions repeatedly describe a steep vocabulary barrier: new players encounter abbreviations before they understand basic game structure, struggle to decode tutorial and aviation language, and ask for a consolidated glossary rather than searching every unfamiliar term individually. September 2026 beginner posts specifically criticize unexplained acronyms and wording that assumes prior aviation knowledge. Older forum requests show the same problem across the core simulator and individual modules, supporting a fast second-screen decoder that works across aircraft.

Sources reviewed on **2026-09-25**:

- Reddit / r/dcsworld, “I understand why lots of people give up on DCS early now” (2026-09-09) — a learner says training missions use unexplained acronyms, vague instructions, and hard-to-hear narration, making it easy to lose the thread: https://www.reddit.com/r/dcsworld/comments/1wbgcdf/i_understand_why_lots_of_people_give_up_on_dcs/
- Reddit / r/dcsworld, “Struggling to comprehend this simulator” (2026-09-08) — an F/A-18C learner says training wording assumes aviation terminology they do not have: https://www.reddit.com/r/dcsworld/comments/1wal32y/struggling_to_comprehend_this_simulator/
- Reddit / r/dcsworld, “Learning DCS Without Feeling Overwhelmed (or why DCS Isn't as Hard as It Looks)” (2026-07-29) — a community learning guide describes the burden of manuals, fragmented tutorials, and unfamiliar systems language: https://www.reddit.com/r/dcsworld/comments/1v9xvtl/learning_dcs_without_feeling_overwhelmed_or_why/
- Eagle Dynamics Forums, “Abbreviations in DCS, where to look?” — a new player asks for one comprehensive list instead of repeatedly searching unfamiliar military terminology; replies note that “acronym hell” is real and often aircraft-specific: https://forum.dcs.world/topic/304206-abbreviations-in-dcs-where-to-look/
- Eagle Dynamics Forums, “F-4E Manual Requests: Acronym Tooltips + Inflight Dark Mode” — a new DCS player asks for in-context acronym explanations to avoid leaving the manual to hunt down meanings: https://forum.dcs.world/topic/353064-f-4e-manual-requests-acronym-tooltips-inflight-dark-mode/
- Air Land Sea Application Center, *Multi-Service Tactics, Techniques, and Procedures for Multi-Service Brevity Codes*, May 2020 — public reference consulted for the general meaning and caution required around brevity terminology: https://www.alsa.mil/Portals/9/Documents/mttps/brevity_2020.pdf

The app is intentionally not a clone of the existing Lesson Lifeline project: Lesson Lifeline preserves user-authored procedural steps; Plain Comm is a browsable vocabulary and recognition tool designed for rapid decoding across lessons, briefings, and multiplayer calls.

## Assumptions and boundaries

- Definitions are concise DCS learning explanations, not an authoritative real-world communications publication.
- DCS modules model different eras, sensors, weapons, controls, and terminology. The current module manual and mission brief take priority.
- Community usage can be looser than formal brevity. Several entries explicitly flag where common DCS speech can hide important distinctions.
- The call decoder recognizes exact terms and phrases. It does not parse bearings, identify contacts, evaluate rules of engagement, or recommend tactics.
- “When you hear it” cues are awareness prompts, not aircraft procedures or safety instructions.
- Custom terms are user-authored and are not validated.
- Browser printing prints the currently selected term card.
- Data remains local unless the user explicitly exports a JSON backup.

## Design note

The primary surface is **Explore**, with **Learn** secondary: search, category filters, a dense scannable index, and a focused detail pane lead the composition; the drill reinforces recognition without turning the project into a course dashboard. The visual system borrows from a field reference binder—bone paper, dark olive, signal orange, serif explanation type, and compact monospaced labels—without external fonts or runtime dependencies.

Slop diagnostic before repair: **1/10**; the initial utility mark risked reading as an unnecessary icon topper. It was reduced to a small masthead registration mark rather than a repeated component pattern. Final score: **0/10**. No tech gradient, generic indigo, equal feature-tile grid, accent rail, blur, monument stat, repeated icon topper, center-stack composition, default Inter, or surface mismatch fires.

## Files

- `index.html` — complete offline app with inline CSS, data, and JavaScript
- `README.md` — instructions, assumptions, design record, and community sources
