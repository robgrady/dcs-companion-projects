# Headspace

Headspace is a self-contained, offline calibration workbench for DCS World head tracking. It turns comfortable physical head movement into a six-axis response reference, guides a repeatable parked-cockpit test, diagnoses common symptoms in a safe adjustment order, and stores successful setup runs locally.

## Use

1. Open `index.html` directly in a modern browser; no server, install, or network connection is required.
2. In **Calibrate**, enter a comfortable physical limit, desired virtual view limit, and curve value for yaw, pitch, roll, and X/Y/Z translation. Select an axis to inspect its response plot and mapping points.
3. Copy the reference into your tracker software manually. Headspace is intentionally vendor-neutral and does not write proprietary TrackIR, OpenTrack, Beam, or other configuration formats.
4. In **Cockpit test**, park the chosen DCS aircraft and rate all six checkpoints.
5. In **Diagnose**, select reproducible symptoms and make one recommended change at a time.
6. In **Logbook**, name the tracker and aircraft, note camera/lighting conditions, and save a complete run. Profiles can also be exported and imported as JSON.

Data is stored in the browser's `localStorage` for this local file. Clearing site data or opening the file under a different browser/profile may hide that state; export JSON for a portable profile record.

## Important assumptions

- Physical inputs are measured from a neutral, repeatable seated posture. Angular axes use degrees and translation axes use centimeters.
- The generated curve is a planning reference, not a claim that every tracking application uses the same curve formula or numeric scale.
- Headspace recommends correcting visibility, camera alignment, lighting, marker loss, and unwanted axis coupling before masking those problems with curves or smoothing.
- Default values are editable starting points, not airframe-, hardware-, or physiology-specific prescriptions.
- The cockpit checkpoints are qualitative. The saved 12-point score is a personal repeatability aid, not an official DCS or real-world grading standard.

## Community signal

Head tracking remains a recurring DCS setup and usability problem rather than a one-time hardware question. Recent community posts describe unstable cockpit pointing, unwanted forward movement while turning, inability to reach panels comfortably, and repeated requests for usable curve settings. The app responds with a vendor-neutral measurement contract and reproducible cockpit test rather than another unexplained settings screenshot.

Sources reviewed on **2026-09-04**:

- r/dcsworld, “this is so [annoying]” — discussion of unstable webcam/head tracking, unwanted translation toward the HUD, panel reach, environmental lighting, calibration, and curve mapping: https://www.reddit.com/r/dcsworld/comments/1nyvbll/this_is_so_fucking_annoying/
- r/dcsworld, “Head tracking query” — community advice centered on OpenTrack curve adjustment and sensitivity: https://www.reddit.com/r/dcsworld/comments/1llnbk7/head_tracking_query/
- r/dcsworld, “12 March 25: any modern easy solution to the headtracker torture?” — setup friction and the need to define range and curves: https://www.reddit.com/r/dcsworld/comments/1j96i2o/12_march_25_any_modern_easy_solution_to_the/
- r/dcsworld weekly support thread (2026-02-23) — evidence that recurring DCS setup and technical-help questions are concentrated into weekly support threads: https://www.reddit.com/r/dcsworld/comments/1rcbvx8/weekly_thread_20260223_questions_on_dcs_pcs/

## Design notes

Headspace uses an **Operate** composition: the calibration contract, active response plot, test state, and corrective actions dominate. It avoids marketing sections, decorative metrics, external fonts, icon grids, and remote dependencies. Keyboard focus is visible, controls meet touch-friendly sizing, layouts collapse for small screens, and nonessential motion respects reduced-motion preferences.
