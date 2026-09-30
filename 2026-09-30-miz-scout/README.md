# MIZ Scout

MIZ Scout is a self-contained, offline preflight inspector for Digital Combat Simulator mission files. Drop a `.miz` archive into the page and it reads the ZIP package locally, surfaces declared terrain and `requiredModules` entries, detects Client/Player slots, inventories common script and media assets, and builds a checkable mission handoff brief. No mission data is uploaded and the app never modifies the archive.

## Use

1. Open `index.html` directly in a current browser. Chrome/Chromium is recommended for the broadest `DecompressionStream('deflate-raw')` support.
2. Drop a `.miz` file on the intake target or choose one with the file picker.
3. Review the findings, archive inventory, detected slots, file list, and raw mission evidence.
4. Check off the identified map and declared modules that are available on the intended machine/server. Acknowledgments persist in `localStorage` by dependency name.
5. Copy, download, or print the generated handoff brief.
6. If the browser cannot decompress the archive, extract the root `mission` file from the `.miz` ZIP and paste its Lua text into the fallback field.

## Important assumptions and limits

- Analysis is entirely client-side and read-only.
- `.miz` files are ZIP archives. This app supports stored entries and standard DEFLATE entries through the browser's native `DecompressionStream` API.
- The parser is deliberately heuristic: DCS mission Lua tables are data-like but are not executed. Slot/type associations are inferred from nearby table fields.
- `requiredModules` is treated as a declared dependency signal, not proof that every listed module is truly necessary or that no undeclared user mod is present.
- Object-type count is a rough mission-density cue, not a performance benchmark.
- A green readiness state means identified declarations were acknowledged; it does **not** certify compatibility, scripting correctness, mission integrity, or server performance. The final check is an actual load/run in the target DCS installation.
- MIZ Scout does not upload, edit, repair, or repack missions.

## Community signal

The project responds to a recurring mission-access and mission-authoring problem visible in current DCS community discussion: players report difficulty finding maintained user missions, mission makers ask how others create and distribute content, and community tools increasingly automate mission generation. Together these signals imply a practical handoff gap: before committing scarce flying time, a player or server host needs a quick way to understand what a downloaded/generated `.miz` appears to contain and what it declares.

Sources reviewed on **2026-09-30**:

- r/hoggit — “DCS mission and campaign - Lack of up-to-date user-generated content” (discussion of finding maintained missions and campaigns): https://www.reddit.com/r/hoggit/comments/1nqmced/dcs_mission_and_campaign_lack_of_up_to_date_user/
- r/hoggit — “DCS mission makers” (discussion of mission-building approaches and the work involved): https://www.reddit.com/r/hoggit/comments/1ninq5k/dcs_mission_makers/
- r/hoggit — “WTH happened to all the DCS user files?” (discussion of user-file discovery and site/search friction): https://www.reddit.com/r/hoggit/comments/1ibwe7d/wth_happened_to_all_the_dcs_user_files/
- r/dcsworld — “Updated AI DCS Mission Generator” (community demand for faster/generated mission creation): https://www.reddit.com/r/dcsworld/comments/1mg65hv/updated_ai_dcs_mission_generator/
- Eagle Dynamics — “DCS Dynamic Campaign – Development Progress” (official evidence that richer generated campaign missions and logistics remain an active product direction): https://www.digitalcombatsimulator.com/en/news/2025-09-19/

## Files

- `index.html` — complete app; all CSS and JavaScript are inline.
- `README.md` — usage, assumptions, limits, and source record.
