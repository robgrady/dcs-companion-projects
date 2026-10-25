# Host Check

Host Check is a self-contained, offline DCS World private co-op launch and recovery desk. It gives the host one place to verify the mission, human slots, version and module parity, network join path, pause behavior, coalition access, voice, and cockpit controls before unpausing. A crew board exposes each person's actual readiness, while symptom-specific fault ladders keep troubleshooting ordered instead of random.

## Why this project

Recent DCS community discussions continue to show that small private multiplayer sessions fail at a predictable set of seams: a friend cannot see or join the host, a connected player remains in spectators, human aircraft were not configured as Client slots, port/firewall setup is unclear, controls fail after occupying a cockpit, or marginal connections destabilize the session. These are often setup and isolation problems rather than flying problems.

Host Check turns that recurring friction into a short launch contract and a shared evidence trail. It does not configure DCS, edit a mission, open network ports, or claim to detect game state; every gate is an explicit human verification.

## Use

1. Open `index.html` directly in a modern browser. No server, installation, network access, build step, or external library is required.
2. Enter the session name, mission, terrain, DCS version, hosting mode, join path, and voice plan.
3. Click each **Host Gate** button to cycle it through open, checked, and blocked. Every critical gate must be checked and no gate may remain blocked for a green launch state.
4. Add one crew row per pilot or multicrew seat. Mark **J**oined, **S**lotted, **C**ontrols checked, and **V**oice checked for each person.
5. Keep the mission paused until the top launch bar turns green. Use **Log unpause** to time-stamp the decision.
6. If a failure appears, select the matching symptom in **Fault Ladder** and work the checks in order. Stop changing things when the fault is isolated.
7. Add manual observations to the session wire, export the complete session as JSON, import it later, or print a compact host brief.

All working state is saved locally in the browser with `localStorage`.

## Important assumptions

- This is a simulation companion and checklist, not a network scanner, DCS plug-in, server controller, or real-world aviation tool.
- A checked gate means a human verified it for the current session; Host Check cannot inspect DCS, the Mission Editor, a firewall, router, installed module, or voice client.
- DCS multiplayer requirements and behavior can change with updates, mission scripting, server rules, modules, terrain, and third-party tools.
- The app deliberately avoids prescribing one networking method. Direct hosting, dedicated hosting, and meeting on a public server have different constraints.
- Do not save or export a real server or coalition password. Record only a hint or the channel where the password is shared.
- “Client” slot guidance applies to seats intended for joining humans in multiplayer; mission-specific scripts and slot systems can impose additional restrictions.
- The fault ladders move from low-cost confirmation toward higher-disruption changes. They are diagnostic prompts, not guarantees.

## Community signals

Accessed October 25, 2026:

- Reddit / r/dcsworld — “Need help setting up multiplayer,” a recent private-hosting question centered on getting a friend into a mission: https://www.reddit.com/r/dcsworld/comments/1nvtylu/need_help_setting_up_multiplayer/
- Reddit / r/hoggit — “DCS multiplayer with friend FAQ,” discussing the recurring setup confusion around hosting and joining a two-person session: https://www.reddit.com/r/hoggit/comments/1n7ox9m/dcs_multiplayer_with_friend_faq/
- Reddit / r/hoggit — “Hotel WiFi is too bad for multiplayer; where to go?” highlighting connection quality as a practical barrier to flying with others: https://www.reddit.com/r/hoggit/comments/1ofneqv/hotel_wifi_is_too_bad_for_multiplayer_where_to/
- Reddit / r/hoggit — “DCS Questions Megathread 2026,” whose current question stream includes requests for help hosting missions with friends and other multiplayer setup questions: https://www.reddit.com/r/hoggit/comments/1qpo39e/dcs_questions_megathread_2026/
- Eagle Dynamics forum — “How to setup dedicated server for multiplayer,” including community guidance on Client slots, port forwarding, and firewall rules: https://forum.dcs.world/topic/314153-how-to-setup-dedicated-server-for-multiplayer/
- Eagle Dynamics — DCS changelog, checked for current multiplayer and module-update context: https://www.digitalcombatsimulator.com/en/news/changelog/

## Files

- `index.html` — complete app with inline CSS and JavaScript
- `README.md` — usage, assumptions, and source context
