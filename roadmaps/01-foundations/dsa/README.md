# 🧭 DSA — Guided Practice Path

> **Start here.** This is the ordered path from *"I know a programming language"* to *"I can clear a
> MAANG interview."* Do the stages **in sequence** — the folder names and file numbers *are* the sequence.

Companion to the [DSA roadmap](../dsa.md) (the *what to learn*). This README is the *what to practice, and in what order*.

---

## 🗺️ The path at a glance

```
STAGE 0 · FOUNDATIONS            (dsa/foundations/ — do first, in order)
   01 Programming Foundations
   02 Complexity Analysis
   03 Mathematics
   04 Bit Manipulation
   05 Recursion & Divide-and-Conquer     ← the recursion on-ramp
   06 Core Problems (Tier-2/3)           ← breadth: structure-first, frequency-ranked
              │
              ▼
STAGE 1 · TIER-1 PATTERNS        (dsa/tier1-patterns/ — MAANG, do after foundations)
   01 Arrays → 02 Strings → 03 Linked List → 04 Stacks & Queues
   → 05 Trees → 06 Heaps → 07 Graphs → 08 Backtracking → 09 Dynamic Programming
```

## 🎯 Pick your track

| Track | Who it's for | The plan |
|---|---|---|
| **Tier-2/3 & startups** | service-based cos, mid MNCs, early startups | Foundations **01–04**, then **06 Core Problems (Tier-2/3)**. *(05 Recursion recommended.)* |
| **Tier-1 / MAANG** | FAANG & top product companies | **Everything** — all of Stage 0, then all 9 Stage-1 pattern banks, in order. |

> Rounds at Tier-2/3 lean on **basics done fast** (arrays/strings/hashing). Tier-1 tests **pattern
> recognition on medium/hard problems**. Same fundamentals — different depth.

---

## 🧱 Stage 0 · Foundations

Do these before the pattern banks. Numbers are the order.

| # | File | What it builds | Status |
|:--:|---|---|:--:|
| 01 | [Programming Foundations](foundations/01-programming-foundations.md) | language basics, I/O, control flow, functions, OOP | ✅ |
| 02 | [Complexity Analysis](foundations/02-complexity-analysis.md) | Big-O, time/space, amortized, recurrences | ✅ |
| 03 | [Mathematics](foundations/03-mathematics.md) | number theory, modular arithmetic, combinatorics, probability | ✅ |
| 04 | [Bit Manipulation](foundations/04-bit-manipulation.md) | bitwise ops, masks, common tricks | ✅ |
| 05 | [Recursion & Divide-and-Conquer](foundations/05-recursion-divide-conquer.md) | recursion mechanics + D&C · **28 Qs** | ✅ |
| 06 | [Core Problems — Tier-2/3](foundations/06-core-problems-tier2-3.md) | breadth across arrays/strings/hashing/LL/stacks/queues, frequency-ranked, ▶️ easy→hard · **111 Qs** | ✅ |

## 🎯 Stage 1 · Tier-1 Patterns (MAANG)

Work these **in order** — each bank is ordered easy→hard inside, and later topics assume earlier ones.

| # | File | Patterns | Qs | Status |
|:--:|---|:--:|:--:|:--:|
| 01 | [Arrays](tier1-patterns/01-arrays.md) | 10 | 90 | ✅ |
| 02 | [Strings](tier1-patterns/02-strings.md) | 8 | 72 | ✅ |
| 03 | [Linked List](tier1-patterns/03-linked-list.md) | 6 | 46 | ✅ |
| 04 | [Stacks & Queues](tier1-patterns/04-stacks-queues.md) | 6 | 37 | ✅ |
| 05 | [Trees](tier1-patterns/05-trees.md) | 10 | 80 | ✅ |
| 06 | [Heaps](tier1-patterns/06-heaps.md) | 5 | 35 | ✅ |
| 07 | [Graphs](tier1-patterns/07-graphs.md) | 9 | 70 | ✅ |
| 08 | [Backtracking](tier1-patterns/08-backtracking.md) | 5 | 45 | ✅ |
| 09 | [Dynamic Programming](tier1-patterns/09-dynamic-programming.md) | 10 | 90 | ✅ |
| | **Total** | **69** | **565** | |

> **Why this order:** linear structures first (01–04) → non-linear (05 Trees, 06 Heaps, 07 Graphs) →
> paradigms last (08 Backtracking = recursion + search, 09 DP = backtracking + memoization). A heap is
> a tree, so it precedes Graphs (which needs it for Dijkstra). Recursion itself is in **foundations 05**.

---

## 🧠 How the pattern banks work

- **Pattern-first.** Problems are grouped by the *pattern that cracks them*, not as a flat list — because MAANG interviews are a pattern-recognition game.
- **🔍 Recognize-cues.** Every pattern opens with a "recognize it when…" line — the trigger you're training your brain to fire on.
- **Easy → hard.** Rows ramp 🟢 → 🟡 → 🔴, so you learn the template before stress-testing it.
- **Examples, not solutions.** Each row shows an `input → output` example to confirm you understood the *question* — you write the solution. (No solutions live here, by design.)
- **⭐ Frequency.** ⭐⭐⭐ = asked constantly · ⭐⭐ common · ⭐ occasional. Short on time? Clear every ⭐⭐⭐ first.
- **One home per problem.** A problem lives in exactly one file; related files link to it, never copy it.

## ✅ How to work it

1. **Foundations in order** (01 → 06). Don't skip Complexity or Recursion — everything leans on them.
2. **Then patterns in order** (01 → 09). Per pattern: read the recognize-cue → solve easy→hard **from the prompt**.
3. **Before a specific interview:** drill by frequency — hit every ⭐⭐⭐ across the relevant banks.
4. Track progress with the checkboxes below.

## 📊 Progress

**Stage 0 · Foundations**
- [ ] 01 Programming Foundations
- [ ] 02 Complexity Analysis
- [ ] 03 Mathematics
- [ ] 04 Bit Manipulation
- [ ] 05 Recursion & Divide-and-Conquer
- [ ] 06 Core Problems (Tier-2/3)

**Stage 1 · Tier-1 Patterns**
- [ ] 01 Arrays
- [ ] 02 Strings
- [ ] 03 Linked List
- [ ] 04 Stacks & Queues
- [ ] 05 Trees
- [ ] 06 Heaps
- [ ] 07 Graphs
- [ ] 08 Backtracking
- [ ] 09 Dynamic Programming

---

*704 curated questions across this area (565 Tier-1 patterns · 111 Tier-2/3 · 28 Recursion & D&C). Examples show intent, never solutions.*
