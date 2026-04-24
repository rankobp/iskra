# v0.1 Design Spec — Iskra Core Prompt + Learning Vault

**Date:** 2026-04-24
**Status:** Approved

## Goal

Ship the minimum viable Iskra protocol: one core prompt + one vault template file that turns any LLM chat into a Socratic learning mentor with spaced repetition and mastery tracking.

## Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Prompt architecture | Single monolithic prompt | Simplest for v0.1 — one copy-paste |
| Spaced repetition | Fixed intervals: 1d → 3d → 7d → 14d → 30d → Mastered | No algorithm complexity, prompt-friendly |
| Mastery model | 3-level: New → Learning → Mastered | Clear, unambiguous |
| Vault format | Single file, clearly sectioned | Low friction (one paste), easy to split later |
| Mastery verification | Demonstrate first, explain second | Apply > Explain > Distinguish |

## Artifacts

```
iskra/
├── prompt/
│   └── core-prompt.md        # The system prompt
├── vault/
│   └── iskra-vault.md        # Template (profile + progress + unit sections)
└── README.md                 # Updated with quick-start
```

## Core Prompt Design

The prompt instructs the AI to:

1. **Adopt the mentor role** — never lecture first, always ask
2. **Parse the vault file** — recognize PROFILE / PROGRESS / UNIT sections
3. **Run onboarding** if profile is empty — interview the learner about goals, constraints, background
4. **Generate or adopt a unit** if none exists — break topic into daily-sized micro-concepts
5. **Execute the session cycle:**
   - Retrieval warm-up (concepts due for review)
   - Socratic diagnostic (current concept)
   - Mastery decision (promote / hold / demote)
   - Output updated vault file
6. **Enforce mastery criteria** — prefer application tasks over verbal explanation when concept allows it
7. **Maintain SR schedule** — advance interval on success, reset to 1d on struggle

## Vault File Structure

Single file with three clearly delimited sections:

```
---
## ISKRA PROFILE
---
[goal, motivation, background, constraints, daily time budget]

---
## ISKRA PROGRESS
---
[mastery map with status/interval/next-review per concept]
[session log]

---
## ISKRA UNIT (optional)
---
[structured curriculum outline]
```

Section delimiters are `---\n## ISKRA <SECTION>\n---` — easy to parse programmatically for future splitting.

## Mastery Criteria

AI selects the highest-fidelity test applicable:

1. **Apply** — Learner performs a novel task using the concept. Preferred for skills, tools, procedures.
2. **Explain** — Learner articulates in own words. Used for principles, theory, conceptual knowledge.
3. **Distinguish** — Learner differentiates from related learned concepts.

Concept advances when learner passes the test. If they struggle, concept resets to 1d interval.

## Session Flow

```
User: pastes core-prompt.md + iskra-vault.md
  ↓
AI: recognizes session, checks PROGRESS for due reviews
  ↓
1. Retrieval warm-up — review concepts where next-review ≤ today
2. Socratic diagnostic — probe current concept, give application tasks
3. Mastery decision — update status and interval
4. Output — AI returns complete updated iskra-vault.md
  ↓
User: copies updated file back to vault folder
```

## Out of Scope for v0.1

- Multi-language support
- App / plugin / skill integration
- Curriculum library
- Gamification / streaks
- Multi-file vault option (designed for easy split later)
