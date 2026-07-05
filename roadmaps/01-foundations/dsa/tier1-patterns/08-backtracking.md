# 🎯 Backtracking — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../../dsa.md) · [Strings](02-strings.md) · [Dynamic Programming](09-dynamic-programming.md) |
| **Status** | ✅ Complete — Backtracking (9th & final in the Tier-1 pattern series) |
| **Kind** | **Paradigm file** (pattern-organized, spans all input types) |
| **Scope** | Backtracking, organized by **sub-pattern**, Tier-1 / MAANG |
| **Coverage** | 5 patterns · 45 questions |
| **Canonical home for** | **String backtracking** — the [Strings bank](02-strings.md#p7) cross-links here |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why a paradigm file?** Like DP, backtracking isn't tied to one data structure — it enumerates
solutions over arrays, strings, grids, and numbers. So it gets its **own** file and is the canonical
home for backtracking problems that also surface elsewhere (the Strings bank points here).

**The backtracking method — one loop, three questions:**
> **choose → explore → un-choose** (DFS over partial solutions).
1. **Choice** — what are the options at this step?
2. **Prune** — when is a partial solution already invalid? (cut early — this is where the speed is)
3. **Goal** — when is a solution complete? (record it)

Reach for backtracking when a problem says *"find all / generate all / does any arrangement satisfy…"*
and brute force is exponential but **pruning** makes it tractable.

**Backtracking vs DP:** backtracking *enumerates*; if subproblems overlap and you only need a
count or an optimum, **memoize** and it becomes [DP](09-dynamic-programming.md).

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the example only confirms you understood the question. Goal:
**name the pattern and state the choice/prune/goal in under 60 seconds** on a new problem.

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> **Templates to internalize:** a `start` index for combinations (avoids reordering dups) · `sort + skip equal siblings` for the "II" (duplicate) variants · always **un-choose** (restore state) after recursing.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Subsets & Combinations](#p1) | 10 | enumerate subsets/combinations (order doesn't matter) — "choose or skip" with a `start` index |
| 2 | [Permutations](#p2) | 7 | enumerate all orderings (order matters) — track used elements |
| 3 | [Grid / Board Backtracking](#p3) | 9 | place items on a board / walk a grid, backtracking on failure (N-Queens, Sudoku, word search) |
| 4 | [Partitioning](#p4) | 9 | split a sequence/set into valid groups — try each cut/assignment |
| 5 | [Combinatorial Enumeration & Constraints](#p5) | 10 | build valid strings/sequences under constraints, pruning aggressively |

---

<a id="p1"></a>
## 1 · Subsets & Combinations (10)

> 🔍 **Recognize it when…** you enumerate all subsets or combinations (order doesn't matter). Use a
> `start` index so you never revisit earlier elements; for duplicates, sort and skip equal siblings.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Subsets | 🟡 | `[1,2,3] → [[],[1],[2],[3],[1,2],[1,3],[2,3],[1,2,3]]` | ⭐⭐⭐ |
| 2 | Subsets II (with duplicates) | 🟡 | `[1,2,2] → [[],[1],[1,2],[1,2,2],[2],[2,2]]` | ⭐⭐⭐ |
| 3 | Combinations | 🟡 | `n=4, k=2 → [[1,2],[1,3],[1,4],[2,3],[2,4],[3,4]]` | ⭐⭐⭐ |
| 4 | Combination Sum | 🟡 | `[2,3,6,7], target=7 → [[2,2,3],[7]]` | ⭐⭐⭐ |
| 5 | Combination Sum II (each once, dups) | 🟡 | `[10,1,2,7,6,1,5], target=8 → [[1,1,6],[1,2,5],[1,7],[2,6]]` | ⭐⭐⭐ |
| 6 | Letter Combinations of a Phone Number | 🟡 | `"23" → ["ad","ae","af","bd","be","bf","cd","ce","cf"]` | ⭐⭐⭐ |
| 7 | Combination Sum III (k numbers 1–9) | 🟡 | `k=3, n=7 → [[1,2,4]]` | ⭐⭐ |
| 8 | Factor Combinations | 🟡 | `12 → [[2,6],[2,2,3],[3,4]]` | ⭐⭐ |
| 9 | Letter Tile Possibilities | 🟡 | `"AAB" → 8` | ⭐⭐ |
| 10 | Count Number of Maximum Bitwise-OR Subsets | 🟡 | `[3,1] → 2` | ⭐ |

<a id="p2"></a>
## 2 · Permutations (7)

> 🔍 **Recognize it when…** you enumerate all orderings (order matters) — track which elements are
> already used; sort + skip for duplicates.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Letter Case Permutation | 🟢 | `"a1b2" → ["a1b2","a1B2","A1b2","A1B2"]` | ⭐⭐ |
| 2 | Permutations | 🟡 | `[1,2,3] → 6 orderings` | ⭐⭐⭐ |
| 3 | Permutations II (with duplicates) | 🟡 | `[1,1,2] → [[1,1,2],[1,2,1],[2,1,1]]` | ⭐⭐⭐ |
| 4 | String Permutations | 🟡 | `"abc" → [abc,acb,bac,bca,cab,cba]` | ⭐⭐ |
| 5 | Palindrome Permutation II | 🟡 | `"aabb" → ["abba","baab"]` | ⭐ |
| 6 | Beautiful Arrangement | 🟡 | `n=2 → 2` | ⭐⭐ |
| 7 | Permutation Sequence (kth) | 🔴 | `n=3, k=3 → "213"` | ⭐⭐ |

<a id="p3"></a>
## 3 · Grid / Board Backtracking (9)

> 🔍 **Recognize it when…** you place pieces on a board or walk a grid, trying options and backtracking
> on a dead end — the classic constraint puzzles.
> **See also:** Word Search & Word Search II also live in the [Strings bank](02-strings.md#p7).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Word Search | 🟡 | `board, "ABCCED" → true` | ⭐⭐⭐ |
| 2 | Path with Maximum Gold | 🟡 | `grid → 24` | ⭐⭐ |
| 3 | N-Queens | 🔴 | `n=4 → 2 distinct boards` | ⭐⭐⭐ |
| 4 | N-Queens II (count) | 🔴 | `n=4 → 2` | ⭐⭐ |
| 5 | Sudoku Solver | 🔴 | `board → solved board` | ⭐⭐⭐ |
| 6 | Unique Paths III (visit every empty cell) | 🔴 | `grid → 2` | ⭐⭐ |
| 7 | Word Search II (trie + backtracking) | 🔴 | `board, words → matched words` | ⭐⭐⭐ |
| 8 | Robot Room Cleaner | 🔴 | `→ clean the whole room` | ⭐⭐ |
| 9 | Word Squares | 🔴 | `["area","lead","wall","lady","ball"] → valid squares` | ⭐ |

<a id="p4"></a>
## 4 · Partitioning (9)

> 🔍 **Recognize it when…** you split a sequence or set into valid groups — try each cut point or
> bucket assignment and backtrack.
> **See also:** Palindrome Partitioning, Restore IP Addresses, Word Break II also in the [Strings bank](02-strings.md#p7).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Palindrome Partitioning | 🟡 | `"aab" → [["a","a","b"],["aa","b"]]` | ⭐⭐⭐ |
| 2 | Restore IP Addresses | 🟡 | `"25525511135" → ["255.255.11.135","255.255.111.35"]` | ⭐⭐ |
| 3 | Matchsticks to Square | 🟡 | `[1,1,2,2,2] → true` | ⭐⭐ |
| 4 | Additive Number | 🟡 | `"112358" → true` | ⭐⭐ |
| 5 | Split String Into Descending Consecutive Values | 🟡 | `"050043" → true` | ⭐ |
| 6 | Partition to K Equal Sum Subsets | 🔴 | `[4,3,2,3,5,2,1], k=4 → true` | ⭐⭐⭐ |
| 7 | Word Break II | 🔴 | `"catsanddog", dict → ["cats and dog","cat sand dog"]` | ⭐⭐ |
| 8 | Fair Distribution of Cookies | 🔴 | `[8,15,10,20,8], k=2 → 31` | ⭐⭐ |
| 9 | Maximum Number of Achievable Transfer Requests | 🔴 | `n, requests → max satisfiable` | ⭐ |

<a id="p5"></a>
## 5 · Combinatorial Enumeration & Constraints (10)

> 🔍 **Recognize it when…** you build valid strings/sequences under constraints and prune aggressively —
> count or list all.
> **See also:** Generate Parentheses & Expression Add Operators also in the [Strings bank](02-strings.md#p7).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Binary Watch | 🟢 | `turnedOn=1 → all valid times` | ⭐ |
| 2 | Generate Parentheses | 🟡 | `n=3 → ["((()))","(()())","(())()","()(())","()()()"]` | ⭐⭐⭐ |
| 3 | Gray Code | 🟡 | `n=2 → [0,1,3,2]` | ⭐⭐ |
| 4 | Find Unique Binary String | 🟡 | `["01","10"] → "11"` | ⭐⭐ |
| 5 | Numbers With Same Consecutive Differences | 🟡 | `n=3, k=7 → [181,292,707,818,929]` | ⭐ |
| 6 | Word Pattern II | 🟡 | `pattern="abab", s="redblueredblue" → true` | ⭐⭐ |
| 7 | Flip Game II | 🟡 | `"++++" → true` | ⭐ |
| 8 | Expression Add Operators | 🔴 | `"123", target=6 → ["1+2+3","1*2*3"]` | ⭐⭐ |
| 9 | Split Array into Fibonacci Sequence | 🔴 | `"123456579" → [123,456,579]` | ⭐ |
| 10 | Maximum Score Words Formed by Letters | 🔴 | `words, letters, score → 27` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] For a new problem I can state the **choice / prune / goal** and write the choose→explore→un-choose loop.
- [ ] I use a **`start` index** for combinations and **sort + skip duplicates** for the "II" variants by reflex.
- [ ] I always **restore state** (un-choose) after recursing, and I prune as early as possible.
- [ ] I know when to **memoize** and turn backtracking into DP.
- [ ] I've solved every 🟡 and attempted every 🔴 (N-Queens, Sudoku, partition-to-K, Expression Add Operators).

> **Series complete 🎉:** Arrays ✅ · Strings ✅ · Linked List ✅ · Stacks & Queues ✅ · Trees ✅ ·
> Graphs ✅ · Heaps ✅ · Dynamic Programming ✅ · Backtracking ✅.
