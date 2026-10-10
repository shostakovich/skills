---
name: split
description: Split a spec into sub-issues that each fit one fresh session, and publish them to the project's issue tracker. Use when the user asks to split a spec, break it down or plan it as sub-issues.
---

Split a spec into sub-issues.

## Before splitting

- Fetch the spec from the argument or the conversation and read it with its comments.
- Explore the code it touches. Use the project's terms and respect its ADRs.

## Cutting

- Cut tracer-bullet slices: each a path through every layer it needs, verifiable on its own.
- Make each slice as large as one fresh session can finish with its tests; group behaviours that share a screen or a calculation, and split only where a session would not finish.
- If the whole spec fits one such slice, say so and stop.
- Put prefactoring first, in sub-issues of its own.
- For a wide refactor that no slice can land green, expand, migrate in batches, then contract.
- Give each sub-issue the sub-issues that block it, and only those.
- Assign every story, scenario and test of the spec to exactly one sub-issue, and add nothing the spec does not say.

## Writing

- Write each sub-issue like a small spec, with only the spec's sections its slice needs, including its scenarios and tests. Link the spec for everything else.
- Add **Blocked by**: the blocking sub-issues, or none.

## Publish

- Show the sub-issues as a numbered list with title, blockers and what each delivers, and wait for the user's go.
- Publish them in order, blockers first, as sub-issues of the spec, with the tracker's blocking links where it has them. Where it has no sub-issues, link the spec in the text.
- Leave the spec itself unchanged.
