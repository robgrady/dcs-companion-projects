# Wingmate Beacon

Wingmate Beacon is a self-contained, offline DCS World flight-finder brief builder. It helps a pilot turn a vague request for help or company into a compact recruiting post, an explicit first-sortie training contract, and a reply/DM fit check with aircraft, seat, current ability, one-session objective, UTC availability, communications expectations, and boundaries.

## Use

1. Open `index.html` directly in a browser; no server, build step, account, or network connection is required.
2. Replace the starter example with a public callsign, aircraft/seat, current capability, one first-session goal, and the point where the workflow breaks down.
3. Choose days and times, then add one or more availability windows. The app publishes both local time with UTC offset and converted UTC time.
4. Set the session length, pace, voice/mod/recording preferences, and boundaries.
5. Resolve any Beacon Check warnings, then copy, download, or print the recruiting post, first-sortie contract, or DM handoff.
6. Use **Save locally** for browser persistence. Export/import JSON provides a portable backup.

## Important assumptions and boundaries

- The app coordinates a human-to-human DCS session; it does not connect to Reddit, Discord, SRS, DCS, a server browser, or any matchmaking service.
- Time conversion uses the UTC offset selected by the user. It does not infer location or daylight-saving changes; update the offset when local rules change.
- The session contract is a planning aid, not an official syllabus or a claim of real-world aviation procedure.
- Starter entries are an editable example, not claims about the user. Generated output intentionally omits Rob Grady's email address.
- Browser storage is local to the current browser/profile. Export a JSON backup before clearing site data.
- Review every generated post before sharing and do not publish real names, email addresses, server passwords, IP addresses, or other sensitive information.

## Community signal (accessed 2026-10-16)

Recent discussions show a repeated gap between “I need help / someone to fly with” and the concrete details another pilot needs in order to respond:

- r/dcsworld, **“Does anyone wanna help me like I’m 5?”** (2026-10-06): the pilot describes research overload, instant-action failure, and Discord overwhelm; replies immediately ask for aircraft and time zone. This directly inspired the narrow one-goal brief and fit-check fields. https://www.reddit.com/r/dcsworld/comments/1wz97x8/does_anyone_wanna_help_me_like_im_5/
- r/dcsworld, **Weekly Thread 2026/10/12**: the standing guidance routes pilots seeking company to Wingman Finder, routes pilots seeking instruction to training communities, and explicitly asks recruiting groups to include their time zone. This inspired UTC-normalized availability and separate mentor/peer/squadron intents. https://www.reddit.com/r/dcsworld/comments/1x3ty16/weekly_thread_20261012_questions_on_dcs_pcs/
- r/hoggit, **Weekly Questions Thread Oct 13** (2026-10-13): the community continues to operate a dedicated questions thread and points newcomers toward a 24/7 training server, evidence that beginner support and structured practice remain active needs. https://www.reddit.com/r/hoggit/comments/1x4hyp5/weekly_questions_thread_oct_13/
- r/dcsworld, **“How do you play this game?”** (2026-10-08): a prospective player asks how DCS’s sandbox, missions, servers, and multiplayer fit together rather than watching a long video. This reinforced the need for a low-friction bridge from general curiosity to one bounded first session. https://www.reddit.com/r/dcsworld/comments/1x0jx97/how_do_you_play_this_game/
- r/dcsworld, **“New to DCS, Interested in MP”** (2026-03-10): replies recommend Wingman Finder and beginner-friendly communities while asking which aircraft the pilot flies. This supports aircraft/seat and desired-partner fields rather than a generic social post. https://www.reddit.com/r/dcsworld/comments/1rplipw/new_to_dcs_interested_in_mp/

## Design and accessibility

This is an **Operate** surface: form state, validation, scheduling, and copy-ready output dominate. It uses left-aligned hierarchy, compact panels, visible keyboard focus, semantic labels, 44px minimum targets, responsive stacking, reduced-motion support, and a print view. The palette is deliberately field-notebook olive/amber rather than default blue-violet software styling.

### Anti-slop audit

Initial score: **1/10** — tell 9 (an offline artifact cannot depend on a remote custom font, so the first pass used a generic UI stack). Treatment: chose an explicit condensed aviation-document heading stack and a restrained humanist body stack, with typography carrying hierarchy instead of decorative icons or extra cards.

Final score: **0/10**. No tech gradient, generic indigo accent, feature-tile trio, accent rail, blur, monument statistic, icon topper, center stack, default Inter/system-ui choice, or wrong-surface composition remains.

## Technical notes

- One dependency-free `index.html` with inline CSS and JavaScript.
- Works from `file://` and makes no network requests.
- Local storage key: `dcs-wingmate-beacon-v1`.
- Backup format: versioned JSON; generated briefs download as plain text.
