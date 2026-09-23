# Tower Chair

Tower Chair is a self-contained, offline pattern-communications trainer for DCS World pilots. It turns one complete towered-airfield circuit into a focused radio exercise: ground request, taxi readback, hold-short call, departure, traffic-pattern reporting, sequencing, landing clearance, and runway-clear call.

## Why this project

Recent DCS community discussions continue to show a sharp beginner-learning problem rather than a lack of aircraft content. New pilots describe training missions that assume aviation vocabulary, use unexplained acronyms, or give instructions that are hard to hear; other newcomers explicitly say they do not know military-aviation terminology or procedures. The community also continues to ask for richer ATC/GCI interaction. Tower Chair addresses the narrow, practiceable part of that demand: listening for clearance elements and building concise readbacks without needing to launch DCS or join a live server.

Sources reviewed on **2026-09-23**:

- Reddit / r/dcsworld, “Struggling to comprehend this simulator” (2026-09-08): https://www.reddit.com/r/dcsworld/comments/1wal32y/struggling_to_comprehend_this_simulator/
- Reddit / r/dcsworld, “I understand why lots of people give up on DCS early now” (2026-09-09): https://www.reddit.com/r/dcsworld/comments/1wbgcdf/i_understand_why_lots_of_people_give_up_on_dcs/
- Reddit / r/dcsworld, “Beginner looking to get into DCS…” (2026-09-13): https://www.reddit.com/r/dcsworld/comments/1wewj5h/beginner_looking_to_get_into_dcs_hoping_to_find/
- Eagle Dynamics forums, “2026 and Beyond Speculation (and Wishlist) Thread” (ATC/GCI module request): https://forum.dcs.world/topic/381933-2026-and-beyond-speculation-and-wishlist-thread/
- Reddit / r/hoggit, Weekly Questions Thread Sep 22 (continuing volume of newcomer questions and training demand): https://www.reddit.com/r/hoggit/comments/1wmtthq/weekly_questions_thread_sep_22/

## Use

1. Open `index.html` directly in a modern browser. No server, installation, build, or network connection is required.
2. Set the callsign, airfield, runway, pattern direction, frequency, ATIS letter, and wind shown in your mission briefing.
3. Read or listen to each controller transmission.
4. Type the radio call or readback you would make, then select **Transmit** (or press Command/Ctrl + Enter).
5. Review which clearance elements were heard or missed, then continue around the circuit.
6. Use **Check ride** mode to hide element hints. Export the local transcript or print a practice card when finished.

Settings and aggregate practice results persist in browser `localStorage`. The current circuit transcript stays on the page and can be exported as a text file.

## Assumptions and boundaries

- This is a phrase-structure and listening trainer, not an authoritative ATC manual.
- DCS missions, multiplayer servers, human controllers, nations, and eras can use different procedures and brevity. The mission briefing and controller instructions always take priority.
- The app intentionally accepts several equivalent word choices and scores required concepts rather than exact punctuation or rigid scripts.
- Browser speech synthesis is optional and voice quality varies by operating system. All calls remain visible as text.
- No aircraft performance, radio-frequency database, or map data is embedded; the pilot supplies scenario values from the mission.

## Design note

The primary surface is **Operate**, with **Learn** secondary: the current controller call, readback field, and clearance state dominate; setup and glossary stay peripheral. Slop diagnostic after implementation: **0/10** — no tech gradient, generic indigo, feature-tile grid, accent rail, blur, monument stat, icon toppers, center-stack composition, default Inter, or wrong-surface hero.
