# 🧮 Data Structures & Algorithms

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Status** | ✅ Complete |
| **Track** | Core |
| **Prerequisites** | Basic programming in one language (variables, loops, functions, recursion syntax) |
| **Feeds into** | [LLD](../03-system-design/lld.md) · [HLD](../03-system-design/hld.md) · [Interview Prep](../00-meta/interview-preparation.md) |
| **Modules** | 15 &nbsp;→&nbsp; 🟢 × 9 · 🟡 × 4 · 🔴 × 2 |

> **Legend** — Levels: 🟢 Fresher (0–1y) · 🟡 Mid (2–5y) · 🔴 Senior (5+y) &nbsp;•&nbsp; In each module: 📚 Topics · 🧩 Exercises · 🛠️ Project · 🎯 Interview

> 📌 **Targeting Tier-2/3 companies or startups?** Start with the focused [Tier-2/3 Question Bank](dsa/foundations/06-core-problems-tier2-3.md) — 111 highest-probability questions (arrays, strings, hashing & linear DS) those rounds actually ask.
> 🎯 **Cracking Tier-1 / MAANG?** Do the [foundations](dsa/foundations/) first (incl. [Recursion & D&C](dsa/foundations/05-recursion-divide-conquer.md)), then work the pattern banks **in sequence**: **1** [Arrays](dsa/tier1-patterns/01-arrays.md) (90) → **2** [Strings](dsa/tier1-patterns/02-strings.md) (72) → **3** [Linked List](dsa/tier1-patterns/03-linked-list.md) (46) → **4** [Stacks & Queues](dsa/tier1-patterns/04-stacks-queues.md) (37) → **5** [Trees](dsa/tier1-patterns/05-trees.md) (80) → **6** [Heaps](dsa/tier1-patterns/06-heaps.md) (35) → **7** [Graphs](dsa/tier1-patterns/07-graphs.md) (70) → **8** [Backtracking](dsa/tier1-patterns/08-backtracking.md) (45) → **9** [Dynamic Programming](dsa/tier1-patterns/09-dynamic-programming.md) (90).

---

## 🗺️ Overview

> The problem-solving spine for every engineering interview. Builds the ability to pick the
> right data structure, reason about time/space complexity, and recognize the pattern behind a
> problem. **Practice is continuous** — do problems weekly, not in one burst.

## 🎚️ Level Map — Definition of Done

| Level | The bar | Modules |
|:---:|---|---|
| 🟢 **Fresher** | Comfortable with easy / easy-medium problems; can explain the Big-O of your own code; know when to reach for a hash map, stack, or two pointers. | M0 – M8 |
| 🟡 **Mid** | Solve medium problems reliably under time pressure; recognize common patterns; reason about trade-offs between two correct approaches. | + M9 – M12 |
| 🔴 **Senior** | Dissect hard problems, optimize across time/space, derive non-obvious solutions from first principles, and communicate trade-offs clearly. | + M13 – M14 |

## 📇 Module Index

