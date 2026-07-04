# Data Structures & Algorithms Roadmap

> **Pillar:** 01-foundations · **Status:** ✅ Complete · **Track:** Core
> **Prerequisites:** Basic programming in one language (variables, loops, functions, recursion syntax)
> **Feeds into:** [LLD](../03-system-design/lld.md) , [HLD](../03-system-design/hld.md) , [Interview Preparation](../00-meta/interview-preparation.md)

## Overview
The problem-solving spine for every engineering interview. Builds the ability to pick the
right data structure, reason about time/space complexity, and recognize the pattern behind a
problem. Practice is continuous — do problems weekly, not in one burst.

## Level Map (Definition of Done)

- **🟢 Fresher** — Complexity analysis + M1–M8. Comfortable with easy and easy-medium problems;
  can explain Big-O of your own code; knows when to reach for a hash map, stack, or two pointers.
- **🟡 Mid** — Adds M9–M12. Solves medium problems reliably under time pressure; recognizes
  common patterns; can reason about trade-offs between two correct approaches.
- **🔴 Senior** — Adds M13–M14. Dissects hard problems, optimizes across time/space, communicates
  approach and trade-offs clearly, and derives non-obvious solutions from first principles.

---

## Modules

### M0 · Complexity & Analysis  `🟢`
**Topics**
- [ ] Big-O / Big-Θ / Big-Ω, best/avg/worst case
- [ ] Time vs space complexity; amortized analysis
- [ ] Complexity of common operations per data structure
- [ ] Recursion cost: recurrence relations, call-stack space

**Exercises**
- Annotate 10 of your past solutions with their time/space complexity and justify each.
- Given 5 code snippets, rank them by asymptotic growth.

**Mini-project (assignment)**
- Build a small "complexity cheat-sheet" table (ops × structures) from memory, then verify it.

**Interview pointers**
- "What's the complexity of this?" · optimizing a brute force · space-time trade-off framing.

### M1 · Arrays & Strings  `🟢`
**Topics**
- [ ] Traversal, in-place mutation, prefix sums
- [ ] String manipulation, immutability, char frequency
- [ ] Matrix traversal (rotation, spiral, transpose)

**Exercises**
- Prefix-sum range queries; in-place array transforms; anagram grouping.

**Mini-project (assignment)**
- CLI text-analytics tool: word/char frequency, top-K words, palindrome detector.

**Interview pointers**
- Sub-array/sub-string problems · in-place with O(1) space · matrix manipulation.

### M2 · Hashing  `🟢`
**Topics**
- [ ] Hash maps & sets: operations, collisions, load factor
- [ ] Frequency counting, de-duplication, grouping
- [ ] Trade-offs vs sorted structures

**Exercises**
- Two-sum family; first unique element; group anagrams; subarray-sum-equals-K.

**Mini-project (assignment)**
- Implement a hash map from scratch (chaining + resizing) and benchmark vs the built-in.

**Interview pointers**
- "Can you do it in one pass?" · space-for-time trade with a map.

### M3 · Two Pointers & Sliding Window  `🟢`
**Topics**
- [ ] Opposite-end & same-direction pointers
- [ ] Fixed and variable-size sliding windows
- [ ] Fast/slow pointers

**Exercises**
- Container-with-most-water style; longest-substring-without-repeats; window max/min.

**Mini-project (assignment)**
- Rate-limiter simulation using a sliding window over a timestamp stream.

**Interview pointers**
- Recognizing when sorting + two pointers beats nested loops.

### M4 · Stacks & Queues  `🟢`
**Topics**
- [ ] Stack, queue, deque; monotonic stack/queue
- [ ] Expression evaluation & parsing
- [ ] Queue via stacks / stack via queues

**Exercises**
- Valid parentheses; next-greater-element; min-stack; sliding-window-maximum (deque).

**Mini-project (assignment)**
- Expression evaluator (infix → postfix → evaluate) supporting +−×÷ and parentheses.

**Interview pointers**
- Monotonic stack pattern · "nearest greater/smaller" family.

### M5 · Linked Lists  `🟢`
**Topics**
- [ ] Singly/doubly lists; dummy-head technique
- [ ] Reversal, cycle detection, merge, reorder
- [ ] Fast/slow pointer applications

**Exercises**
- Reverse in groups; detect & remove cycle; merge K sorted lists; LRU building block.

**Mini-project (assignment)**
- Implement an LRU cache (doubly linked list + hash map) with O(1) get/put.

**Interview pointers**
- Pointer manipulation without extra space · cycle problems.

### M6 · Recursion & Backtracking  `🟢`
**Topics**
- [ ] Recursion patterns, base/recursive cases, state restore
- [ ] Subsets, permutations, combinations
- [ ] Pruning & constraint propagation

**Exercises**
- Generate subsets/permutations; N-Queens; word search; combination sum.

**Mini-project (assignment)**
- Sudoku solver with backtracking + constraint pruning; report nodes explored.

**Interview pointers**
- "Enumerate all …" problems · recursion-tree reasoning · when to prune.

### M7 · Sorting & Searching  `🟢`
**Topics**
- [ ] Comparison sorts (merge, quick, heap) & stability
- [ ] Binary search + "binary search on the answer"
- [ ] Non-comparison sorts (counting, radix) — when valid

**Exercises**
- Implement merge & quicksort; search in rotated array; find peak; k-th smallest.

**Mini-project (assignment)**
- Sorting visualizer (data only): instrument comparisons/swaps and compare algorithms.

**Interview pointers**
- Binary search on monotonic predicates · custom comparators · partial sorting.

