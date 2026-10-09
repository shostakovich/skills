---
name: ship
description: Ship the current branch as a pull request - final review, a few clean commits on the latest base, push. Use when the user wants to ship a finished branch as a pull request.
---

The base is the branch this one forked from, else the remote's default branch.
Write commits, branch name and pull request in English.

## Steps

1. **Issue.** Take it from the argument, the branch name or the commit messages. If none is known, ship without one.
2. **Base.** Bring in the latest base.
3. **Review.** Have a fresh agent with no context do the final review of the full diff against the base. Decide each finding yourself: fixed, or rejected with a reason.
4. **Commits.** Rebuild the branch as a few atomic commits on top of the base, by any method:
   - Docs, behaviour-neutral refactoring and behaviour changes go in separate commits.
   - Tests go with the code they test.
   - Review fixes go into the commit whose code they fix.
   - Each commit passes the tests it touches; the content stays exactly as after the review.
5. **Branch name.** If the branch is not pushed yet and its name is not short, descriptive and free of agent names such as claude or codex, rename it.
6. **Push.** Only after the full test suite passes, apart from failures the base already has; fix failures the branch causes in the matching commit. Force-push only with `--force-with-lease`, and only if nobody else has pushed to the branch.
7. **Pull request.** If one already exists for the branch, update it. Otherwise use the repository's template, wherever its forge keeps it; if there is none, use [this skill's template](assets/pull-request-template.md). Title in the imperative. Link the issue, if known.

## Summary

Report to the user:

- The commits, one line each.
- The review findings with their verdicts.
- Test failures the base already has, if any.
- A change table of the branch's own diff against the base. Test files count as Tests, documentation as Docs, the rest as Code:

  |       | Files | +   | −  | Net |
  |-------|-------|-----|----|-----|
  | Code  | 3     | 120 | 40 | 80  |
  | Tests | 2     | 90  | 5  | 85  |
  | Docs  | 1     | 10  | 0  | 10  |
  | Total | 6     | 220 | 45 | 175 |

- As the last line, the pull request URL.
