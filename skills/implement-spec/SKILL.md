---
name: implement-spec
description: Implement a whole spec unattended, one sub-issue after another with fresh agents, and ship it as one pull request. Use only when the user asks to build a whole spec unattended, for example overnight.
---

Implement a whole spec without asking the user anything, and ship it as one pull request.

## Before building

- Start only on a clean working tree; otherwise stop and report.
- Fetch the spec from the argument and its sub-issues with their blockers, linked or written in their text. A sub-issue is finished once it is closed or its commit is on the branch. If the spec has no sub-issues at all, treat it as the only one.
- If the current branch is the default branch, create a branch first.

## Building

- Work through the unfinished sub-issues one at a time, each once all its blockers are finished.
- Give each to a fresh agent with only its reference, to build with the implement skill without asking questions. If you cannot start agents, build them yourself one at a time.
- When a sub-issue ends without its commit, discard the uncommitted work and skip every sub-issue it blocks, directly or not. Comment on it and on each skipped one why it stays open.

## Done

- If any sub-issue is finished, ship the branch with the ship skill and pass it the issues the pull request closes: the finished sub-issues, and the spec only if all are finished.
- Report the pull request, the finished sub-issues, the skipped ones with reasons, and the decisions the agents reported.
