# product-skills

A collection of [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) for Claude Code and other AI agents. Each skill packages instructions, workflows, and reference material that Claude loads on demand when a task matches — turning open-ended prompts into structured, repeatable work.

## Available skills

| Skill | What it does |
|-------|--------------|
| [`market-research`](market-research/SKILL.md) | Conducts structured, web-powered market research — market sizing (TAM/SAM/SOM), competitive landscapes, customer segmentation, pricing, and go/no-go opportunity assessments. Produces decision-ready briefs, not generic overviews. |

## Installing a skill

Skills are directories containing a `SKILL.md` file. To make one available in Claude Code, copy its folder into your skills directory:

```bash
# Personal skills (available in every project)
cp -r market-research ~/.claude/skills/

# Or project-scoped skills (shared with a repo)
cp -r market-research /path/to/your/project/.claude/skills/
```

Claude Code discovers the skill automatically and invokes it when a request matches the skill's `description`.

## Repository layout

Each skill lives in its own top-level directory:

```
<skill-name>/
├── SKILL.md              # required: frontmatter (name + description) and instructions
└── references/           # optional: supporting files the skill links to
    ├── ...
```

`SKILL.md` links to files under `references/` using relative paths (e.g. `` `references/data-sources.md` ``), so the folder must sit next to `SKILL.md`.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for the skill layout convention and a starter template.

## License

[MIT](LICENSE)
