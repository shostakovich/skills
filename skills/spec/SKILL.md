---
name: spec
description: Write the decisions from the conversation into a short spec and publish it to the project's issue tracker. Use when the user asks for a spec, or to write up what was decided.
---

Turn what was already decided into a spec.

## Before writing

- If no clarify round was done and the scope is unclear, run the clarify skill first. Otherwise, write from what is already known.
- Explore the code you have not seen yet. Use the project's terms and respect its ADRs.

## Writing

- Record every decision from the conversation, and nothing else.
- Keep it as long as the work needs: a bug gets a few lines, a large feature more.
- Leave out any section with nothing to say.
- State each fact once, in the section where it fits.
- Write in prose, Gherkin aside: no file paths, no code.
- Link or attach material from planning, e.g. prototypes, diagrams, research. Keep private data out of anything public.

## Sections

- **Summary**: two or three sentences on what this is about; only for large work.
- **Problem**: the problem, from the user's view.
- **Solution**: the solution, from the user's view.
- **Behaviour**: only for new user-visible behaviour; omit for bugs, UI layout changes and refactoring.
  - Write a few user stories: As a <role>, I want <feature>, so that <benefit>.
  - Add a Gherkin scenario only where an edge case needs precision.
- **Decisions**: only what the user doesn't see: modules, interfaces, schema, API contracts.
- **Tests**: the required integration tests not already given as Gherkin scenarios: a few for a feature, a regression test for a bug. Implementation adds more.
- **Out of scope**: what was deliberately left out.

## Publish

- Show the draft with any open questions you found and wait for the user's go.
- Publish to the project's issue tracker. If it has none, ask where.
