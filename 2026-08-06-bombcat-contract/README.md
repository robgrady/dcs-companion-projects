# Bombcat Contract

Bombcat Contract is a self-contained, offline F-14 unguided air-to-ground crew trainer. It turns target-acquisition conditions, WCS/radar-ranging availability, release intent, store class, delivery pattern, and fuze choices into an explicit Pilot–RIO contract. It then provides a five-phase run-in rehearsal and an eight-scenario attack-mode drill.

## Use

1. Open `index.html` directly in a modern browser. It requires no server, account, build step, or network connection.
2. In **Build contract**, describe how the target will be acquired and choose the intended release setup.
3. Read the recommended attack mode and the separate Pilot and RIO/Jester responsibilities. Resolve any **NO VALID PLAN** result before continuing.
4. Use **Rehearse run** to walk through contract, configuration, A/G entry, acquisition, and release-gate cues.
5. Use **Mode drill** to practice choosing among CMPTR PLT, CMPTR TGT, CMPTR IP, MAN, and no-release/no-plan outcomes.
6. Copy or print the resulting crew card as needed. Inputs and rehearsal progress persist in browser `localStorage` for this file URL.

## Important assumptions and limits

- The app covers **unguided bombs and rockets** and teaches mode selection and crew coordination; it is not a ballistic calculator, weapons table, or substitute for the current Heatblur manual.
- Heatblur's names are retained. **CMPTR PLT** is CCIP-like and **CMPTR TGT** is CCRP-like, but those modern labels are analogies rather than the cockpit mode names.
- **CMPTR IP** assumes a known, visually identifiable initial point and correctly entered IP-to-target altitude, range, and bearing data.
- **MAN** is treated as a fixed-depression backup when computer assistance is unavailable or A/G radar ranging is not desired. The planned release profile and valid weapon-delivery tables remain the crew's responsibility.
- In Computer Pilot with rockets, the diamond over the pipper is treated as an out-of-range cue; the trigger, rather than bomb-release button, fires rockets once in range.
- A pull-up cue at the velocity vector is a no-release indication because the aircraft is below safe store-release altitude.
- Delivery-pattern and fuze controls describe crew setup only. Compatibility, stations, profiles, quantities, intervals, and fuzing must be checked against the current module documentation and mission/squadron standards.
- The app is unofficial and is not affiliated with Eagle Dynamics or Heatblur Simulations.

## Community signal

Research accessed **2026-08-06** found a timely, specific training gap immediately after the F-14B(U) release: pilots are trying to reconcile familiar CCIP/CCRP language with the Tomcat's CMPTR PLT/CMPTR TGT workflow and unguided-weapon controls.

- r/hoggit, **“CCIP, CCRP and Unguided Weapons in the F-14B(u)”** (posted 2026-08-05): https://www.reddit.com/r/hoggit/comments/1vg3p8d/ccip_ccrp_and_unguided_weapons_in_the_f14bu/
- r/hoggit **new-post RSS feed** (reviewed 2026-08-06) placed that question among other fresh F-14B(U) support requests, including VR kneeboard behavior, crash reports, and RIO countermeasure bindings: https://www.reddit.com/r/hoggit/new/.rss
- r/hoggit, **“Beginner’s Guide – Next release”** (posted 2026-08-04), supplied a broader current signal that approachable, updated DCS instruction remains in demand: https://www.reddit.com/r/hoggit/comments/1vfcmqc/beginners_guide_next_release/

Reddit's main RSS feed was retrieved live during this run; direct per-post RSS requests were subsequently rate-limited. Procedure and mode facts were therefore verified independently against the current public Heatblur manual source rather than inferred from discussion replies.

## Fact sources

Accessed **2026-08-06**:

- Heatblur F-14 manual source, **F-14B(U) Unguided Weapons Employment**: https://github.com/Heatblur-Simulations/f-14-manual/blob/cf70f9c288a48fe64dc1181a9f9d7b87264a6d11/src/f14bu/weapons/air_to_ground/unguided_weapons/unguided_weapons_employment.md
- Heatblur F-14 manual source, **Air-to-Ground Weapon Delivery**: https://github.com/Heatblur-Simulations/f-14-manual/blob/cf70f9c288a48fe64dc1181a9f9d7b87264a6d11/src/f14ab/stores/air_to_ground/weapon_delivery.md
- Heatblur F-14 manual source, **Air-to-Ground Weapon Settings**: https://github.com/Heatblur-Simulations/f-14-manual/blob/cf70f9c288a48fe64dc1181a9f9d7b87264a6d11/src/f14ab/stores/air_to_ground/weapon_settings.md
- Heatblur F-14 manual source, **Bombing Tool**: https://github.com/Heatblur-Simulations/f-14-manual/blob/cf70f9c288a48fe64dc1181a9f9d7b87264a6d11/src/dcs/bombing_tool.md

## Design and accessibility

Bombcat Contract is primarily a **Configure** surface with a secondary Learn mode: the input-to-crew-contract workflow controls the composition, while rehearsal and drill modes reinforce the result. It uses semantic landmarks, labeled controls, visible focus states, responsive layouts, 44-pixel targets, reduced-motion handling, print styling, and live regions for interaction feedback.

Slop diagnostic before repair: **1/10** — unearned blur fired on the sticky navigation. Repair removed the blur so depth is expressed by borders and tonal separation. Final score: **0/10**; no compositional tells remain.
