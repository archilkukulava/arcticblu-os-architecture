# Evals

The system has its own evals. Any change to an agent's instructions, tools or model is measured before it reaches
a portfolio manager (PM).

**How the measurement works**

- **Held-out questions.** A fixed set of questions, half used for tuning and half held out and never tuned on.
- **A blind panel.** Two versions of an agent (two models, two sets of instructions) are compared by a panel from
  two model families that sees no names, every pair in both orders. A
  judge's verdict counts when it picks the same answer both ways round, and the panel counts when both
  judges agree. The decision rule is written down before any result is read. A judge is never the model under
  test, and the code refuses to run if it is. Each agent's model was chosen
  this way.
- **Judges validated before they are trusted.** They were first given planted cases, some with one known mistake
  and some correct. They found every planted mistake and invented none. Code keeps a finding when its quotes
  appear word for word in the answer and in the agent's own material.
- **Judge bias controlled.** Model judges favour the longer answer, so verdicts are re-read at matched length.
- **A mistake has a definition.** It is a statement the agent's own tool results contradict, or a figure no tool
  gave. Two blind reviewers count them apart, and a third rules where they differ.

**A regression eval suite for every change**

Before and after any change to an agent's instructions, tools or model, the agents run the same fixed eval suite, so a
change that makes answers worse is caught before a PM sees it.

- Half of the suite is held back and never tuned on. A case is assigned to its half by a hash of its id, so it can
  never change sides.
- The suite is tested before it is trusted, with the reference answer required to score 100% and an empty
  answer 0%.
- Answer keys for live figures are read from the page's own function when the suite runs, so they never go stale.
- A second check replays the PMs' real recorded conversations through the production checks with no model
  call, so it costs nothing. The same conversations are replayed to price a change to context management before it
  ships.

**Back-testing the platform's own methods**

Before a PM relies on a figure the platform calculates, the calculation is checked against history. A back-test
tool runs the platform's real code as if today were a past date, using the data as it existed on that day,
then compares the result with what happened next. Companies that have since left the S&P 500 are included, so
the test is not flattered by the survivors. The uncertainty rating on each company report was chosen this way,
across 25 dates from 2013 to 2025.

[Back to the overview](../README.md)
