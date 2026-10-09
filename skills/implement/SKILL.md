---
name: implement
description: Implement one issue and commit it to the current branch. Use when the user asks to implement an issue, a spec or a change planned in the conversation.
---

Implement one issue on the current branch: a spec, a sub-issue or a change planned in the conversation.

## Before building

- Fetch the issue from the argument or the conversation and state its title. If the reference is ambiguous or the issue has sub-issues, ask which one.
- For a sub-issue, read its spec too.
- Explore the code it touches. Use the project's terms and respect its ADRs.
- If the current branch is the default branch, create a branch first.
- Run the full test suite once to know what already fails.
- Plan the work as a todo list, then work through it without waiting for a go.

## Building

- Build only what the issue asks for, plus what it needs to be secure and correct.
- Follow the boy scout rule: fix small, clear problems you notice outside the issue. Report larger ones.
- Start with a failing integration test for each scenario and test the issue lists.
- Then work test-first and outside-in, London school: a failing unit test with collaborators mocked, then just enough code to make it pass.
- Add further integration tests sparingly.
- Write clear, meticulous code from the start: small methods, names that say what they do, the project's style.
- Run the affected tests often, the typecheck if the project has one, and the full test suite at the end.
- Decide open questions yourself, with the cleanest, simplest solution.
- Stop only for a relevant problem, e.g. the issue contradicts the code, cannot be built as written, or would cause harm as written, such as a security hole or data loss. Leave the work uncommitted and report the problem.

## Done

- Commit to the current branch once the full test suite passes, apart from failures that were there before. Reference the issue in the commit message; give each fix outside the issue its own commit.
- Report what you built, the decisions you made, anything left open, and what you fixed or found outside the issue.
