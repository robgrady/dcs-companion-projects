# Procedure Crosscheck

Procedure Crosscheck is a self-contained offline DCS World companion for reconciling two versions of the same cockpit procedure. Paste one step per line from each source; the app aligns likely equivalents, exposes omitted or differently worded steps, and lets the pilot deliberately build a canonical run card.

## Open it

Open `index.html` directly in any current browser. It has no network calls, external libraries, build step, or server requirement, and is designed to work from a `file://` URL.

## Use it

1. Name Source A and Source B and record a date or version for each.
2. Paste one procedural step per line. Existing bullets and line numbering are stripped automatically.
3. Select **Crosscheck procedures** (or press Command/Ctrl + Enter).
4. Review each aligned row:
   - **Close match** means the wording overlaps strongly.
   - **Review wording** means the app found a possible but uncertain pairing.
   - **Only in A/B** means there is no aligned counterpart.
5. Choose **Use A**, **Merge**, **Use B**, or **Skip** for each row.
6. Edit and reorder the canonical checklist, then copy, print, or export it.

The project persists locally in browser storage. JSON export/import is included for backup and handoff.

## Important assumptions and limits

- Text similarity is evidence about wording, not proof of procedural correctness.
- The app has no aircraft-specific authority and intentionally ships with no invented procedure data.
- Resolve disputed actions against the current official module manual, official change log, or a controlled in-simulator test.
- A newer source is not automatically a better source; record provenance and version context.
- The output is for DCS World simulation only, never real-world aviation.
- Best alignment comes from short, action-led lines with one action per step.

## Why this exists

Recent community questions show a recurring learning problem: pilots move among in-game training, manuals, community guides, YouTube tutorials, and personal checklists, then have to decide whether different wording reflects simplification, outdated material, or a real procedural disagreement. Procedure Crosscheck does not add another authoritative checklist; it gives the pilot a disciplined comparison surface for making and documenting that decision.

Community signals reviewed on **2026-11-23**:

- **r/dcsworld — “F16 Training”**: a new F-16 pilot reported moving between in-game training, YouTube, Chuck's guide, and the manual; replies recommended learning in layers and maintaining a personal checklist. This directly supports a source-reconciliation tool rather than another fixed tutorial.  
  https://www.reddit.com/r/dcsworld/comments/1xqtsnw/f16_training/
- **r/hoggit — Weekly Questions Thread, September 8**: discussion distinguishes official documentation and current procedures from incomplete or divergent community material, illustrating why source date and provenance matter.  
  https://www.reddit.com/r/hoggit/comments/1wa8obj/weekly_questions_thread_sep_08/
- **r/hoggit — Weekly Questions Thread, August 25**: community answers point learners toward manuals, training missions, videos, and self-authored reference notes, reinforcing that DCS learning commonly spans multiple sources.  
  https://www.reddit.com/r/hoggit/comments/1vxjwhi/weekly_questions_thread_aug_25/
- **Eagle Dynamics forum — C-130J CNI-MU complete manual request**: users note that available videos do not cover all functions and ask for complete written material, another example of procedural knowledge being fragmented across formats.  
  https://forum.dcs.world/topic/383310-cni-mu-complete-manual/

URLs were accessed on **2026-11-23**. Community statements are treated as demand signals, not technical authority.

## Design notes

**Surface:** Compare, with Configure as a secondary activity. The aligned three-column comparison is the composition; the canonical checklist follows only after source differences are visible.

**System:** near-black maintenance-desk surfaces, warm amber action color, restrained status colors, Georgia display type, Avenir/system sans body, and monospaced evidence labels. Motion is limited to the method drawer, toast, and optional result scroll; reduced-motion preferences are respected.

**Anti-slop audit after implementation: 0/10.** No tech gradient, generic indigo accent, feature-tile grid, accent rail, blur-as-decoration, monument statistic, icon toppers, center stack, default Inter typography, or surface mismatch was present. The only backdrop blur is functional on the sticky header over scrolling content, not a glass-card treatment.
