# 🎯 Recursion & Divide-and-Conquer — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../../dsa.md) · [Backtracking](../tier1-patterns/08-backtracking.md) · [Dynamic Programming](../tier1-patterns/09-dynamic-programming.md) |
| **Status** | ✅ Complete — Recursion & Divide-and-Conquer (foundational on-ramp) |
| **Kind** | **Paradigm file** (pattern-organized; the base layer under Backtracking / DP / tree & graph DFS) |
| **Scope** | Recursion mechanics + divide-and-conquer, Tier-1 / MAANG |
| **Coverage** | 4 patterns · 28 questions |
| **Read before** | [Backtracking](../tier1-patterns/08-backtracking.md) and [Dynamic Programming](../tier1-patterns/09-dynamic-programming.md) — this is their foundation |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Where recursion sits.** Recursion isn't a "pattern" so much as the **engine** under half of DSA. Rather
than re-list search or DP problems here, this bank covers the two things that live *nowhere else*:
**recursion for its own sake** (mechanics) and **divide-and-conquer**.

**The recursion family — one picture that makes it all click:**

| Recursion + … | = Topic | Bank |
|---|---|---|
| a **base case + shrinking problem** | plain recursion | *this bank* |
| **split → solve halves → combine** | divide & conquer | *this bank* |
| **exhaustive search + undo** (choose/explore/un-choose) | backtracking | [Backtracking](../tier1-patterns/08-backtracking.md) |
| **overlapping subproblems + memo** | dynamic programming | [DP](../tier1-patterns/09-dynamic-programming.md) |
| **a tree / graph** | DFS | [Trees](../tier1-patterns/05-trees.md) · [Graphs](../tier1-patterns/07-graphs.md) |

