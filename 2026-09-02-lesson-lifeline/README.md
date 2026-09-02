# Lesson Lifeline

Lesson Lifeline is a self-contained offline companion for DCS World training missions. It keeps user-authored tutorial prompts visible, resumable, readable aloud, and easy to advance from a second screen or tablet when the in-simulator instruction has disappeared.

## Use

1. Open `index.html` directly in a modern browser. No server, account, network connection, or build step is required.
2. Select **New lesson**.
3. Enter a lesson title and aircraft/module label.
4. Paste or type one prompt per line. Use `PANEL ZONE | Instruction` to add a short location cue; plain, numbered, and bulleted lines also work.
5. During training, use the large active prompt and:
   - **Left / Right Arrow** to move between prompts.
   - **Space** to check the current prompt and advance.
   - **R** to read the prompt aloud when browser speech synthesis is available.
   - The stopwatch to measure a difficult step.
   - The scratchpad to record switch locations, frequencies, or the point where progress stopped.
6. Use **Print lesson** for a compact paper/PDF reference. Use **Export** to save one lesson as JSON, and **Import** to restore that file later.

Lessons, completion state, current position, and notes persist in browser `localStorage`. Keyboard shortcuts are deliberately disabled while typing in an input or text area.

## Assumptions and limits

- Lesson Lifeline does not scrape DCS, inspect `.miz` files, or capture text from the simulator. The pilot supplies prompts from notes or other material they are entitled to use.
- The app contains no aircraft procedures or performance claims. Users should verify every instruction against the current DCS module manual and current module behavior.
- Browser speech synthesis voice and availability vary by platform. Every other core feature works without it.
- Data stays in the browser unless the user explicitly exports a JSON file. Clearing browser site data may remove saved lessons.
- Printing uses the browser print dialog and lays out the complete active lesson, not only the current prompt.

## Community signal

The project responds to a specific, recurring DCS training problem: instructional text can disappear before a learner has located the referenced cockpit control, and the learner may have to restart a long lesson to recover the instruction.

Sources reviewed on **2026-09-02**:

- Reddit r/hoggit, **“DCS World Tutorials”** — an F-14B learner reports that long cold-start instructions disappear before the relevant panel area can be found and asks how to avoid restarting repeatedly: <https://www.reddit.com/r/hoggit/comments/1oc0e4d/dcs_world_tutorials/>
- Eagle Dynamics Forums, **“Trying to learn about the Tacan but text disappears in training to quick?”** — an F/A-18C learner describes instruction text disappearing while trying to inspect gauges and repeatedly restarting the training mission; replies suggest pausing or exporting mission text: <https://forum.dcs.world/topic/216899-trying-to-learn-about-the-tacan-but-text-disappears-in-training-to-quick/>
- Eagle Dynamics Forums, **“Tutorial question”** — another learner asks to recover written instructions after they disappear because otherwise a late-lesson stall can require a complete restart: <https://forum.dcs.world/topic/95487-tutorial-question/>
- Eagle Dynamics Forums, **“Training Missions”** — users request repeatable previous instructions and describe reminders superseding prompts that do not return: <https://forum.dcs.world/topic/48952-training-missions/page/5>

The Reddit report is the recent trigger; the older forum threads show that the workflow problem is persistent rather than a one-off module complaint.

## Files

- `index.html` — complete application with inline CSS and JavaScript
- `README.md` — usage, assumptions, limitations, and source record
