# CLAUDE.md — Rules & Conventions

This repo is a **collection of learning roadmaps in Markdown**. Each roadmap is a
skeleton/curriculum, **not** a textbook. The goal: take a learner from foundations to
advanced, structured so **fresher, mid, and senior interviews** can be cleared with strong
fundamentals, via **exercise- and project-based learning**.

Audience: **team / cohort curriculum** — consistency across files matters more than any one
file's flair.

---

## Golden rules

1. **Roadmaps are skeletons, not content.** Provide: topic checklists, exercise *prompts*,
   project *ideas*, and interview-topic *pointers*. Do **NOT** write tutorials, explanations,
   solutions, or answers. If you catch yourself teaching, stop.
2. **Every roadmap follows [`templates/ROADMAP-TEMPLATE.md`](templates/ROADMAP-TEMPLATE.md).**
   Same sections, same order, every time.
3. **Project-based is mandatory.** Every module has ≥1 exercise prompt. Every roadmap has ≥1
   capstone project. Mini-projects and capstones are framed as **assignments** (cohort use).
4. **One file per topic, segmented internally** by Fresher / Mid / Senior.
5. **Cross-link** related roadmaps with relative Markdown links (e.g. `[HLD](../03-system-design/hld.md)`).

## Level taxonomy (use these definitions everywhere)

- **🟢 Fresher (0–1 yr):** Knows the fundamentals; can implement the basics from scratch;
  understands core concepts and terminology; clears screening / entry-level rounds.
- **🟡 Mid (2–5 yr):** Applies concepts in real systems; reasons about trade-offs; owns
  features end-to-end; handles ambiguity and debugging under load.
- **🔴 Senior (5+ yr):** Deep trade-off judgment; designs at scale; mentors; drives
  architecture and cross-domain decisions; can dissect and communicate hard problems.

## Naming & structure

- Pillar folders are **numbered by dependency order**: `NN-pillar-name/`.
- Roadmap files are **kebab-case**, no number prefix: `dsa.md`, `distributed-systems.md`.
- Frontend and AI/ML are **parallel tracks** — numbered for placement, but can start after Foundations.

## Status markers (put in each file's header)

- `🚧 Stub` — created, not yet written
- `🔨 In progress`
- `✅ Complete` — follows the template fully, reviewed

## Progress convention

Use GitHub task checkboxes for learner-trackable items: `- [ ] topic` / `- [x] done`.

## Model workflow (how this repo gets built)

- **Opus** — taxonomy, this file, the template, and the hardest roadmaps
  (distributed-systems, hld, llm, databases). Get the pattern right here.
- **Sonnet** — mass-produce the remaining roadmaps by following the locked template.
- **Fable 5** — not used for technical curriculum structuring.

## Commits

- Small, per-roadmap commits. Message: `roadmap(<topic>): <what>` e.g. `roadmap(apis): add mid + senior modules`.
