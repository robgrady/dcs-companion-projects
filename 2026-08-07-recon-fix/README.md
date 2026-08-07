# Recon Fix

**Recon Fix** is a self-contained, offline coordinate desk for DCS World reconnaissance screenshots. It lets an analyst load a local image, calibrate it against three known map references, plot observed targets, and produce a compact mission record without uploading imagery or installing a build tool.

## Use

1. Open `index.html` directly in a modern browser (`file://` is supported).
2. Load a PNG, JPEG, or WebP reconnaissance frame.
3. For each reference A, B, and C, enter a known latitude and longitude in decimal degrees, select its **FIX** button, and click the corresponding landmark in the image. Use three well-separated, non-collinear references.
4. Select **TARGET**, click an observation, complete its classification/priority/note, and add it to the report.
5. Export the target list as CSV, save the complete analysis as JSON, or print a report. Opening a saved session restores its coordinates and overlays; reload the original image with the same pixel dimensions to restore the visual background.

Useful preferences (active plot mode and reference coordinate fields) persist in `localStorage`. Source images do not leave the browser and are deliberately not put in browser storage.

## Assumptions and limitations

- The image must be map-aligned or close enough to an affine projection for the intended planning accuracy.
- Three-point affine calibration accounts for translation, rotation, skew, and unequal axis scale, but **not** terrain relief, lens distortion, camera perspective, or curved-map projection effects.
- Inputs are WGS-like decimal latitude/longitude values: latitude from −90 to 90 and longitude from −180 to 180.
- References must be non-collinear and should surround the area of interest; extrapolating beyond them increases error.
- Computed coordinates are mission-planning aids, not sensor-certified geolocation. Verify important coordinates in DCS or an authoritative map before use.
- No aircraft-specific TARPS symbology, camera model, classified behavior, or proprietary workflow is claimed or reproduced.

## Why this project

The clearest current community signal was a same-day r/dcsworld post, **“TARPS Target Tool,”** in which a player shared an HTML app made to derive target coordinates from DCS F-14 TARPS pictures. That concrete tool-sharing signal suggested an unmet reconnaissance-analysis workflow. Nearby discussions also show active demand for mission-planning tooling and sustained attention around the recently released F-14B(U).

Sources reviewed on **2026-08-07**:

- r/dcsworld, “TARPS Target Tool” (2026-08-07): https://www.reddit.com/r/dcsworld/comments/1vhmmb5/tarps_target_tool/
- r/hoggit, “Plan the mission before you fly it—free virtual aviation software launching July 31” (2026-07-27): https://www.reddit.com/r/hoggit/comments/1v8dj3g/plan_the_mission_before_you_fly_itfree_virtual/
- r/hoggit, “F-14B(u) JDAM toss/loft prior to mission for DTC” (2026-08-02), another example of players needing clearer pre-mission coordinate workflows: https://www.reddit.com/r/hoggit/comments/1vdmul9/f14bu_jdam_tossloft_prior_to_mission_for_dtc/
- Eagle Dynamics, “DCS: F-14B(U) Released!” (2026-07-24), confirming the module release and its modernized navigation/JDAM context: https://www.digitalcombatsimulator.com/en/news/2026-07-24/

Recon Fix is an original complement to that demand: its focus is general three-reference image calibration, annotation, durable mission records, and CSV/print handoff rather than reproducing another tool’s interface or implementation.
