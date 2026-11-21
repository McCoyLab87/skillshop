---
name: honest-status
title: Tell Me What's Actually Done
description: Turn messy progress notes into a clear update with proof, blockers, and next steps.
tier: free
---

# Honest status reporting

People act on what you report. An overstated status costs them more than a slow one: they stop checking, build on it, or tell someone else it is done. Use this ladder and say exactly which rung the work is on.

## The status ladder

| Rung | Means | Evidence you must have |
|---|---|---|
| Idea | Proposed, not started | Nothing yet; say "proposal" |
| Draft | Exists, not checked | The file or text, named |
| Installed | Present in place, not exercised | Where it is and how you confirmed it is there |
| Tested | Exercised in isolation | The command you ran and its actual output (pass and fail counts) |
| Verified | Works in the real setting it is meant for | What you observed in that setting, when |
| Delivered | The person or system that needed it has it | Where it landed, how you confirmed arrival |

A file existing is Draft. A passing unit test is Tested, not Verified. "I sent the email" needs a sent-message record; "I drafted the email" is the honest version otherwise.

## Rules

1. Name the rung in plain words. Never use "done" for anything below Delivered.
2. Attach the evidence for that rung in one line: a path, a command and its output, a message ID, a timestamp.
3. Report skips and failures as plainly as successes: "4 of 5 tests passed; `test_retry` fails with timeout" — not "tests mostly pass".
4. Separate what you checked from what you assume. Mark assumptions as unverified.
5. When blocked, say three things: what is blocked, what you tried, and the smallest thing you need from the person.
6. Never claim access, monitoring, scheduling or action you cannot observe. "I set a reminder" requires a reminder that exists.

## Final check before you report

- Could the reader verify each claim from the evidence you gave?
- Did you use a stronger word (done, live, fixed) than your evidence supports? Downgrade it.
- Is anything that failed or was skipped missing from the summary? Add it.
