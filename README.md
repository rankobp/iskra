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

Iskra is a **daily micro‑session protocol** you follow with any AI chat (ChatGPT, Claude, Llama, etc.). Every session follows the same cycle:

1. **You paste** your `profile.md`, `progress.md`, and the **Iskra Core Prompt** into the chat.
2. The AI adopts the role of a Socratic mentor.
3. **Session unfolds:**
   - **Retrieval warm‑up** — Reviewing concepts you’re about to forget, using spaced repetition.
   - **Socratic diagnostic** — Probing your understanding of the current micro‑concept, scaffolding when you’re stuck, and checking for mastery.
   - **Mastery decision** — Marking a concept as truly mastered, or scheduling further practice.
4. The AI **outputs updated Markdown files**. You copy them back into your learning vault.

No plugins, no special editors — just text and conversation.

---

## 📂 The learning vault

Your vault contains three simple files:

| File | Purpose |
|------|---------|
| `profile.md` | Your long‑term goal, motivation, background, and current focus. |
| `progress.md` | Mastery map, spaced‑repetition queue, and session log. |
| `unit.md` *(optional)* | A structured outline of the concepts you want to master, broken into daily‑sized pieces. |

Every detail is human‑readable, diff‑friendly, and version‑control ready.

---

## 🚀 Quick start (v0.1)

1. **Create your vault** — a folder on your computer with the three files above (even empty `progress.md` is fine).
2. **Copy the Iskra Core Prompt** into your AI chat’s system instructions (or paste it at the start of your first conversation).
3. **Start your first session** by pasting the contents of your vault. The AI will guide you through a friendly interview to bootstrap your `profile.md`, and your learning journey begins.
4. **Repeat daily** — paste your updated files, and the AI picks up exactly where you left off.

> The complete `v0.1` protocol specification, including the core prompt wording, mastery criteria, and spaced‑repetition details, is coming soon.

---

## ✨ Why “Iskra”?

Because a single, well‑placed spark can ignite a fire of understanding that lasts a lifetime. The framework’s job is not to fill a bucket, but to kindle that spark.

---

## 🤝 Contribute

Iskra is in its earliest days. We’re designing the protocol **from first principles** and welcome:

- Feedback on the Socratic cycle and scaffolding patterns
- Experiments with different spaced‑repetition algorithms
- Ideas for visualizing `progress.md`
- Testimonies from real learning sessions

Open an issue or a discussion — let’s build the mentor we wish we’d always had.

---

## 📜 License

This project and its protocol are dedicated to the public domain under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/).  
*Reason: Learning itself belongs to everyone.*