**How to think recursively:** define the **base case** (when to stop) + the **recursive case** (how the
problem shrinks), then take the *recursive leap of faith* — trust the smaller call works. For
**divide-and-conquer**, the whole algorithm lives in the **combine** step (the merge in merge sort, the
cross-boundary case in max-subarray).

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the example only confirms you understood the question.

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> **Tips:** write the base case *first* · draw the recursion tree · watch call-stack depth (convert to iteration if deep) · for D&C complexity, `T(n)=a·T(n/b)+f(n)` → Master Theorem.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Recursion Fundamentals](#p1) | 7 | you're building the recursive muscle — base case + shrinking problem + the call stack |
| 2 | [D&C — Sorting & Selection](#p2) | 7 | split in half, sort/select each, combine — order statistics |
| 3 | [D&C — Arrays & Math](#p3) | 7 | halve the computation — exponentiation by squaring, D&C over an array |
| 4 | [D&C — Build & Combine](#p4) | 7 | recursively construct all solutions / a structure by splitting on a pivot/operator |

---

<a id="p1"></a>
## 1 · Recursion Fundamentals (7)

> 🔍 **Recognize it when…** you're learning to *think* recursively — a clear base case, a problem that
> shrinks each call, and reasoning about the call stack. These are the warm-ups.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Fibonacci Number (recursive → memo) | 🟢 | `n=6 → 8` | ⭐⭐ |
| 2 | Sum of Digits (recursive) | 🟢 | `12345 → 15` | ⭐ |
| 3 | Reverse a String (recursive) | 🟢 | `"hello" → "olleh"` | ⭐ |
| 4 | Power of Three (recursive) | 🟢 | `n=27 → true` | ⭐ |
| 5 | Greatest Common Divisor (Euclid) | 🟢 | `gcd(48,18) → 6` | ⭐⭐ |
| 6 | Tower of Hanoi | 🟡 | `n=3 → 7 moves` | ⭐⭐ |
| 7 | Flatten Nested List Iterator | 🟡 | `[[1,1],2,[1,1]] → [1,1,2,1,1]` | ⭐⭐ |

<a id="p2"></a>
## 2 · Divide & Conquer — Sorting & Selection (7)

> 🔍 **Recognize it when…** you split the input in half, solve each half, and **merge/combine** —
> sorting and order-statistics. Counting problems often hide inside the merge step.
> **See also:** Quickselect relates to [Heaps → Top-K](../tier1-patterns/06-heaps.md#p1); Merge k Lists to [Linked List](../tier1-patterns/03-linked-list.md#p4).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Merge Sort (implement) | 🟡 | `[5,2,4,1,3] → [1,2,3,4,5]` | ⭐⭐⭐ |
| 2 | Quick Sort (implement) | 🟡 | `[5,2,4,1,3] → [1,2,3,4,5]` | ⭐⭐ |
| 3 | Sort an Array | 🟡 | `[5,1,1,2,0,0] → [0,0,1,1,2,5]` | ⭐⭐ |
| 4 | Kth Largest Element (Quickselect) | 🟡 | `[3,2,1,5,6,4], k=2 → 5` | ⭐⭐⭐ |
| 5 | Count of Smaller Numbers After Self | 🔴 | `[5,2,6,1] → [2,1,1,0]` | ⭐⭐⭐ |
| 6 | Reverse Pairs | 🔴 | `[1,3,2,3,1] → 2` | ⭐⭐ |
| 7 | Merge k Sorted Lists (D&C pairing) | 🔴 | `[1→4→5, 1→3→4, 2→6] → 1→1→2→3→4→4→5→6` | ⭐⭐ |

<a id="p3"></a>
## 3 · Divide & Conquer — Arrays & Math (7)

> 🔍 **Recognize it when…** you halve the work each step — exponentiation by squaring, or a
> cross-boundary combine over an array.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Sqrt(x) (integer) | 🟢 | `x=8 → 2` | ⭐⭐ |
| 2 | Majority Element (Divide & Conquer) | 🟢 | `[2,2,1,1,1,2,2] → 2` | ⭐⭐ |
| 3 | Pow(x, n) (fast exponentiation) | 🟡 | `x=2, n=10 → 1024` | ⭐⭐⭐ |
| 4 | Maximum Subarray (Divide & Conquer) | 🟡 | `[-2,1,-3,4,-1,2,1,-5,4] → 6` | ⭐⭐ |
| 5 | Search a 2D Matrix II | 🟡 | `matrix, target=5 → true` | ⭐⭐ |
| 6 | Median of Two Sorted Arrays | 🔴 | `[1,3],[2] → 2.0` | ⭐⭐⭐ |
| 7 | The Skyline Problem (D&C) | 🔴 | `buildings → skyline key points` | ⭐⭐ |

<a id="p4"></a>
## 4 · Divide & Conquer — Build & Combine (7)

> 🔍 **Recognize it when…** you recursively construct all solutions or a structure by splitting on a
> pivot/operator, then combining the sub-results.
> **See also:** tree constructions live in [Trees → Construct & Serialize](../tier1-patterns/05-trees.md#p7).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Convert Sorted Array to BST | 🟢 | `[-10,-3,0,5,9] → height-balanced BST` | ⭐⭐ |
| 2 | Different Ways to Add Parentheses | 🟡 | `"2-1-1" → [0,2]` | ⭐⭐ |
| 3 | Construct Binary Tree from Preorder & Inorder | 🟡 | `pre=[3,9,20,15,7], in=[9,3,15,20,7] → tree` | ⭐⭐⭐ |
| 4 | Balance a Binary Search Tree | 🟡 | `unbalanced BST → balanced BST` | ⭐⭐ |
| 5 | Unique Binary Search Trees II | 🟡 | `n=3 → all structurally unique BSTs` | ⭐⭐ |
| 6 | Beautiful Array | 🟡 | `n=4 → [2,1,4,3]` | ⭐ |
| 7 | Longest Substring with At Least K Repeating Characters | 🔴 | `"aaabb", k=3 → 3` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] I write the **base case first** and trust the recursive call ("recursive leap of faith").
- [ ] I can implement **merge sort, quick sort, and quickselect** from scratch and state their recurrences.
- [ ] I recognize the D&C shape: **split → solve halves → combine** — and know the combine step *is* the algorithm.
- [ ] I can articulate the recursion family: this + memo = **DP**; this + undo = **Backtracking**; this over a tree = **DFS**.
- [ ] I've solved every 🟡 and attempted every 🔴 (count-smaller-after-self, median of two sorted, skyline).

> **Foundational on-ramp** to [Backtracking](../tier1-patterns/08-backtracking.md) and [Dynamic Programming](../tier1-patterns/09-dynamic-programming.md).
> **Full suite:** Arrays · Strings · Linked List · Stacks & Queues · Trees · Graphs · Heaps · Recursion & D&C · DP · Backtracking ✅
