# Monitoring, cost and human control

**A steward watches the platform.** It is plain code with no model, and it checks health through the day and
correctness every day: jobs, data freshness, spending against every cap, returns and positions against the
broker's own statement, and prompt-cache health. It repairs routine faults by itself from a fixed
playbook (rerun a job, renew a read-only sign-in, pause a paid job that keeps failing) and raises the rest to a
person. A weekly review groups flagged agent runs by likely cause and proposes fixes.

**Where the human decides.** A portfolio manager (PM) confirms what is theirs to decide: a portfolio view before it enters a
calculation, a memory, an alert, the plan of a long research job and the start of a paid job. The rest of the
agents' work runs without asking.

**Cost controls**

- Layered limits where the tightest wins: per turn, per helper run, per task, per PM, per day, per month.
- Calls in flight hold their estimated cost, so parallel workers cannot each be admitted to the same money.
- Near a limit the agent is told this is its last call, so it ends with an answer.
- A test requires each request to begin with the whole previous one, byte for byte, to protect the cache.
- PM conversations read 82% of their input from cache.

[Back to the overview](../README.md)
