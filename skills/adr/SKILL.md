---
name: adr
description: Record a hard-to-reverse decision as an architecture decision record in DECISIONS.md. Use when the user wants to write an ADR or record a decision, or when a conversation settles a decision a future reader would question.
---

Record the decisions a future reader would otherwise question or undo.

## When

- Offer an ADR only for a decision that is hard to reverse, surprising without context, and the result of a real trade-off.
- Write it only after the user agrees.

## File

- All ADRs live in `DECISIONS.md` at the root, numbered on from the highest. Create it with `# Decisions` and the first ADR.
- If the project keeps ADRs in separate files, ask whether to move them into `DECISIONS.md`, keeping their text word for word and adding only the heading and a status line with the date of their first commit; if not, add a new file in their folder, in the format below.

## Writing

- Write ADRs in English, each like this:

  ```md
  ## 0007. Store readings in SQLite

  Accepted, 2026-10-09

  - **Context:** One server, a single writer, no backup infrastructure.
  - **Decision:** SQLite instead of Postgres.
  - **Consequences:** No concurrent writers; moving to Postgres later means a data migration.
  ```

- **Context** names the forces that made the decision necessary.
- **Decision** names the chosen option, and a rejected one only if someone would otherwise suggest it again.
- **Consequences** names what the decision costs, not only what it gains.
- Keep each field to one or two sentences.
- Change an accepted ADR only to mark it superseded. When a decision replaces an ADR, name it in the new ADR's Context and change the old one's status line to `Superseded by NNNN, <date>`.
