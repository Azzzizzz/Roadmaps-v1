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
- **Companion question banks** live in a `<topic>-practice/` folder beside the roadmap
  (e.g. `dsa-practice/linear-ds-tier2-3.md`). They are curated question lists with tags +
  example `input → output` — **never solutions**. Name as `<scope>-<tier>.md`.

## DSA practice banks (two styles)

Both live in `roadmaps/01-foundations/dsa-practice/`:

1. **Structure-first, frequency-ranked (Tier-2/3)** — `linear-ds-tier2-3.md`. Sections are data
   structures; rows ranked by interview frequency with a ▶️ easy→hard practice-order column.
   For **foundations / breadth** (startups, service-based, mid MNCs). *Keep as-is.*
2. **Pattern-first (Tier-1 / MAANG)** — `<topic>-patterns-tier1.md`. Sections are algorithmic
   patterns; rows ordered **easy→hard**, medium/hard skew. For **interview pattern-recognition**.

### Tier-1 pattern-first rules
- **Two file kinds:** *structure files* (arrays, strings, linked-list, stacks-queues, trees,
  graphs, heaps) and *paradigm files* (dynamic-programming, backtracking).
- **One home per problem. Classification — ask in order:**
  1. Core skill is DP or backtracking → **paradigm file**.
  2. Manipulates a specific structure (LL / tree / graph / heap) → **that structure's file**.
  3. Else → **arrays or strings** by input, grouped by the technique-pattern.
- **Classify by the skill tested, not the helper DS used** (monotonic-stack-on-array → arrays).
- **Techniques stay as sections, not files:** binary search, two pointers, sliding window,
  greedy, prefix sum, bit manipulation (input is always a concrete array/string).
- **Anti-duplication:** one home file; elsewhere use a one-line "see also" link, never a copy.
- **Every file opens with a "how to use / why pattern-first" block**, then a 🧭 Pattern Index
  (🔍 recognize-cues + jump links); each section = recognize-cue + easy→hard table
  (`# · Question · Diff · example in→out · Freq`).
- **Build order (foundations-first):** linked-list → stacks-queues → trees → graphs → heaps → dp → backtracking.
- When the DP & Backtracking paradigm files are built, the existing "DP on Strings" / "Backtracking"
  sections in `02-strings.md` become **cross-links** to them (no duplication).

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
