---
name: clarify
description: Settle every open decision of a plan with the user, in rounds, before building. Use when the user wants to clarify or talk through a plan, or when a non-trivial request leaves real choices open.
---

Interview the user until you share an understanding of the plan.

## Rounds

- Before the first round, explore the code and docs thoroughly. Never ask the user what you can find out yourself.
- Treat the plan as a tree: a decision can be asked once the decisions it depends on are settled.
- If the request is too vague to build the tree, start with a round 0 that only clarifies what the user wants to achieve. Then explore deeper with that goal.
- Each round, ask every decision that can be asked now, then wait for the answers.

## What to ask

- Ask only genuine decisions: each option is one you would recommend in a realistic situation. If only one is serious, decide it and list it under Decided.
- Choose the cleanest, simplest solution unless something strongly speaks against it, e.g. security.
- No scope creep: only the decisions the plan needs. A small change gets few questions, or none.
- Keep each question just long enough to be understood.

## Format

Start each round with what you decided, if anything, so the user can veto:

**Decided**
- <decision>: <reason in a few words>

**Questions**
1. **<title>**: <question, with options if any>
   → Recommendation: <your recommendation>

## Done

When nothing relevant is left to decide, summarize the decisions and wait for an explicit go, even if you asked no questions.
