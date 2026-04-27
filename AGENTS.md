# AGENTS.md

## Project Overview

Iskra is an open-source, AI-assisted learning framework. It's a **protocol** — a set of Markdown files (prompts + vault templates) that turn any AI chat into a Socratic mentor with spaced repetition and mastery tracking. No code, no build system, no runtime dependencies. Pure Markdown.

The repo also contains an installable agent skill at `skills/iskra/` that automates vault file management.

## Repository Structure

```
iskra/
├── prompt/
│   └── core-prompt.md          # Standalone mentor system prompt (copy-paste into any AI chat)
├── vault/
│   ├── iskra-vault.md          # Empty vault template (standalone use)
│   └── iskra-all-in-one.md     # Combined prompt + vault (single-paste use)
├── skills/
│   └── iskra/                  # Installable agent skill
│       ├── SKILL.md            # Skill entry point (orchestration)
│       ├── references/
│       │   └── mentor-protocol.md  # Full Socratic mentor protocol
│       └── assets/
│           └── vault-template.md   # Blank vault for skill use
├── docs/
│   └── specs/                  # Design specifications
└── LICENSE                     # CC0-1.0 (public domain)
```

## Validation

- Validate the skill against the Agent Skills spec: `npx skills-ref validate ./skills/iskra`

## Editing Guidelines

- All files are Markdown. Use consistent formatting.
- The vault template uses `---` delimiters with `## ISKRA <SECTION>` headers — do not change this format, it's part of the protocol.
- The skill's `SKILL.md` must stay lean (under 500 lines). Heavy content goes in `references/`.
- `references/mentor-protocol.md` is the canonical mentor behavior definition. Do not duplicate its content in `SKILL.md`.
- `vault/iskra-all-in-one.md` combines the core prompt + vault template. If you update either source, update the all-in-one too.
- All dates use `YYYY-MM-DD` format.

## Conventions

- License: CC0-1.0 (public domain dedication)
- No secrets, no API keys, no credentials anywhere in this repo
- Skill frontmatter follows [Agent Skills Specification](https://agentskills.io/specification)
- Skill `name` field must match parent directory name (`iskra`)
- Description field max 1024 characters

## PR Guidelines

- Title format: `[area] Brief description` (e.g., `[skill] add vault path persistence`, `[prompt] refine scaffolding guardrail`)
- Validate the skill before committing: `npx skills-ref validate ./skills/iskra`
- Keep `prompt/core-prompt.md` and `skills/iskra/references/mentor-protocol.md` in sync when changing mentor behavior
