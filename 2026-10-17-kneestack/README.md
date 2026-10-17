# KneeStack

KneeStack is a self-contained, offline DCS World sortie-reference editor. It helps a pilot turn a large library of checklists, screenshots, briefing notes, and quick-reference pages into a small, ordered kneeboard stack for the next mission.

Open `index.html` directly in a modern browser. No server, account, build step, or network connection is required.

## What it does

- Builds text cards for mission, comms, route, target, threat, procedure, recovery, and notes material.
- Imports PNG, JPEG, and WebP reference pages, then resizes them locally for practical browser storage.
- Reorders pages with buttons, keyboard controls, or drag-and-drop.
- Enables or disables pages without deleting source material.
- Enforces a user-selected page budget and checks for mission, comms, route, and recovery coverage.
- Provides a distraction-free review mode for rehearsing the page sequence.
- Prints enabled pages or saves them as a PDF for later kneeboard conversion.
- Saves the active stack in `localStorage` and supports complete JSON backup/import, including imported images.

## How to use it

1. Enter the mission name, aircraft/seat, and a realistic page budget.
2. Add short text cards or import existing image pages.
3. Select a page to inspect it; use the arrow buttons, keyboard arrows, or drag-and-drop to order the stack by expected time of use.
4. Disable pages that are not necessary for this sortie.
5. Resolve the readiness checks, then use **Review stack** to rehearse the sequence.
6. Use **Print / PDF** to print the enabled stack. Browser print settings control final scaling and margins.
7. Export a JSON backup before clearing a large or important stack.

## Keyboard controls

- `R`: open review mode when focus is not in a form field.
- `Left` / `Right` or `Page Up` / `Page Down`: move through review pages.
- `Escape`: exit review mode.
- `Up` / `Down`: reorder the selected page when focus is not in a form field.

## Assumptions and limits

- KneeStack is a planning and organization aid, not an official Eagle Dynamics or aircraft procedure source.
- The user is responsible for the accuracy and currency of imported procedures, frequencies, coordinates, and mission data.
- Imported images are converted to JPEG and limited to 1,400 pixels on their longest side. This is intentional to reduce `localStorage` pressure; detailed charts should be checked after import.
- Browser storage quotas vary. If a stack contains many image pages, export a backup and split it into smaller mission-specific stacks.
- PDF files are not imported directly because the app has no external runtime dependencies. Export needed PDF pages to PNG or JPEG first.
- The print layout targets a clean full-page reference. Final DCS kneeboard sizing or placement depends on the user's normal kneeboard workflow.

## Community signal

Accessed 2026-10-17.

- A recent r/dcsworld newcomer thread asked how to approach DCS without becoming overwhelmed; replies pointed new pilots toward short, focused starts rather than trying to absorb everything at once. KneeStack applies that same constraint to reference material by making the page budget explicit: https://www.reddit.com/r/dcsworld/comments/1od6roa/im_new_to_dcs_how_should_i_approach_it_without/
- A recent r/hoggit discussion asked how people organize large kneeboard collections and noted that some aircraft can accumulate twenty or more pages. KneeStack is purpose-built to cut a library down to one sortie-specific sequence: https://www.reddit.com/r/hoggit/comments/1qi7uiw/how_do_you_guys_handle_kneeboard_management/
- A recent r/hoggit discussion praised concise community quick-reference guides as especially useful for learning and reference. KneeStack provides a local workbench for combining such concise material with the user's mission-specific notes: https://www.reddit.com/r/hoggit/comments/1qvh96q/dcs_players_when_they_realise_chucks_guides_are/
- Eagle Dynamics' January 2026 newsletter described a new in-game digital kneeboard system, reinforcing that kneeboard workflow remains an active product and community concern: https://www.digitalcombatsimulator.com/en/news/newsletters/f135cc39f027794fe5088631f6f85202/

## Privacy

All processing is local. The app makes no network requests and contains no analytics or external dependencies.
