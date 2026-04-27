# Iskra ✦

**An open-source, AI-assisted learning framework that sparks deep understanding.**

> *AI as a mentor, never a shortcut.*

Iskra (Slavic for “spark”) is a **protocol for learning** that combines the power of large language models with decades of research in cognitive psychology and pedagogy. It turns any AI chat into a patient, Socratic mentor that guides you from shallow familiarity to true mastery — one 5‑to‑15‑minute session per day.

---

## 🌱 Core philosophy

Most AI‑learning tools give answers. Iskra gives questions.

- **AI as a mentor, not an oracle** — The AI never lectures first. It asks, listens, and scaffolds your thinking. You build understanding; the AI guards the path.
- **Mastery over completion** — A concept is only “learned” when you can explain it in your own words and apply it to a new situation. No skipping ahead.
- **Plain Markdown as source of truth** — Your knowledge, progress, and spaced‑repetition schedule live in simple Markdown files that you own forever. No proprietary format, no lock‑in.
- **Psychology‑first** — Spaced repetition, retrieval practice, scaffolding, and motivation support are wired into the protocol, not bolted on as an afterthought.

---

## 🧠 How it works

Iskra is a **daily micro‑session protocol** you follow with any AI chat (DeepSeek, Z.AI, Qwen, ChatGPT, Claude, LM-Studio, Llama, etc.). Every session follows the same cycle:

1. **You paste** the **Iskra Core Prompt** and your **vault file** into the chat.
2. The AI adopts the role of a Socratic mentor.
3. **Session unfolds:**
   - **Retrieval warm‑up** — Reviewing concepts you're about to forget, using spaced repetition (1d → 3d → 7d → 14d → 30d → Mastered).
   - **Socratic diagnostic** — Probing your understanding through tasks and questions. The mentor prefers **doing over explaining** — you'll apply concepts to novel situations whenever possible.
   - **Mastery decision** — Promoting, holding, or resetting concepts based on your demonstrated understanding.
4. The AI **outputs your updated vault file**. You copy it back. Done.

No plugins, no special editors — just text and conversation.

---

## 📂 The learning vault

Your vault is a **single Markdown file** (`iskra-vault.md`) with three clearly separated sections:

| Section | Purpose |
|---------|---------|
| **PROFILE** | Your goal, motivation, background, constraints, and daily time budget. |
| **PROGRESS** | Mastery map (concept status + spaced‑repetition schedule) and session log. |
| **UNIT** *(optional)* | A structured outline of the concepts you want to master, broken into daily‑sized pieces. |

Every detail is human‑readable, diff‑friendly, and version‑control ready. Sections are clearly delimited so the vault can be split into separate files at any time.

---

## 🚀 Quick start (v0.1)

**Option A — All-in-one (simplest):** Grab [`vault/iskra-all-in-one.md`](vault/iskra-all-in-one.md). Paste the entire file into any AI chat. Done — one file, one paste.

**Option B — Prompt + vault (for repeat sessions):** Grab [`prompt/core-prompt.md`](prompt/core-prompt.md) and [`vault/iskra-vault.md`](vault/iskra-vault.md). Set the core prompt as your chat's system instructions (paste it once), then paste only the vault file each session.

Either way, the mentor interviews you about your goals, generates a personalized curriculum, and your learning journey begins. Repeat daily — paste your updated file, and the mentor picks up exactly where you left off.

### Mastery criteria

A concept reaches **Mastered** when you:
1. Demonstrate long‑term retention (pass review at 30‑day interval)
2. **Apply** it to a novel situation (for practical skills) OR **explain** it clearly and distinguish it from related concepts (for theory)
3. Do so without scaffolding — no hints, no leading questions

---

## Agent Skill

If you use an AI coding agent (Claude Code, Cursor, etc.) with [skills support](https://agentskills.io/), you can install Iskra as a skill. The agent will automatically manage your vault files on disk — no copy-pasting needed.

```bash
npx skills add https://github.com/rankobp/iskra --skill iskra
```

Once installed, just tell your agent "I want to learn X" or "start an Iskra session" and it handles the rest.

---

## ✨ Why “Iskra”?

Because a single, well‑placed spark can ignite a fire of understanding that lasts a lifetime. The framework’s job is not to fill a bucket, but to kindle that spark.

---

## 🤝 Contribute

Iskra is in its earliest days. We’re designing the protocol **from first principles** and welcome:

- Feedback on the Socratic cycle and scaffolding patterns
- Experiments with different spaced‑repetition algorithms
- Ideas for visualizing progress
- Pre‑built unit outlines for popular topics
- Testimonies from real learning sessions

Open an issue or a discussion — let’s build the mentor we wish we’d always had.

---

## 📜 License

This project and its protocol are dedicated to the public domain under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/).  
*Reason: Learning itself belongs to everyone.*
