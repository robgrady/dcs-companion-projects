# Mayday Matrix

Mayday Matrix is a self-contained, offline emergency-procedure card builder for Digital Combat Simulator. It is intentionally module-neutral: the built-in cards organize decision-making after failures or battle damage without pretending to replace the current aircraft manual, squadron SOP, mission briefing, or instructor guidance.

## Open it

Open `index.html` directly in any modern browser. No server, internet connection, install, or build step is required; the app is designed to run from a Dropbox `file://` URL.

## Use it

1. Pick a procedure in **Your cards**.
2. Check off steps in the normal view, or choose **Focus mode** for one large step at a time.
3. Add mission-specific notes such as divert fields, frequencies, fuel gates, or aircraft-specific cautions.
4. Use the elapsed timer when practicing a failure response.
5. Choose **New** or **Edit** to make a verified module-specific procedure. Step labels can distinguish memory items, checks, decisions, and comms.
6. Use **Export backup** before moving between browsers or machines; **Import backup** restores that JSON file.
7. Print the active card for a clean kneeboard-style hard copy.

Cards, completion state, and notes persist in browser `localStorage`. Focus mode supports Left Arrow, Space, and Escape. Export/import is the portable backup path because `localStorage` is browser- and file-origin-specific.

## Important assumptions

- Built-in steps are high-level simulator decision prompts, not certified real-world procedures.
- Aircraft-specific switch actions must be checked against the current DCS module manual and applicable squadron SOP.
- The app does not read DCS telemetry, mission files, or Saved Games data.
- Browser print settings determine final kneeboard dimensions; use portrait orientation and disable browser headers/footers when desired.

## Community signal

Accessed 2026-08-02 (America local date):

- **“Emergency Procedures” — r/hoggit, 2026-07-07.** A pilot described enjoying battle-damage recoveries but being unable to find a comprehensive emergency checklist, then began collecting procedures manually. This is the primary signal behind an editable emergency-card library and one-step focus mode. https://www.reddit.com/r/hoggit/comments/1uq2ho4/emergency_procedures/
- **“DCS visual aids to help senior pilots? Particularly limited vision due to age.” — r/hoggit, 2026-03-03.** The request for better visual support informed the large, high-contrast focus view, keyboard operation, and restrained information density. https://www.reddit.com/r/hoggit/comments/1rjsalk/dcs_visual_aids_to_help_senior_pilots/
- **“DTC to Kneeboard” — r/hoggit, 2026-03-18.** The wish for mission data such as comms and waypoints to become immediately usable kneeboard material reinforced editable mission notes, print styling, and offline portability. https://www.reddit.com/r/hoggit/comments/1rwuox4/dtc_to_kneeboard/
- **Recent r/hoggit kneeboard search feed.** The feed showed repeated 2026 activity around checklist creation, DTC conversion, OpenKneeboard integration, mission cards, and accessibility. https://www.reddit.com/r/hoggit/search.rss?q=kneeboard&restrict_sr=on&sort=new&t=year
- **r/dcsworld checklist search reviewed.** Reddit blocked the programmatic response during this run, so it was treated as a reviewed but unavailable corroboration path rather than evidence for a factual claim. https://www.reddit.com/r/dcsworld/search/?q=checklist&restrict_sr=1&sort=new&t=year

## Design posture

This is an **Operate** surface: procedures, completion state, and fast action dominate. The interface uses a cockpit-document vocabulary—warm amber, near-black/olive surfaces, condensed headings, hard dividers—and avoids dashboard metrics, decorative card grids, glass effects, and marketing framing.
