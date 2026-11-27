# Autonomous work

The agents do most of their work autonomously. They watch the market and the book of each portfolio manager (PM), and act
when a company files, results come out or a thesis condition breaks.

- **Idea sourcing.** A scout gathers
  candidates from the PM's own style screen, insider buying, unusual options activity, value-chain companies and
  technical leaders. It sets aside what the PM already holds, watches or dismissed, ranks the rest by fit, and
  writes up the best few as one-page cases in the PM's inbox.
- **It learns the PM's taste.** It turns the reasons a PM gives for dismissing ideas into proposed changes to
  their style profile.
- **Thesis-break monitoring.** Every thesis carries "warn me if" conditions. Code checks them daily and after
  each report, and tells the PM at once when one breaks.
- **Watch rules.** A PM writes a valuation or chart rule. Code detects that it may be met, and one structured call
  gives the verdict with its reasons.
- **Reading every filing.** When a company files, code draws the passages that changed and an agent writes the
  entry in that company's notebook.
- **Reading every results release,** within minutes of its filing with the SEC. A small model finds each figure
  in the release's tables, and code reads the value from the table itself. The figures reach Slack set against
  consensus.
- **A nightly notebook** for every covered company, **morning and evening briefs** for each PM, a **weekly
  portfolio review**, a **monthly report**, a reading of **the Fed's words**, and a weekly review of the
  **value-chain maps**.
- **The agents review themselves.** Flagged runs are grouped by likely cause, with a fix proposed for each.

Each of these leaves its own record of what it did and what it cost.

[Back to the overview](../README.md)
