# Axis Wire

Axis Wire is a self-contained, offline DCS World response-curve workbench. It helps a pilot reason about DCS Axis Tune values before changing a live control profile, then validates the resulting curve with a short precision-gate exercise.

## Use

1. Open `index.html` directly in a modern browser; no server, install, or internet connection is required.
2. Name the profile and choose a starting posture: **Sensor slew**, **Head look**, or **Flight axis**.
3. Adjust deadzone, curvature, Saturation X/Y, invert, and slider mode. Drag **Bench input** to inspect the modeled transfer curve.
4. Open **Validate feel** and match each amber gate with the teal needle. Lock ten samples to save a precision score.
5. Enter cockpit findings under **Pilot notes**, then copy, print, or export the recipe. State persists in `localStorage` for this file origin.

## Important assumptions

- Axis Wire is a planning and comparison model; browsers opening a local file cannot read DirectInput axes without additional software. The bench slider or keyboard arrows stand in for physical travel.
- The response model approximates the intent of DCS Axis Tune controls so settings can be compared consistently. It is not an official Eagle Dynamics implementation and should not be treated as a bit-for-bit reproduction of DCS internals.
- Positive curvature softens center response, deadzone removes center travel, Saturation X reduces required physical travel, and Saturation Y limits output. Final values must be entered and verified in **DCS → Options → Controls → Axis Tune**.
- Presets are starting hypotheses, not airframe recommendations. Always validate in the relevant cockpit page and flight condition.

## Why this exists

Recent community traffic shows the same underlying friction across sensors, view control, and flight hardware: pilots can bind an analog control but struggle to make its response predictable. Axis Wire turns that trial-and-error into a visible curve plus a repeatable test.

Signals reviewed on **2026-08-17**:

- A current r/hoggit pilot reported that F-16 sensor slew rates feel very different between radar and HAD pages while learning SEAD, highlighting the need to compare fine-control response deliberately: https://www.reddit.com/r/hoggit/comments/1vpbgko/are_the_f16_sensor_slew_rates_way_different_per/
- A current r/dcsworld post asked how to make a VKB POV analog stick work for view control, another example of analog mapping and response confusion: https://www.reddit.com/r/dcsworld/comments/1vqk2mg/dcs_bind_issue/
- A recent r/hoggit user sought a large forward deadzone in OpenTrack because small head movement prevented a stable view: https://www.reddit.com/r/hoggit/comments/1vj6wbr/add_a_large_deadzone_only_infront_opentrack/
- Similar head-tracking calibration trouble appeared again in both communities on August 13: https://www.reddit.com/r/hoggit/comments/1vnirhz/opentrack_problem/
- Eagle Dynamics remains the authoritative product source; DCS World’s current news page was checked for the present module/update context: https://www.digitalcombatsimulator.com/en/news/

## Privacy and portability

The app has no external runtime dependencies, analytics, network calls, or build step. Exported JSON contains only the profile values, notes, and locally saved run summaries shown in the app.
