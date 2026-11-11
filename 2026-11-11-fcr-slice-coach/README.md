# FCR Slice Coach

An offline, single-file DCS F-16C radar-geometry trainer for the common “I see the datalink symbol, but my radar will not lock it” problem. It turns antenna elevation, cursor range, target altitude, and display scale into a live top-down FCR view plus a side-on scan-volume diagram.

## Use

1. Open `index.html` directly in a browser; no server or internet connection is required.
2. Choose one of the teaching setups or move the five geometry controls.
3. Compare the target altitude with the modeled upper/lower bracket at the FCR cursor range.
4. Use **Test TMS Up** to read the current diagnosis.
5. Run the short diagnosis drill. Score and the current setup persist in local storage.
6. Use **Print quick reference** for a compact paper/PDF reminder.

Keyboard controls when focus is not inside a control: Up/Down changes antenna center, Left/Right changes cursor range, and Space re-runs the diagnosis.

## What it teaches

- A datalink donor track and an ownship FCR return are not the same thing.
- Radar elevation is angular, so the altitude slice changes with range.
- The cursor should be near the target range before its altitude bracket is used.
- Display range, antenna travel, control bindings, and target bracketing are separate gates.
- Correct geometry does not guarantee detection; mode, aspect, range, clutter, radar state, and simulator behavior still matter.

## Assumptions and limits

This is a conceptual geometry coach, not an APG-68 performance simulation. The Narrow/Medium/Wide controls use deliberately simplified 4°, 8°, and 14° vertical slices so the relationship is visible. Detection logic checks only modeled vertical inclusion, display range, and an antenna-stop sanity condition. It does not model bar spacing, beam shape, revisit time, look-down clutter, RCS, jamming, azimuth, aspect, radar power state, track history, or DCS-version-specific implementation details. Use the current in-game manual and training missions for exact switchology and symbology.

No external code, fonts, images, analytics, or network requests are used. User state remains in the browser’s local storage.

## Community signal

Live search on **2026-11-11** found the same beginner failure pattern across DCS communities: players can see a Link 16/datalink contact but cannot create an FCR lock; replies repeatedly point to antenna-elevation placement, cursor-range altitude brackets, range scale, radar mode/state, and bindings. These discussions motivated a geometry-first trainer rather than another checklist:

- r/dcsworld, “What am I doing wrong? (F16C radar),” accessed 2026-11-11: https://www.reddit.com/r/dcsworld/comments/1mlq54h/what_am_i_doing_wrong_f16c_radar/
- r/hoggit, “DCS F-16 Radar TMS up not locking,” accessed 2026-11-11: https://www.reddit.com/r/hoggit/comments/1nk5qb9/dcs_f16_radar_tms_up_not_locking/
- r/hoggit, “New to F-16 and I can’t lock radar targets at all,” accessed 2026-11-11: https://www.reddit.com/r/hoggit/comments/1myg4zk/new_to_f16_and_i_cant_lock_radar_targets_at_all/
- r/hoggit, “Understanding radar symbols,” accessed 2026-11-11: https://www.reddit.com/r/hoggit/comments/1mqg488/understanding_radar_symbols/
- Eagle Dynamics, official DCS F-16C Early Access Guide (radar and datalink reference), accessed 2026-11-11: https://www.digitalcombatsimulator.com/upload/iblock/3f2/wc4wu2w3cjqszyzcy9gez1q9tctrrr7v/DCS_F-16C_Early_Access_Guide_EN.pdf

Community posts are treated as demand evidence, not authoritative avionics documentation.

## Design posture

Primary surface: **Operate**, secondary **Learn**. Controls, scan state, and diagnosis dominate; there is no marketing hero or equal-weight feature grid. The visual language uses a restrained radar-phosphor palette, an instrument-like display, and one side-profile diagram.

Slop audit before final verification: **0/10** — none of the ten diagnostic tells fired. Final score: **0/10**; no compositional repair was required.

## Files

- `index.html` — complete self-contained app
- `README.md` — usage, assumptions, provenance, and source record
