# Envelope Desk

Envelope Desk is a self-contained, offline DCS World stores-employment rehearsal ledger. It lets a pilot record **their own verified** range and altitude envelopes, setup cues, confidence level, source, and verification date; compare up to three profiles; match a planned pass against the library; and rehearse profiles as recall cards.

## Use

1. Open `index.html` directly in any modern browser. No server, account, network, or build step is required.
2. Choose **Add profile** and record one store/module combination using values you have verified for the current DCS version and mission conditions.
3. In **Library**, search/filter profiles and select up to three for an aligned comparison.
4. In **Match**, enter a planned range and altitude to screen profiles. “Inside” only means the entered values fall within your recorded bounds.
5. In **Rehearse**, recall the envelope and cues before revealing the answer, then mark it Again or Known.
6. Use **Backup / restore** to export or import JSON. Browser state and rehearsal score persist in `localStorage`; printing produces a clean card sheet.

## Important assumptions

- This is a personal knowledge and rehearsal tool, **not a ballistic calculator**, authoritative weapons manual, or substitute for module documentation and in-sim testing.
- The app intentionally ships without pre-populated weapon data: DCS parameters vary with patches, aircraft state, release conditions, target geometry, and technique. The user owns every value entered.
- Match results test only range and altitude bounds; they do not model speed, aspect, target motion, wind, seeker limits, fuzing, countermeasures, or probability of kill.
- Source/reference is free text so a profile can point to a manual revision, track file, test card, or URL. Re-verify profiles after relevant DCS updates.
- All data remains local unless the user explicitly exports a JSON file.

## Community signal (accessed 2026-08-18)

Live search showed strong, current interest in compact DCS weapons references, alongside immediate community correction of unqualified range figures—evidence that provenance and user-verifiable conditions matter as much as quick lookup. The app responds by making every envelope user-owned and attaching confidence, source, and date rather than presenting generic figures as truth.

- r/hoggit — **“Built this DCS Weapons Guide that works well on mobile and tablet (web app)”**. Discussion praised the format but immediately debated missile-range values and their launch conditions: https://www.reddit.com/r/hoggit/comments/1rwtnhe/built_this_dcs_weapons_guide_that_works_well_on/
- r/hoggit — **“What supplemental software do you use? DCS Noob Post”**. Replies highlight kneeboard and data-entry utilities as core companions, reinforcing demand for cockpit-adjacent offline tools: https://www.reddit.com/r/hoggit/comments/19da1b7/what_supplemental_software_do_you_use_dcs_noob/
- ED Forums — recurring, airframe-specific dive-bombing technique discussions show that useful employment parameters are conditional rather than universal: https://forum.dcs.world/topic/259640-dive-bombing-best-practices/ and https://forum.dcs.world/topic/375545-help-with-bombing-in-the-f4u-corsair-tips-reticle-usage/

## Files

- `index.html` — complete application with inline CSS and JavaScript
- `README.md` — usage, assumptions, and research record
