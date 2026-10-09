---
name: review
description: Review a change with fresh agents, verify every finding, and fix and commit what is clearly right. Use when the user asks for a review or code review of a branch, a pull request, a commit range or a folder.
---

Review a change, verify each finding and fix what is clearly right.

## Target

- By default, the diff against the base plus uncommitted changes. The base is the branch this one forked from, else the remote's default branch.
- If the user names a pull request, branch, commit range or folder, review that instead. Review a folder in full.
- For a pull request, treat its open review comments as findings.
- Gather the spec from the issue, pull request and commit messages, and read the project's conventions and ADRs.

## Find

- Have fresh agents review the target with the spec and the conventions, instead of your conversation. Scale them to its size: one agent for all angles on a small change, one per angle on a larger one, and more per angle by files on a large one. If you cannot start agents, take the angles one at a time.
  - **Correctness**: line by line; what deleted code guaranteed and whether that still holds; callers and callees of changed code.
  - **Security and tests**: new attack surface, missing tests.
  - **Spec and conventions**: missing, partial or wrong against the spec; scope creep; the project's conventions and ADRs.
  - **Simplicity**: reuse, needless code, fixes at the wrong level, comments that repeat the code, stale docs.
- Review once. Tell reviewer agents to review directly, without starting this skill or more agents. The tests check your fixes, not another review.
- Report every finding, including problems that already exist on the base. An empty result is a valid result.
- Skip what linters and the typecheck catch, and pedantic nitpicks.
- Each finding names file and line, a concrete failure scenario and its blast radius. Mark taste as taste.

## Verify

- Have another fresh agent check the findings against the code, more for many findings: confirmed, plausible or refuted. Refute only with a quoted line of code or spec.
- Behaviour that the spec, pull request or issue intends is not a finding, nor is an exception the project documents.

## Fix

- Fix confirmed findings that are clearly right, with a regression test for each bug.
- Fix small problems that already exist on the base. For larger ones, propose a separate pull request or issue for the user to create.
- Leave taste, plausible findings, unclear intent and larger redesigns open, and say why.
- Commit each fix on its own to the reviewed branch. On the default branch, create a branch first.
- Fixes in the user's uncommitted work stay uncommitted.
- Run the affected tests after each fix and the full test suite at the end.

## Report

- Report a table: severity (high, medium, low), file and line, finding with failure scenario and blast radius, verdict (fixed, or open with the reason).
- Sort by severity, correctness before cleanup. Group problems already on the base separately.
- Then give the number of refuted findings.
