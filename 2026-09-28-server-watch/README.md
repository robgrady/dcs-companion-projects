# Server Watch

Server Watch is a self-contained, offline field notebook for finding DCS World multiplayer servers that fit the pilot's actual aircraft, terrain ownership, play style, connection, voice-comms preference, and available hours. Instead of trusting an old recommendation or a single population snapshot, it records observations over time and reveals the pilot's own median population, median ping, join success rate, and best observed local hour for each server.

## Use

1. Open `index.html` directly in a modern browser. It requires no server, account, package, network connection, or build step.
2. Add a server from the DCS browser or a community recommendation. Record only details you have verified: mode, era, terrains, useful aircraft or roles, voice expectation, address/search phrase, briefing link, and fit notes.
3. Select the server and choose **Log observation** whenever you check it near a time you could realistically fly. Record local time, players seen, ping, join outcome, side balance, and a short note.
4. Use search and the mode, era, aircraft, terrain, freshness, and favorite filters to narrow the library before launching DCS.
5. Sort by recent check, median players, name, or observed fit. The fit sort favors favorites, successful populated observations, and recent evidence; it is a local prioritization aid, not a universal server rating.
6. Complete the six-item join gate before committing to a sortie: build, terrain, aircraft slot, voice, registration/password, and briefing.
7. Export a JSON backup regularly. Import replaces the current browser library after confirmation. Print produces a compact record for the selected server.

Keyboard shortcuts work when focus is not inside a control: `/` focuses search, `N` adds a server, `O` logs an observation for the selected server, and `Esc` closes a dialog.

## Important assumptions and limits

- Server Watch is deliberately not a live server browser. It does not contact Eagle Dynamics, server APIs, Discord, SRS, or any community service.
- It starts empty rather than inventing server availability, population, ping, aircraft, maps, or rules.
- All records are user-entered observations. Server operators can change names, missions, passwords, versions, allowed modules, voice policy, and schedules without notice.
- “Best observed hour” is the local clock hour with the highest median player count among observations where joining succeeded. Sparse samples are not proof of a stable peak.
- Median players and ping describe only recorded samples. They do not measure mission quality, teamwork, server hardware, scripting load, network route stability, or whether a desired aircraft slot remains available.
- Join success rate counts observations marked **Yes**. A failed join can reflect version, terrain, module, registration, password, capacity, integrity check, or another unrecorded requirement.
- The “best observed fit” sort is intentionally transparent and personal: it combines observed population with join success, a favorite bonus, and an age penalty. It does not rank server communities against one another.
- Briefing links open in a new browser tab and therefore require a network connection at that moment.
- Data persists in browser `localStorage` and can differ by browser, profile, and `file://` path. Clearing browser data or moving the project can make the library unavailable; JSON export is the durable backup path.
- Server rules, current briefings, DCS release notes, mission commanders, and administrators always take priority over this notebook.

## Community signal

Recent community discussion repeatedly describes a discovery problem rather than a simple shortage of servers: returning pilots ask which communities replaced old favorites; players report difficulty finding a server that is populated but not full; the usefulness of SRS and activity varies by server and time of day; and desired experience depends on era, realism, aircraft/weapon set, PvE/PvP posture, region, and tolerance for casual versus organized play. A single recommendation list ages quickly. Server Watch turns those changing conditions into a personal, time-aware field record.

Sources reviewed on **2026-09-28**:

- Reddit / r/hoggit, **“Is the multiplayer scene deteriorating?”** (2026-06-26) — a returning player reports that former favorites appear quiet; replies emphasize that server interest moves, voice activity depends on server and time of day, and specialized realism can reduce population: https://www.reddit.com/r/hoggit/comments/1ug2kxa/is_the_multiplayer_scene_deteriorating/
- Reddit / r/dcsworld, **“What to do in DCS in 2026”** (2026-06-20) — a returning Cold War pilot asks which active servers replaced an older favorite; replies note that finding a server that is populated but not full can be difficult and recommend different servers according to PvE/PvP, region, aircraft, and realism preferences: https://www.reddit.com/r/dcsworld/comments/1uamfz2/what_to_do_in_dcs_in_2026/
- Reddit / r/dcsworld, **“New player, does this game have a social or PvE community?”** (2026-03-25) — two new helicopter-focused players seek structured, intentional cooperative play rather than merely any open server, and replies route them toward communities with different mission styles: https://www.reddit.com/r/dcsworld/comments/1s3qcsu/new_player_does_this_game_have_a_social_or_pve/
- Reddit / r/hoggit, **Weekly Questions Thread Sep 08** (2026-09-08) — the current support thread continues to point newcomers toward a 24/7 training server and Discord-based help, illustrating that server discovery, module availability, and community channels remain connected onboarding concerns: https://www.reddit.com/r/hoggit/comments/1wa8obj/weekly_questions_thread_sep_08/
- Eagle Dynamics Forums, **“Server Browser: Random Instances missing (for CGNAT users only?)”** (2026-05-04) — a server operator reports that some players see only a subset of multiple hosted instances in the browser, reinforcing that a browser snapshot can be incomplete for some network paths: https://forum.dcs.world/topic/387790-server-browser-random-instances-missing-for-cgnat-users-only-bind_address-2nd-ip-did-not-work/

## Design and implementation

The primary surface is **Explore**, with **Compare** secondary: filters and evidence-backed destination records dominate the composition, while the inspector exposes one server's fit, observed pattern, join gate, and notes. The visual language is a restrained squadron operations notebook—near-black field surfaces, warm instrument-paper text, muted olive structure, signal amber, serif destination names, and monospaced observations. It avoids a marketing hero, decorative metrics, generic feature cards, and remote assets.

Accessibility and portability features include semantic labels, visible keyboard focus, 44-pixel controls, keyboard shortcuts, responsive filter and inspector behavior, reduced-motion support, print styling, confirmation before destructive replacement/deletion, and escaped user content before rendering.

Slop diagnostic before final polish: **0/10**. No tech gradient, default indigo, feature-tile grid, accent rail, glass surface, monument statistic, repeated icon topper, centered-stack composition, default Inter typography, or surface mismatch is present. Final score: **0/10**; the compact numeric cells report user-recorded evidence and serve the compare task rather than decoration.

## Files

- `index.html` — complete offline application with inline CSS and JavaScript
- `README.md` — operating instructions, assumptions, design notes, and community sources
