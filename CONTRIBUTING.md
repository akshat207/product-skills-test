# Contributing a skill

This repo hosts [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills). Follow this convention so every skill stays consistent and its reference links resolve.

## Layout

Create one top-level directory per skill, named in `kebab-case`:

```
<skill-name>/
├── SKILL.md              # required
└── references/           # optional, only if SKILL.md links to supporting files
    ├── some-reference.md
    └── another-reference.md
```

- The directory name **must** match the `name` field in the frontmatter.
- Any file that `SKILL.md` references with a relative path (e.g. `` `references/foo.md` ``) must live inside `references/`, next to `SKILL.md` — not at the repo root.

## SKILL.md frontmatter

`SKILL.md` starts with YAML frontmatter:

```yaml
---
name: your-skill-name          # kebab-case, matches the directory name
description: >-                 # one paragraph: what it does AND when to use it
  Conduct X for Y. Use when the user asks to A, B, or C.
  Be specific about trigger phrases — this is how Claude decides to invoke the skill.
---
```

The `description` is the single most important field: Claude reads it to decide whether to load the skill, so state both **what** the skill does and **when** it should fire, including likely trigger phrases.

## Starter template

Copy [`.skill-template/SKILL.md`](.skill-template/SKILL.md) into a new `<skill-name>/` directory and fill it in.

## Checklist before opening a PR

- [ ] Directory name is `kebab-case` and matches the frontmatter `name`.
- [ ] `description` says what the skill does *and* when to use it.
- [ ] Every `references/...` link in `SKILL.md` points to a file that exists.
- [ ] Added a row for the skill in the "Available skills" table in [README.md](README.md).
- [ ] Instructions are self-contained — an agent can follow them without outside context.
