---
name: ubiquitous-language
description: Keep a project's ubiquitous language in GLOSSARY.md. Use when the user wants to pin down domain terms or a glossary, or when a term is fuzzy, overloaded or used against the glossary.
---

Keep the project's domain language precise while you plan with the user.

## Files

- The glossary is `GLOSSARY.md` at the root; with several bounded contexts, one in each context's folder.
- If there is only a `CONTEXT.md`, ask whether to rename it; if not, use it as it is.
- Create the glossary only when it gets its first term.

## In the conversation

- When the user uses a term against the glossary, say so at once.
- When a term is fuzzy or overloaded, propose one precise term.
- Probe the boundaries between terms with concrete edge-case scenarios.
- When the user says how something works, check the code and point out contradictions.
- Write a term to the glossary only after the user agrees to it.

## Glossary

- Start with `# <context name>` and one or two sentences on what it covers.
- Group terms by topic. Only terms a domain expert would use: no general programming concepts, no implementation details.
- Include the domain's actions and events, not only its things.
- Write each term like this:

  ```md
  **Invoice** · _de:_ Rechnung
  - A request for payment sent to a **Customer** after delivery. Not a **Quote**, which comes before the order.
  - _Example:_ "Invoice 2026-041 for 3 hours of consulting, due in 14 days"
  - _Avoid:_ Bill
  ```

- Write the glossary in English, with terms named as in the code. If the user's language is not English, add the term in it, as the UI shows it.
- Define the term in one or two sentences, and how it differs from the terms most easily confused with it.
- Add an example where the definition alone stays abstract.
- Bold other glossary terms. Under _Avoid_, list the rejected synonyms.
