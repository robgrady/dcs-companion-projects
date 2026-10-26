# Auth Shelter

Auth Shelter is a self-contained, offline DCS World access-continuity desk. It helps a pilot prepare a deliberately offline solo session before losing internet, or isolate an authorization failure without immediately reinstalling, deleting files, updating, or changing several variables at once.

## Why this project

Recent DCS community posts show a recurring pattern: account-service disruptions or local authorization failures can disable paid modules, users are uncertain about the meaning of remaining-time warnings, and advice often jumps rapidly from service status to DNS, clock, repair, license, or offline-mode theories. Separate discussions ask whether DCS can be used during travel or unreliable internet and reveal confusion about the limits of offline mode, trial modules, and hardware changes.

Auth Shelter turns those questions into two explicit workflows: **prepare while connected** and **preserve evidence during a failure**. It does not claim to detect account, network, license, or DCS state.

## Use

1. Open `index.html` directly in a modern browser. It needs no server, install, network, build step, or external library.
2. Enter a session label, required aircraft/module, and optional start/end window.
3. Choose one operating intent: normal online launch, planned offline sortie, unexpected authorization failure, or PC change while offline.
4. Click each access gate to cycle it through **unknown**, **yes**, and **no**. The decision strip and ordered action card update immediately.
5. During a failure, select the closest symptom and work the fault ladder from top to bottom. Change one variable at a time.
6. Add time-stamped observations to the evidence wire. Export the worksheet as JSON for backup or support context, import it later, or print a compact brief.

Useful state is saved in browser `localStorage`.

## Important assumptions

- This is a simulation companion, not a DCS plug-in, entitlement checker, network monitor, account client, or real-world aviation tool.
- A **yes** gate is a human assertion. The app cannot inspect DCS, Eagle Dynamics services, licenses, installed modules, account state, network state, or hardware identity.
- Offline mode must be prepared using DCS while connected. Auth Shelter cannot enable, disable, extend, or repair DCS offline authorization.
- DCS trial licenses require internet access and should not be treated as offline entitlements.
- Multiplayer and network-dependent mission services are outside a planned offline sortie.
- Hardware and operating-system changes can affect machine-bound authorization. Return DCS online before changing the machine whenever possible and consult current official guidance.
- Authorization behavior, limits, messages, and support procedures can change. The app intentionally avoids asserting a universal offline-duration number; verify current policy with Eagle Dynamics.
- Do not place passwords, payment details, serial numbers, or other sensitive account data in the evidence log or exported JSON.
- For persistent loss of owned-module access, preserve the exact warning, timestamp, DCS version, and relevant log context, then use Eagle Dynamics support.

## Community and official signals

Accessed October 26, 2026:

- Reddit / r/dcsworld — “Authorization Failed” (September 11, 2026), reporting an authorization warning with modules disabled: https://www.reddit.com/r/dcsworld/comments/1ndm23x/authorization_failed/
- Reddit / r/dcsworld — “Server Status” (August 22, 2026), a cluster of reports about the website/login path being unavailable and authorization consequences: https://www.reddit.com/r/dcsworld/comments/1mvgl1f/server_status/
- Reddit / r/hoggit — “What does ‘Authorization is valid for 2d 23h 59m’ mean?” (June 11, 2026), showing uncertainty about warnings and access state: https://www.reddit.com/r/hoggit/comments/1l9qzk8/what_does_authorization_is_valid_for_2d_23h_59m/
- Reddit / r/dcsworld — “Offline mode while traveling” (May 1, 2026), discussing preparation for play without reliable internet: https://www.reddit.com/r/dcsworld/comments/1kbbr4c/offline_mode_while_traveling/
- Eagle Dynamics support — official DCS offline-mode article, including activation, return-online, trial-license, and hardware/OS-change cautions: https://www.digitalcombatsimulator.com/en/support/faq/authorization/
- Eagle Dynamics forum — recurring authorization-server error discussion and user troubleshooting context: https://forum.dcs.world/topic/372661-authorization-server-unavailable/

## Files

- `index.html` — complete offline app with inline CSS and JavaScript
- `README.md` — usage, assumptions, and source context
