# Static Check

Static Check is a self-contained, offline visual-QA desk for DCS World mission and campaign creators. It turns every important scenery object, landmark, and static objective into an inspection card, then tracks the visual, pathing, client-view, and trigger checks that make a dressed scene dependable.

## Use it

1. Open `index.html` directly in any modern browser. No server, installation, or network connection is required.
2. Select **Add object** and enter the exact object name used in the DCS Mission Editor.
3. Record its zone, role, required season/state, and placement reference.
4. Inspect the object in DCS and complete the seven visual and mission gates.
5. Enter any unresolved issue in **Blocking issue**; clearing the field returns the card to review or ready status.
6. Use search and filters to focus the queue, or **Review next** to advance to the next incomplete card.
7. Use **Copy report** for a concise handoff, **Print queue** for a paper review sheet, and JSON export/import for backup or transfer.

The project saves automatically in browser `localStorage`. Import intentionally replaces the current browser project only after validating the backup and asking for confirmation.

## Readiness model

- **Review** — one or more of the seven QA gates is incomplete.
- **Blocked** — a blocking issue is recorded, regardless of check count.
- **Ready** — all seven QA gates are complete and the blocker is empty.

The checklist is deliberately a verification record, not an automated `.miz` editor. Static Check does not infer object durability, collision geometry, trigger behavior, or appearance; those must be tested in the actual DCS mission and recorded by the author.

## Assumptions

- Object names are copied exactly from the Mission Editor so trigger and report references remain unambiguous.
- “Client perspective” means the relevant player or multiplayer client slot, not only the Mission Editor preview.
- Required state describes what the mission author must inspect; it does not claim every DCS object offers every damage state.
- Seasonal checks apply only where the selected map, mission date, and object support visible seasonal treatment.
- Browser storage is device- and browser-specific; JSON export is the portable backup.

## Community signal

Accessed **2026-09-20**:

- [Eagle Dynamics newsletter — Updated Static Building Models (11 September 2026)](https://www.digitalcombatsimulator.com/en/news/2026-09-11/) announced an ongoing refresh of classic DCS static objects while preserving dimensions and placement. It specifically calls out seasonal textures plus proper damaged and destroyed models, creating a timely visual-regression and objective-state QA need for mission builders.
- [DCS 2026 Core Feature Wishlist — ED Forums](https://forum.dcs.world/topic/384194-dcs-2026-core-feature-wishlist/) asks for a movable 3D Mission Editor camera so creators can place assets correctly the first time; replies also request undo and repeat the 3D-editor need. Static Check supplies a disciplined external review queue while those editor ergonomics remain a community request.
- [The Universal Mission v0.3.250914 — r/hoggit](https://www.reddit.com/r/hoggit/comments/1ngsmxd/the_universal_mission_v03250914/) includes player discussion of static objects as strike targets and the weapon/damage uncertainty around destroying them. This reinforced explicit required-state and trigger-handoff checks rather than treating scene dressing as purely decorative.
- [DCS Mission Creation — r/hoggit](https://www.reddit.com/r/hoggit/comments/gijlgq/dcs_super_carrier_mission_creation/) documents the long-running friction of static placement, blocked spawns/AI paths, and recreating detailed scenes. That recurring pain shaped the pathing gate and reusable QA handoff.

## Privacy and portability

Static Check has no analytics, external runtime dependencies, or network requests. All CSS and JavaScript are embedded in `index.html`; project data remains in the local browser unless explicitly exported or copied.