| # | Module | Lvl | Focus |
|:--|:--|:--:|:--|
| [M0](#m0) | Complexity & Analysis | 🟢 | Big-O, recurrences, trade-offs |
| [M1](#m1) | Arrays & Strings | 🟢 | Traversal, prefix sums, matrices |
| [M2](#m2) | Hashing | 🟢 | Maps/sets, frequency, one-pass |
| [M3](#m3) | Two Pointers & Sliding Window | 🟢 | Windows, opposite/same-direction pointers |
| [M4](#m4) | Stacks & Queues | 🟢 | Monotonic stack, parsing, deque |
| [M5](#m5) | Linked Lists | 🟢 | Reversal, cycles, LRU building block |
| [M6](#m6) | Recursion & Backtracking | 🟢 | Subsets/permutations, pruning |
| [M7](#m7) | Sorting & Searching | 🟢 | Binary search on the answer, custom sorts |
| [M8](#m8) | Trees & BST | 🟢 | Traversals, BST invariants, LCA |
| [M9](#m9) | Heaps & Priority Queues | 🟡 | Top-K, streaming median, k-way merge |
| [M10](#m10) | Graphs | 🟡 | BFS/DFS, topo sort, Dijkstra, union-find |
| [M11](#m11) | Greedy | 🟡 | Intervals, exchange argument |
| [M12](#m12) | Dynamic Programming | 🟡 | State design, knapsack, subsequences |
| [M13](#m13) | Tries & String Algorithms | 🔴 | Trie, KMP, rolling hash |
| [M14](#m14) | Advanced Structures | 🔴 | Union-find, segment/Fenwick, bitmask |

---

## Modules

<a id="m0"></a>
### M0 · Complexity & Analysis &nbsp;`🟢`
> **Focus:** Reason about cost *before* you optimize.

**📚 Topics**
- [ ] Big-O / Big-Θ / Big-Ω, best / avg / worst case
- [ ] Time vs space complexity; amortized analysis
- [ ] Complexity of common operations per data structure
- [ ] Recursion cost: recurrence relations, call-stack space

**🧩 Exercises**
- Annotate 10 of your past solutions with their time/space complexity and justify each.
- Given 5 code snippets, rank them by asymptotic growth.

**🛠️ Mini-project — assignment**
- Build a "complexity cheat-sheet" table (ops × structures) from memory, then verify it.

**🎯 Interview pointers**
- "What's the complexity of this?" · optimizing a brute force · space–time trade-off framing.

---

<a id="m1"></a>
### M1 · Arrays & Strings &nbsp;`🟢`
> **Focus:** In-place work and sub-array / sub-string reasoning.

**📚 Topics**
- [ ] Traversal, in-place mutation, prefix sums
- [ ] String manipulation, immutability, char frequency
- [ ] Matrix traversal (rotation, spiral, transpose)

**🧩 Exercises**
- Prefix-sum range queries; in-place array transforms; anagram grouping.

**🛠️ Mini-project — assignment**
- CLI text-analytics tool: word/char frequency, top-K words, palindrome detector.

**🎯 Interview pointers**
- Sub-array / sub-string problems · in-place with O(1) space · matrix manipulation.

---

<a id="m2"></a>
### M2 · Hashing &nbsp;`🟢`
> **Focus:** Trade space for time with maps and sets.

**📚 Topics**
- [ ] Hash maps & sets: operations, collisions, load factor
- [ ] Frequency counting, de-duplication, grouping
- [ ] Trade-offs vs sorted structures

**🧩 Exercises**
- Two-sum family; first unique element; group anagrams; subarray-sum-equals-K.

**🛠️ Mini-project — assignment**
- Implement a hash map from scratch (chaining + resizing) and benchmark vs the built-in.

**🎯 Interview pointers**
- "Can you do it in one pass?" · space-for-time trade with a map.

---

<a id="m3"></a>
### M3 · Two Pointers & Sliding Window &nbsp;`🟢`
> **Focus:** Turn nested loops into a single linear scan.

**📚 Topics**
- [ ] Opposite-end & same-direction pointers
- [ ] Fixed and variable-size sliding windows
- [ ] Fast / slow pointers

**🧩 Exercises**
- Container-with-most-water style; longest-substring-without-repeats; window max/min.

**🛠️ Mini-project — assignment**
- Rate-limiter simulation using a sliding window over a timestamp stream.

**🎯 Interview pointers**
- Recognizing when sorting + two pointers beats nested loops.

---

<a id="m4"></a>
### M4 · Stacks & Queues &nbsp;`🟢`
> **Focus:** The monotonic-stack pattern and expression parsing.

**📚 Topics**
- [ ] Stack, queue, deque; monotonic stack / queue
- [ ] Expression evaluation & parsing
- [ ] Queue via stacks / stack via queues

**🧩 Exercises**
- Valid parentheses; next-greater-element; min-stack; sliding-window-maximum (deque).

**🛠️ Mini-project — assignment**
- Expression evaluator (infix → postfix → evaluate) supporting `+ − × ÷` and parentheses.

**🎯 Interview pointers**
- Monotonic stack pattern · "nearest greater / smaller" family.

---

<a id="m5"></a>
### M5 · Linked Lists &nbsp;`🟢`
> **Focus:** Pointer manipulation without extra space.

**📚 Topics**
- [ ] Singly / doubly lists; dummy-head technique
- [ ] Reversal, cycle detection, merge, reorder
- [ ] Fast / slow pointer applications

**🧩 Exercises**
- Reverse in groups; detect & remove cycle; merge K sorted lists; LRU building block.

**🛠️ Mini-project — assignment**
- Implement an LRU cache (doubly linked list + hash map) with O(1) get / put.

**🎯 Interview pointers**
- Pointer manipulation without extra space · cycle problems.

---

<a id="m6"></a>
### M6 · Recursion & Backtracking &nbsp;`🟢`
> **Focus:** Enumerate a search space, then prune it.

**📚 Topics**
- [ ] Recursion patterns, base / recursive cases, state restore
- [ ] Subsets, permutations, combinations
- [ ] Pruning & constraint propagation

**🧩 Exercises**
- Generate subsets / permutations; N-Queens; word search; combination sum.

**🛠️ Mini-project — assignment**
- Sudoku solver with backtracking + constraint pruning; report nodes explored.

**🎯 Interview pointers**
- "Enumerate all …" problems · recursion-tree reasoning · when to prune.

---

<a id="m7"></a>
### M7 · Sorting & Searching &nbsp;`🟢`
> **Focus:** Binary search on any monotonic predicate.

**📚 Topics**
- [ ] Comparison sorts (merge, quick, heap) & stability
- [ ] Binary search + "binary search on the answer"
- [ ] Non-comparison sorts (counting, radix) — when valid

**🧩 Exercises**
- Implement merge & quicksort; search in rotated array; find peak; k-th smallest.

**🛠️ Mini-project — assignment**
- Sorting visualizer (data only): instrument comparisons / swaps and compare algorithms.

**🎯 Interview pointers**
- Binary search on monotonic predicates · custom comparators · partial sorting.

---

<a id="m8"></a>
### M8 · Trees & BST &nbsp;`🟢`
> **Focus:** Recursion over trees and BST invariants.

**📚 Topics**
- [ ] Traversals (pre / in / post / level), recursive & iterative
- [ ] BST properties, insert / delete / search
- [ ] Height, diameter, LCA, path problems

**🧩 Exercises**
- Level-order; validate BST; LCA; serialize / deserialize a tree.

**🛠️ Mini-project — assignment**
- Build a BST-backed ordered map with range queries; add self-balancing as a stretch goal.

**🎯 Interview pointers**
- Recursion over trees · BST invariants · traversal-order reconstruction.

---

<a id="m9"></a>
### M9 · Heaps & Priority Queues &nbsp;`🟡`
> **Focus:** "Top / smallest K" and streaming problems.

**📚 Topics**
- [ ] Binary heap: sift-up / down, build-heap
- [ ] Top-K, streaming median (two heaps)
- [ ] k-way merge

**🧩 Exercises**
- Top-K frequent; median of a data stream; merge k sorted streams.

**🛠️ Mini-project — assignment**
- Task scheduler using a priority queue with priorities + cooldowns.

**🎯 Interview pointers**
- "Top / smallest K" · streaming problems · heap vs sort trade-off.

---

<a id="m10"></a>
### M10 · Graphs &nbsp;`🟡`
> **Focus:** Model the problem as a graph, then pick the traversal.

**📚 Topics**
- [ ] Representations (adjacency list / matrix); BFS / DFS
- [ ] Topological sort; cycle detection (directed / undirected)
- [ ] Shortest paths (Dijkstra, Bellman-Ford, 0-1 BFS); Union-Find
- [ ] MST (Kruskal / Prim) — intro

**🧩 Exercises**
- Number of islands; course schedule; word ladder; network delay time.

**🛠️ Mini-project — assignment**
- Route planner over a city grid / graph: shortest path + alternate routes, with metrics.

**🎯 Interview pointers**
- Modeling a problem as a graph · picking BFS vs Dijkstra · connectivity via Union-Find.

---

<a id="m11"></a>
### M11 · Greedy &nbsp;`🟡`
> **Focus:** Know *when* greedy is provably correct.

**📚 Topics**
- [ ] Exchange-argument intuition; when greedy is provably correct
- [ ] Interval scheduling & merging
- [ ] Heap-assisted greedy

**🧩 Exercises**
- Merge intervals; non-overlapping intervals; jump game; task assignment.

**🛠️ Mini-project — assignment**
- Meeting-room allocator: minimize rooms for a set of intervals; justify the greedy choice.

**🎯 Interview pointers**
- Proving / knowing greedy correctness · counterexamples where greedy fails.

---

<a id="m12"></a>
### M12 · Dynamic Programming &nbsp;`🟡`
> **Focus:** Define state + transition for a new problem unaided.

**📚 Topics**
- [ ] Memoization vs tabulation; state design
- [ ] 1-D DP (climbing / house-robber), 2-D DP (grid / edit-distance)
- [ ] Knapsack family; subsequence DP (LIS, LCS)
- [ ] Interval DP intro

**🧩 Exercises**
- Coin change; edit distance; LIS in O(n log n); 0/1 knapsack; word break.

**🛠️ Mini-project — assignment**
- Diff tool core: compute LCS / edit-distance between two files and print an alignment.

**🎯 Interview pointers**
- Defining state + transition · recognizing overlapping subproblems · space optimization.

---

<a id="m13"></a>
### M13 · Tries & String Algorithms &nbsp;`🔴`
> **Focus:** Prefix problems and efficient substring search.

**📚 Topics**
- [ ] Trie: insert / search / prefix; compressed tries (intro)
- [ ] Pattern matching: KMP, Rabin-Karp, Z-algorithm
- [ ] Suffix structures (intro)

**🧩 Exercises**
- Implement a trie; word-search II; substring search with KMP; longest repeated substring.

**🛠️ Mini-project — assignment**
- Autocomplete engine: trie-backed prefix search with ranking by frequency.

**🎯 Interview pointers**
- Prefix problems → trie · efficient substring search · rolling hash.

---

<a id="m14"></a>
### M14 · Advanced Structures &nbsp;`🔴`
> **Focus:** Range queries, connectivity, and bitmask state.

**📚 Topics**
- [ ] Union-Find with path compression + union by rank
- [ ] Segment tree / Fenwick (BIT) for range queries + updates
- [ ] Bit manipulation: masks, subsets, tricks
- [ ] Advanced graph (bridges / articulation, max-flow intuition) — awareness

**🧩 Exercises**
- Range-sum / min with updates; count inversions (BIT); bitmask DP; redundant connection.

**🛠️ Mini-project — assignment**
- Range-query engine supporting sum / min / max with point + range updates; benchmark structures.

**🎯 Interview pointers**
- Range-query trade-offs · bitmask state compression · Union-Find for connectivity.

---

## 🏆 Capstone Projects

> **🥈 Capstone A — "Algorithm Playground"** &nbsp;`🟡`
> A data-only engine to run, instrument, and compare implementations across modules
> (counts of ops, time, space).
> - **Acceptance:** covers ≥ 6 modules · reports metrics · includes a written pattern index.

> **🥇 Capstone B — "Mini-LeetCode Grader"** &nbsp;`🔴`
> A harness that runs your solutions against test cases with time limits and reports the
> complexity class empirically.
> - **Acceptance:** supports custom test sets · timeouts · a per-problem pattern tag.

## ✅ Self-Assessment Checkpoints

- [ ] 🟢 I can state the time / space complexity of my own solution and defend it.
- [ ] 🟢 I reach for the right structure (map / stack / two-pointers) without trial and error.
- [ ] 🟡 I solve a random medium in ~25 min and explain trade-offs between two approaches.
- [ ] 🟡 I can design DP state + transition for a new problem unaided.
- [ ] 🔴 I dissect a hard problem, find a non-obvious optimization, and communicate it clearly.

## 🎤 Interview Question Bank — *pointers*

- **Patterns to drill** — two pointers · sliding window · fast / slow · monotonic stack ·
  BFS / DFS · topological sort · binary search on answer · backtracking ·
  DP (1-D / 2-D / knapsack / subsequence) · union-find · heap / top-K · trie · intervals / greedy · bitmask.
- **By round type** — phone screen (easy-medium, 1–2 problems) · onsite coding (medium-hard) ·
  "optimize the brute force" follow-ups · communication + edge-case handling.
- **The loop** — clarify → examples → brute force → optimize → code → test → complexity.
