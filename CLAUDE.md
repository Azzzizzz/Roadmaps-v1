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
- **Companion practice** for a roadmap lives in a `<topic>/` folder beside it (e.g. `dsa/`), with a
  `README.md` guided path. Curated question lists with tags + example `input → output` — **never solutions**.

## DSA practice (`roadmaps/01-foundations/dsa/`)

The DSA topic = the roadmap (`dsa.md`) + a **staged practice area** under `dsa/`, front-doored by
[`dsa/README.md`](roadmaps/01-foundations/dsa/README.md). Two folders enforce the sequence:

### `dsa/foundations/` — Stage 0, do first, in order
`01-programming-foundations` · `02-complexity-analysis` · `03-mathematics` · `04-bit-manipulation` ·
`05-recursion-divide-conquer` · `06-core-problems-tier2-3`.
- `05` is the **recursion + divide-and-conquer** on-ramp to Backtracking/DP.
- `06` is the **structure-first, frequency-ranked Tier-2/3** breadth bank (sections = data structures;
  rows ranked by frequency with a ▶️ easy→hard practice-order column). For startups / service-based / mid MNCs.

### `dsa/tier1-patterns/` — Stage 1 (Tier-1 / MAANG), do after foundations
Files named `NN-topic.md` (the folder already says "tier-1 patterns" — no redundant suffix), numbered
in **learning sequence**: `01-arrays · 02-strings · 03-linked-list · 04-stacks-queues · 05-trees ·
06-heaps · 07-graphs · 08-backtracking · 09-dynamic-programming`. **Pattern-first:** sections are
algorithmic patterns, rows easy→hard, medium/hard skew.

### Tier-1 pattern-first rules
- **Two file kinds:** *structure files* (arrays…heaps) and *paradigm files* (dynamic-programming, backtracking).
- **One home per problem. Classify — ask in order:** (1) core skill is DP/backtracking → paradigm file;
  (2) manipulates a specific structure (LL/tree/graph/heap) → that structure's file; (3) else → arrays/strings by input.
- **Classify by the skill tested, not the helper DS used** (monotonic-stack-on-array → arrays).
- **Techniques stay as sections, not files:** binary search, two pointers, sliding window, greedy, prefix sum, bit manipulation.
- **Anti-duplication:** one home file; elsewhere a one-line "see also" link, never a copy. (String DP &
  string backtracking live in the paradigm files; `02-strings.md` cross-links to them.)
- **Every file opens with a "how to use / why pattern-first" block**, then a 🧭 Pattern Index
  (🔍 recognize-cues + jump links); each section = recognize-cue + easy→hard table (`# · Question · Diff · example in→out · Freq`).
- **After any move/rename, run a link-checker** over all `.md` before committing.

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