### M8 · Trees & BST  `🟢`
**Topics**
- [ ] Traversals (pre/in/post/level), recursive & iterative
- [ ] BST properties, insert/delete/search
- [ ] Height, diameter, LCA, path problems

**Exercises**
- Level-order; validate BST; LCA; serialize/deserialize a tree.

**Mini-project (assignment)**
- Build a BST-backed ordered map with range queries; add self-balancing as a stretch goal.

**Interview pointers**
- Recursion over trees · BST invariants · traversal-order reconstruction.

### M9 · Heaps & Priority Queues  `🟡`
**Topics**
- [ ] Binary heap: sift-up/down, build-heap
- [ ] Top-K, streaming median (two heaps)
- [ ] k-way merge

**Exercises**
- Top-K frequent; median of a data stream; merge k sorted streams.

**Mini-project (assignment)**
- Task scheduler using a priority queue with priorities + cooldowns.

**Interview pointers**
- "Top/smallest K" · streaming problems · heap vs sort trade-off.

### M10 · Graphs  `🟡`
**Topics**
- [ ] Representations (adjacency list/matrix); BFS/DFS
- [ ] Topological sort; cycle detection (directed/undirected)
- [ ] Shortest paths (Dijkstra, Bellman-Ford, 0-1 BFS); Union-Find
- [ ] MST (Kruskal/Prim) — intro

**Exercises**
- Number of islands; course schedule; word ladder; network delay time.

**Mini-project (assignment)**
- Route planner over a city grid/graph: shortest path + alternate routes, with metrics.

**Interview pointers**
- Modeling a problem as a graph · picking BFS vs Dijkstra · connectivity via Union-Find.

### M11 · Greedy  `🟡`
**Topics**
- [ ] Exchange-argument intuition; when greedy is provably correct
- [ ] Interval scheduling & merging
- [ ] Heap-assisted greedy

**Exercises**
- Merge intervals; non-overlapping intervals; jump game; task assignment.

**Mini-project (assignment)**
- Meeting-room allocator: minimize rooms for a set of intervals; justify the greedy choice.

**Interview pointers**
- Proving/knowing greedy correctness · counterexamples where greedy fails.

### M12 · Dynamic Programming  `🟡`
**Topics**
- [ ] Memoization vs tabulation; state design
- [ ] 1-D DP (climbing/house-robber), 2-D DP (grid/edit-distance)
- [ ] Knapsack family; subsequence DP (LIS, LCS)
- [ ] Interval DP intro

**Exercises**
- Coin change; edit distance; LIS in O(n log n); 0/1 knapsack; word break.

**Mini-project (assignment)**
- Diff tool core: compute LCS/edit-distance between two files and print an alignment.

**Interview pointers**
- Defining state + transition · recognizing overlapping subproblems · space optimization.

### M13 · Tries & String Algorithms  `🔴`
**Topics**
- [ ] Trie: insert/search/prefix; compressed tries (intro)
- [ ] Pattern matching: KMP, Rabin-Karp, Z-algorithm
- [ ] Suffix structures (intro)

**Exercises**
- Implement a trie; word-search II; substring search with KMP; longest repeated substring.

**Mini-project (assignment)**
- Autocomplete engine: trie-backed prefix search with ranking by frequency.

**Interview pointers**
- Prefix problems → trie · efficient substring search · rolling hash.

### M14 · Advanced (Union-Find, Segment/Fenwick Trees, Bit Manipulation)  `🔴`
**Topics**
- [ ] Union-Find with path compression + union by rank
- [ ] Segment tree / Fenwick (BIT) for range queries + updates
- [ ] Bit manipulation: masks, subsets, tricks
- [ ] Advanced graph (bridges/articulation, max-flow intuition) — awareness

**Exercises**
- Range-sum/min with updates; count inversions (BIT); bitmask DP; redundant connection.

**Mini-project (assignment)**
- Range-query engine supporting sum/min/max with point + range updates; benchmark structures.

**Interview pointers**
- Range-query trade-offs · bitmask state compression · Union-Find for connectivity.

---

## Capstone Project(s)

- **Capstone A — "Algorithm Playground"** `🟡` — A data-only engine that lets you run,
  instrument, and compare implementations across modules (counts of ops, time, space).
  *Acceptance:* covers ≥6 modules, reports metrics, and includes a written pattern index.
- **Capstone B — "Mini-LeetCode grader"** `🔴` — A harness that runs your solutions against
  test cases with time limits and reports complexity class empirically.
  *Acceptance:* supports custom test sets, timeouts, and a per-problem pattern tag.

## Self-Assessment Checkpoints
- [ ] 🟢 I can state the time/space complexity of my own solution and defend it.
- [ ] 🟢 I reach for the right structure (map/stack/two-pointers) without trial and error.
- [ ] 🟡 I solve a random medium in ~25 min and explain trade-offs between two approaches.
- [ ] 🟡 I can design DP state + transition for a new problem unaided.
- [ ] 🔴 I dissect a hard problem, find a non-obvious optimization, and communicate it clearly.

## Interview Question Bank (pointers)
- **Patterns to drill:** two pointers · sliding window · fast/slow · monotonic stack ·
  BFS/DFS · topological sort · binary search on answer · backtracking · DP (1-D/2-D/knapsack/subsequence) ·
  union-find · heap/top-K · trie · intervals/greedy · bitmask.
- **By round type:** phone screen (easy-medium, 1–2 problems) · onsite coding (medium-hard) ·
  "optimize the brute force" follow-ups · communication + edge-case handling.
- **Meta:** clarify → examples → brute force → optimize → code → test → complexity.
