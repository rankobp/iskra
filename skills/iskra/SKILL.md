---
name: iskra
description: >
  AI-assisted Socratic learning mentor with spaced repetition and mastery tracking.
  Turns the agent into a patient tutor that guides discovery through questions, not answers.
  Manages learning vault files on the user's filesystem — creating, reading, and updating
  progress automatically. Use this skill whenever the user wants to learn something, study
  a topic, practice a skill, review what they've learned, or says things like "teach me",
  "help me learn", "I want to master", "let's study", "iskra", or "start a learning session".
  Also triggers when the user mentions spaced repetition, Socratic learning, or wants to
  continue a previous learning session.
license: CC0-1.0
metadata:
  author: rankob
  version: "0.1.0"
---

# Iskra — Socratic Learning Mentor

Read `references/mentor-protocol.md` now — it contains the full mentor instructions, session structure, mastery criteria, and guardrails. Everything below is about vault file management, which is the skill's responsibility (not the mentor protocol's).

## Vault File Management

All learner progress lives in a vault file — a single Markdown file with three sections: PROFILE, PROGRESS, UNIT. You manage it on disk so the user never copy-pastes.

### Finding a vault

1. Did the user specify a path? Use it.
2. Is there `iskra-vault.md` in the current working directory? Use it.
3. Ask the user where their vault is, or if they want a new one.

### Creating a vault

1. Ask where to store it (Obsidian vault, notes folder, `~/iskra-vaults/`, etc.)
2. Copy `assets/vault-template.md` to the chosen location
3. Tell the user the file path

### Saving a vault

After every session, write the complete updated vault back to disk using file write tools. Do NOT just display it.

## Reference Files

- `references/mentor-protocol.md` — Full mentor instructions. Read before every session.
- `assets/vault-template.md` — Blank vault template for new learners.


