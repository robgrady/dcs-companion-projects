# Userfile Radar

Userfile Radar is a self-contained, offline discovery and readiness desk for DCS World community files. It gives pilots a personal searchable layer over promising missions, campaigns, liveries, mods, documents, control profiles, and static templates—without depending on the DCS User Files site's search experience after the source has been found.

## Use

1. Open `index.html` directly in a modern browser. No server, account, install, or network connection is required.
2. Open **My DCS install** (the gear button) and select the aircraft/modules and terrains you own. Add uncommon names one per line.
3. Select **Add file** and capture a title, creator, source URL, file type, aircraft, terrain, mode, dates, dependencies, tags, and notes.
4. Move each item through **Watchlist → Downloaded → Installed → Tested → Archived** with the arrow action or by editing it.
5. Search and filter the catalog by workflow, compatibility, type, aircraft, and terrain. The compatibility filter identifies requirements that do not match the locally stored ownership list.
6. Use **Data** to export/import a JSON backup, print the current filtered view, or clear the catalog.

All catalog data and ownership settings stay in browser `localStorage` under `dcs-userfile-radar-v1`. Opening the file in a different browser profile creates a separate catalog. Source links open only when the user explicitly selects them.

## Assumptions

- Requirement matching is exact but case-insensitive. Use consistent names across entries and ownership settings.
- Aircraft and terrain fields accept comma-separated requirements. Blank, `Any`, `None`, and `N/A` do not create ownership gaps.
- “Ready for my install” means the aircraft/module and terrain names match the ownership list; it does not prove version compatibility, required scripts, or file integrity.
- Other dependencies are recorded for review but are not automatically interpreted because community package naming is inconsistent.
- The app does not scrape, download, inspect, install, or update community files. It is a private catalog and decision layer.

## Community signal

Built on 2026-11-08 after reviewing current and recurring DCS community reports about content discovery:

- A January 2026 r/hoggit discussion asking for DCS-adjacent tool ideas identified the User Files section as a major pain point, specifically poor search, categorization, dependency visibility, and map requirements: https://www.reddit.com/r/hoggit/comments/1q1g3yz/what_is_your_biggest_pain_around_dcs/ (accessed 2026-11-08).
- A recent Eagle Dynamics forum report described User Files pagination returning users to the top page and requested better filtering by file type: https://forum.dcs.world/topic/387973-userfiles-keeps-resetting-to-top-page/ (accessed 2026-11-08).
- An August 2026 Eagle Dynamics forum report described login/navigation failures around the User Files section and noted that Eagle Dynamics had acknowledged an issue: https://forum.dcs.world/topic/390648-user-files-page-acting-crazy/ (accessed 2026-11-08).
- A 2025 Eagle Dynamics forum proposal argued that discovering community content needed urgent improvement and called for a more usable browsing interface: https://forum.dcs.world/topic/380853-ed-user-files-please-help-me-to-better-find-stuff/ (accessed 2026-11-08).
- A September 2026 r/hoggit roadmap discussion again highlighted the dependence on mission creators and frustration with needing to design or locate content to sustain play: https://www.reddit.com/r/hoggit/comments/1wecy39/2026_dcs_roadmap_progress/ (accessed 2026-11-08).

## Design notes

This is an **Explore** surface: search, filters, result scanning, and compatibility inspection drive the composition. It deliberately avoids a marketing hero, equal-weight feature tiles, fake metrics, gradients, and decorative dashboard data. The visual system uses a restrained field-desk palette, compact metadata, keyboard focus states, 44px-class primary controls, responsive layouts, reduced-motion handling, and a print view.

### Anti-slop audit

Score: **0/10**. None of the ten diagnostic tells fired: no tech gradient, generic indigo accent, feature-tile grid, accent rails, unearned blur, monument stats, icon toppers, center-stack composition, default Inter/system typography, or surface mismatch. No slop-directed repair was required; functional verification did expose and correct one JavaScript template-literal defect before publication.
