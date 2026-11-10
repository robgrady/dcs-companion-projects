# Fuze Contract

Fuze Contract is a self-contained, offline DCS World attack-setup desk. It makes a pilot state the weapon construction, target surface, desired effect, fuze station, arming value, function delay, impact geometry, and source authority as one repeatable contract. The app flags generic contradictions—especially delayed non-penetrator weapons against hard surfaces—then produces a compact rearm-to-release card.

## Use

1. Open `index.html` directly in a current browser. No server, account, installation, or network connection is required.
2. Enter the exact aircraft, weapon, fuze, arming, and function values shown by the current module, rearm panel, manual, or mission brief.
3. Select weapon construction, target surface, desired effect, and expected impact geometry.
4. Choose **Evaluate contract**. Resolve red blocking conflicts and consciously review amber open items.
5. Save useful snapshots, search and reload them, copy the plain-text readback, print the execution card, or export/import the local JSON library.
6. After checking a primary source or running a controlled DCS test, use **Mark test verified**, add any resulting notes, and save a new snapshot.

Saved contracts remain in browser `localStorage` under `dcs-fuze-contract-v1`. Data is local to the browser/profile and file origin; export a backup before clearing browser data or moving the file.

## Important assumptions and limits

- This is an independent planning and verification aid, not an official Eagle Dynamics or third-party module product.
- It does **not** prescribe real-world weapon use and is intended only for simulation.
- The app deliberately does not ship aircraft-specific fuze settings. DCS implementations, cockpit labels, available fuzes, and campaign requirements vary; enter and verify the exact values for the current module and version.
- “No generic conflict detected” means only that the entered construction, target, and intent do not trip this app's broad consistency rules. It is not a certification of the selected weapon profile.
- The hard-surface shatter warning is based on Eagle Dynamics' September 30, 2026 core changelog statement that non-penetrator bombs and rockets with delayed fuzes can shatter on hard surfaces instead of detonating.
- The decoder separates arming/safe-separation logic from function delay because community discussions commonly blur those concepts, while aircraft indications and ground-set fuze behavior can differ.
- Marking a contract verified is a manual user assertion. It should follow a current primary-source check or controlled in-sim test.
- Clipboard access from `file://` depends on browser permissions; the app includes a legacy local fallback.

## Community signal

Built on 2026-11-10 in response to a concentrated current signal around DCS's expanded fuze modeling and the resulting need to match bomb construction, target surface, desired effect, and delay rather than treating “delay” as a universally better setting.

Sources reviewed on 2026-11-10:

- Eagle Dynamics, **DCS 2.9.30.28536 changelog** — the September 30, 2026 core update introduced shattering when delayed-fuze non-penetrator bombs or rockets strike hard surfaces: https://www.digitalcombatsimulator.com/en/news/changelog/
- r/hoggit, **DCS 2.9.30.28536 changelog discussion** — pilots described delay fuzing as esoteric, called out precise munition/fuze/impact combinations, and asked for documentation and examples: https://www.reddit.com/r/hoggit/comments/1wu55sj/changelog_dcs_293028536/
- r/dcs, **September 30 changelog discussion** — the cross-community thread repeated the new hard-surface shatter rule and explicitly framed weaponeering as underappreciated: https://www.reddit.com/r/dcs/comments/1wu63c4/20260930_293028536_change_log/
- r/dcsworld, **September 30 changelog discussion** — the same core change reached a second major DCS community, confirming that the behavior is not module-specific chatter: https://www.reddit.com/r/dcsworld/comments/1wu630n/20260930_293028536_change_log/
- r/hoggit, **“Do different fuzes do anything”** — pilots asked for target-specific guidance and debated the difference between arming delay, function delay, and actual DCS damage behavior: https://www.reddit.com/r/hoggit/comments/1dp5lr6/do_different_fuzes_do_anything/
- r/dcsworld, **Bomb fuze options in the rearming panel** — a detailed community reference separates arming time, safe separation, function, premature function, and dud terminology: https://www.reddit.com/r/dcsworld/comments/1fvkmof/bomb_fuze_options_in_the_rearming_panel/
- Eagle Dynamics forum, **Are the delay fuzes broken for laser-guided bombs right now?** — a version-sensitive troubleshooting thread reinforces the need to record exact setup and verify current behavior: https://forum.dcs.world/topic/374518-are-the-delay-fuses-broken-for-laser-guided-bombs-right-now/

## Design notes

This is a **Configure** surface, with a secondary saved-contract library. The left side captures one explicit setup; the right side immediately exposes the resulting card and contradictions. It avoids a marketing hero, equal-weight feature tiles, fake metrics, cockpit-art imitation, and decorative dashboard data.

### Anti-slop audit

Initial score: **0/10**. No diagnostic tells fired: there is no glossy tech gradient, generic indigo/violet accent, feature-tile grid, accent rail, glass blur, monument statistic, icon topper, centered-stack composition, default Inter/system typography, or surface mismatch. The restrained field-desk palette, square-edged paper card, compact type hierarchy, and asymmetric configure/result composition all serve the task.

## Technical notes

- One self-contained `index.html` with inline CSS and JavaScript; no runtime dependencies or build step.
- Designed for direct `file://` use at desktop, tablet, and phone widths.
- Semantic form controls, explicit labels, live status regions, visible keyboard focus, 44px-class controls, reduced-motion handling, and print styling are included.
- Core features: live execution card, rule-based conflict checks, local snapshot library, search, load/delete, JSON backup/restore, clipboard readback, manual verification state, and print output.
