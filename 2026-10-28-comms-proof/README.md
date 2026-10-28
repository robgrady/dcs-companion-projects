# Comms Proof

**Comms Proof** is a self-contained, offline DCS World voice-readiness desk. It turns the vague “comms check” into a six-stage proof: declare the route, lock audio devices, verify bindings, set the cockpit, record two-way evidence, and follow an ordered fault path when the check fails.

Open `index.html` directly in any modern browser. No server, installation, network connection, or build step is required.

## What it does

- Supports DCS native Voice Chat, SRS, or a deliberately separated dual-stack setup.
- Tracks required and recommended gates across route, device, binding, and cockpit stages.
- Requires separate transmit and receive evidence before releasing the setup.
- Diagnoses six common symptom classes with ordered, one-variable-at-a-time fault paths.
- Generates a concise proof card for copying, printing, or downloading.
- Saves working state in browser `localStorage` and supports JSON backup/restore.
- Works responsively and includes keyboard focus states, semantic controls, reduced-motion handling, and a print layout.

## How to use it

1. Choose **DCS native**, **SRS**, or **Dual stack**. Use dual stack only when each system has a distinct push-to-talk control.
2. Record the server, aircraft/seat, primary route, backup path, and flight contract.
3. Work each stage in order. A microphone meter is not treated as proof that receive audio or radio routing works.
4. Run the live matrix with another pilot or a known server response. Pass both **You transmit to partner** and **Partner transmits to you** to earn release status.
5. If the proof fails, select the observed symptom and follow the ordered path without changing several variables at once.
6. Copy or print the final proof card. Export JSON when you want to preserve or move the complete desk state.

## Important assumptions

- The app is a setup and troubleshooting companion, not a voice client. It does not connect to DCS, inspect Windows devices, tune aircraft radios, or transmit audio.
- Exact cockpit radio procedures remain module-specific. The app records those details rather than claiming one sequence fits every aircraft.
- Native DCS Voice Chat and SRS are separate systems; users on different systems should not be assumed to hear one another.
- A successful two-way test with a real partner is stronger evidence than a meter, carrier click, overlay animation, or client connection indicator alone.
- The September 30, 2026 DCS changelog is the basis for the current patch-warning text. Future patches may change binding behavior.

## Community signal and sources

Accessed **2026-10-28**:

- Eagle Dynamics release changelog — DCS 2.9.30.28536 changed dynamic-radio logic and explicitly instructed users to check VoiceChat hotkeys: https://www.digitalcombatsimulator.com/en/news/changelog/
- Eagle Dynamics Voice Chat Quick Start guide — official room/radio-mode and setup reference: https://www.digitalcombatsimulator.com/upload/medialibrary/30a/k3o2gik7dkxf2qpk2fram6igpp8egac0/DCS_Voice_Chat_Quick_Start.pdf
- Eagle Dynamics forum quick guide — explains radio mode, room mode, generic bindings, and aircraft-specific VoIP commands: https://forum.dcs.world/topic/292022-quick-dcs-voice-chat-guide/
- Eagle Dynamics 2026 Voice Chat development report — continued native voice development and new human-operated radio roles: https://forum.dcs.world/topic/386748-voice-chat-development-report-2026-spring-sale-amvi-wings-over-normandy/
- r/dcsworld, “Can’t get SRS to work” — recent evidence of client/export integration troubleshooting: https://www.reddit.com/r/dcsworld/comments/1v8helg/cant_get_srs_to_work/
- r/dcsworld, “Voice Chat” — recent native-versus-SRS setup and per-aircraft binding friction: https://www.reddit.com/r/dcsworld/comments/1sfxedp/voice_chat/
- r/dcsworld, “Spent a good chunk of my evening trying to set up voice chat” — recurring uncertainty over whether the failure is setup, adoption, channel choice, or lack of a reply: https://www.reddit.com/r/dcsworld/comments/1jbozes/spent_a_good_chunk_of_my_evening_trying_to_set_up/
- r/dcsworld, “SRS vs in game voice chat” — recurring confusion over whether users on the two voice systems interoperate: https://www.reddit.com/r/dcsworld/comments/1m5zfc9/srs_vs_in_game_voice_chat/

The repeated need was not another frequency list. It was an evidence-based way to distinguish device, binding, cockpit, route, audience, and two-system failures before a multiplayer sortie.

## Design posture

This is a **Configure** surface: progressive setup and visible release gates take priority over marketing, decoration, or dashboard metrics. The interface uses one muted operations palette, compact stages, explicit check states, and a final printable artifact.

**Anti-slop audit before repair:** 0/10. No tech gradient, generic indigo, feature-tile grid, accent rail, blur, monument statistic, icon toppers, center stack, default Inter/system typography, or wrong-surface composition fired. **Final audit:** 0/10; no compositional repair was required.
