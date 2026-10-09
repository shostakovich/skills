# Writing skills here

Skills follow the [Agent Skills spec](https://agentskills.io/specification).

## Layout

- One skill per directory: `skills/<name>/SKILL.md`; `name` matches the directory.
- Frontmatter: `name` and `description` only.
- `description` says what the skill does and when to use it, with the words a user would say.
- Extra files (`references/`, `scripts/`) only when `SKILL.md` can't stay small otherwise.

## Agent-agnostic

- Say what to do, not which tool does it: no tool names (`Bash`, `Read`, `Task`), no agent-specific paths (`~/.claude`), no agent-specific frontmatter.
- Scripts: POSIX shell, dependencies named at the top.

## Small

- Aim for ~25 lines; `SKILL.md` has a hard limit of 50.
- English, imperative bullets. No prose on why a rule exists.
- Public repo: no personal names, hosts or private data.

## Review

- The owner approves every line and must be able to explain each one.
- Before approval, a fresh agent with no context reads only the `SKILL.md` and restates when it applies and what it does. If it misreads, rewrite the skill.
- `bin/check` passes (needs `skills-ref`, installed as in `.github/workflows/check.yml`).
