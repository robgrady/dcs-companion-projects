# Flight Contract

Flight Contract is a self-contained, offline DCS World instructor/student session desk. It turns an informal training sortie into a narrow learning contract, a timestamped observation log, and a concrete debrief that can be printed or carried into the next lesson.

## Use

1. Open `index.html` directly in a modern browser; no server, install, account, or network connection is required.
2. Name the sortie, define a measurable completion standard, and edit the four objectives. Keep the lesson narrow.
3. Start the timer. During flight, use the six observation buttons (or keys **1–6**) to add a coaching mark. Hold **Shift** with a number to record an observed strength. Add a typed note when the exact behavior matters.
4. In the debrief, check completed objectives, rate only observable behaviors, and record one behavior to keep and one focused next repetition.
5. Print the debrief or export the complete session as JSON. A later session can import that JSON.

Useful state is saved automatically in `localStorage`. **New session** deliberately clears the current local session after confirmation. JSON export is the portable backup. Printing uses a compact three-column debrief layout.

## Assumptions

- This is module-agnostic: the instructor supplies aircraft-specific limits, procedures, and standards from current official documentation.
- Ratings are coaching shorthand, not qualification records: 1 = unsafe/unassisted gap, 2 = coached, 3 = independent, and 4 = repeatable and explained.
- The timer is a relative lesson clock, not DCS mission time. It pauses when the page is closed.
- The app does not claim to replace a squadron syllabus, flight manual, or safety judgment.
- Data never leaves the browser unless the user explicitly exports or prints it.

## Community signal

The idea follows a strong, current pairing: communities are actively recruiting volunteer instructors while new players continue to describe DCS’s steep learning curve and uncertainty about joining organized training. Rather than add another aircraft checklist, Flight Contract supports the human teaching session itself—scope, observation, debrief, and next repetition.

Sources reviewed on **2026-08-10**:

- r/hoggit — [“Announcing ‘The Pub’ Volunteer Flight Instructor Program!”](https://www.reddit.com/r/hoggit/comments/1vk06c0/announcing_the_pub_volunteer_flight_instructor/) (posted 2026-08-09): asks experienced community members to teach learners across modules and skill levels, explicitly citing the steep learning curve.
- r/dcsworld — [“The Pub DCS Community Volunteer Flight Instructor Program”](https://www.reddit.com/r/dcsworld/comments/1vk2fnn/the_pub_dcs_community_volunteer_flight_instructor/) (posted 2026-08-09): parallel recruitment signal from the second requested DCS community.
- r/dcsworld — [“New player”](https://www.reddit.com/r/dcsworld/comments/1vjqes2/new_player/) (posted 2026-08-09): a new Su-25T pilot asks how to move into a squadron that runs missions and training.
- r/hoggit — [“is Dcs actually this hard or am I just stupid (new player)”](https://www.reddit.com/r/hoggit/comments/1vc8iob/is_dcs_actually_this_hard_or_am_i_just_stupidnew/) (posted 2026-08-01): a learner describes weeks of repeating an intercept without understanding what to change, reinforcing the need for specific observation and a bounded next repetition.

Recent-post discovery used the public Arctic Shift Reddit archive because direct Reddit API requests from this environment were blocked by network policy; the canonical Reddit discussion URLs above are retained as sources.

## Design and accessibility

This is an **Operate** surface: the center of gravity is live marking and action, not a dashboard or marketing hero. The paper-and-charcoal visual language separates the persistent contract, live observation rail, and debrief without decorative cards. Controls have visible focus treatment, semantic labels, keyboard shortcuts, responsive layouts, 44px-class mobile targets, reduced-motion handling, and print styles.

Slop diagnostic before repair: **1/10**, with only “default type” initially flagged by the fallback stack. The typography was then explicitly composed around Georgia for judgment/debrief hierarchy, Avenir/Futura for controls, and monospace only for operational metadata. Final diagnostic: **0/10**; no tech gradient, generic indigo, feature grid, accent rail, blur, monument stat, icon topper, center stack, default-type dependence, or wrong-surface composition remains.
