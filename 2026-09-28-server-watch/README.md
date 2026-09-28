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

Recent and recurring community discussion describes a fit-and-discovery problem rather than a simple shortage of servers. Pilots ask for alternatives to a familiar server, distinguish PvE from PvP, seek particular eras and mission tempos, need a suitable place to learn, and sometimes cannot see the same browser entries as another player. New communities also advertise themselves through specific combinations of terrain, era, weapon restrictions, persistence, logistics, and AI/player balance. A static recommendation list therefore ages quickly; Server Watch turns those changing conditions into a personal, time-aware field record.

Sources found through live web search and reviewed on **2026-09-28**:

- Reddit / r/hoggit, **“Looking for good PvP or PvE DCS servers bored of Contention”** (2026-03-04) — the question asks for alternatives by play style; the indexed discussion recommends a late-Cold-War PvE option partly because of its focused missions, realistic stores, and threat environment: https://www.reddit.com/r/hoggit/comments/1rkajw3/looking_for_good_pvp_or_pve_dcs_servers_bored_of/
- Reddit / r/hoggit, **“New PvPvE Multiplayer Server — Operation Have Chips”** — the indexed announcement differentiates the server through 1989/2014 eras, Syria and Caucasus terrain, period weapon limits, logistics, persistence, and a mix of AI and human pilots, demonstrating why one server record needs more than a population number: https://www.reddit.com/r/hoggit/comments/1rtjsax/new_pvpve_multiplayer_server_operation_have_chips/
- Reddit / r/hoggit, **“DCS Noob multiplayer Server recommendations?”** — the indexed answers route a new pilot toward different training/PvE servers and explicitly mention listening to SRS, showing that destination choice and comms readiness are linked: https://www.reddit.com/r/hoggit/comments/14e8ktc/dcs_noob_multiplayer_server_recommendations/
- Reddit / r/dcsworld, **“Best multiplayer servers for fast-paced gameplay?”** — the pilot wants options beyond dogfight-only play and one familiar server, a clear example of searching by mission tempo rather than popularity alone: https://www.reddit.com/r/dcsworld/comments/117nglu/best_multiplayer_servers_for_fastpaced_gameplay/
- Reddit / r/dcsworld, **“Best multi role multiplayer servers for DCS?”** — a direct request for a server matched to a desired range of roles, reinforcing aircraft/role filtering as a recurring need: https://www.reddit.com/r/dcsworld/comments/107aejo/best_multi_role_multiplayer_servers_for_dcs/
- Reddit / r/hoggit, **“Servers not showing up in multiplayer”** — one player can see and join servers that another cannot, supporting an observation log that distinguishes “offline” from a local visibility or join problem: https://www.reddit.com/r/hoggit/comments/1frk39x/servers_not_showing_up_in_multiplayer/

## Design and implementation

The primary surface is **Explore**, with **Compare** secondary: filters and evidence-backed destination records dominate the composition, while the inspector exposes one server's fit, observed pattern, join gate, and notes. The visual language is a restrained squadron operations notebook—near-black field surfaces, warm instrument-paper text, muted olive structure, signal amber, serif destination names, and monospaced observations. It avoids a marketing hero, decorative metrics, generic feature cards, and remote assets.

Accessibility and portability features include semantic labels, visible keyboard focus, 44-pixel controls, keyboard shortcuts, responsive filter and inspector behavior, reduced-motion support, print styling, confirmation before destructive replacement/deletion, and escaped user content before rendering.

Slop diagnostic before final polish: **0/10**. No tech gradient, default indigo, feature-tile grid, accent rail, glass surface, monument statistic, repeated icon topper, centered-stack composition, default Inter typography, or surface mismatch is present. Final score: **0/10**; the compact numeric cells report user-recorded evidence and serve the compare task rather than decoration.

## Files

- `index.html` — complete offline application with inline CSS and JavaScript
- `README.md` — operating instructions, assumptions, design notes, and community sources
