# 🎯 Dynamic Programming — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../../dsa.md) · [Arrays](01-arrays.md) · [Strings](02-strings.md) · [Trees](05-trees.md) |
| **Status** | ✅ Complete — Dynamic Programming (8th in the Tier-1 pattern series) |
| **Kind** | **Paradigm file** (pattern-organized, spans all input types) |
| **Scope** | Dynamic programming, organized by DP **sub-pattern**, Tier-1 / MAANG |
| **Coverage** | 10 patterns · 90 questions |
| **Canonical home for** | **String DP** — the [Strings bank](02-strings.md#p4) cross-links here |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why a paradigm file?** DP isn't tied to one data structure — it shows up on arrays, strings, grids,
and trees. It's a huge, distinctive skill, so it gets its **own** file (like Backtracking), and it's the
canonical home for DP problems that live elsewhere (e.g. String DP — the Strings bank points here).

**The DP method — the *only* thing you're really practicing:**
1. **State** — what does `dp[i]` / `dp[i][j]` *mean*? (the hardest step)
2. **Transition** — how does a state build from smaller ones? (the recurrence)
3. **Base cases** — the smallest subproblems.
4. **Order** — compute states so dependencies come first (or memoized recursion).

The 10 patterns below are really just **the shape of the state**. Recognize DP when you see
*"count the ways" / "min or max cost" / "is it possible"* **with choices at each step and overlapping
subproblems**. Start with **recursion + memoization**, then convert to tabulation and optimize space.

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the example only confirms you understood the question. Goal:
**name the pattern and define the state in under 90 seconds** on a new problem (DP earns the extra 30s).

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Rows ordered **easy → hard within each pattern**. DP skews medium/hard — that's the topic, not the bank.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [1-D Linear (Fibonacci-style)](#p1) | 12 | `dp[i]` depends on a few previous indices — a linear scan |
| 2 | [0/1 Knapsack](#p2) | 9 | pick a subset (each item once) to hit a target/capacity |
| 3 | [Unbounded Knapsack](#p3) | 8 | pick items with **unlimited reuse** to reach a target |
| 4 | [Longest Increasing Subsequence](#p4) | 8 | longest/optimal subsequence under an ordering constraint |
| 5 | [Grid / 2-D DP](#p5) | 12 | each grid cell depends on its neighbors (up/left/diagonal) |
| 6 | [String DP](#p6) | 10 | transform/match two strings, or optimal subsequence/partition of a string |
| 7 | [Interval / Partition DP](#p7) | 8 | `dp[i][j]` over a range — try every split / last-operation point |
| 8 | [State Machine (Stocks)](#p8) | 8 | at each step you're in one of a few states and transition between them |
| 9 | [Bitmask DP](#p9) | 6 | small n (≤ ~20); track a subset of used/visited items as a bitmask |
| 10 | [DP on Trees & Digit DP](#p10) | 9 | the "sequence" is a tree (combine children) or the digits of a number |

---

<a id="p1"></a>
## 1 · 1-D Linear — Fibonacci-style (12)

> 🔍 **Recognize it when…** `dp[i]` depends on a couple of earlier indices (`i-1`, `i-2`) — a single
> linear pass building on prior answers.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Climbing Stairs | 🟢 | `n=3 → 3` | ⭐⭐⭐ |
| 2 | Min Cost Climbing Stairs | 🟢 | `[10,15,20] → 15` | ⭐⭐ |
| 3 | Fibonacci Number | 🟢 | `n=4 → 3` | ⭐⭐ |
| 4 | N-th Tribonacci Number | 🟢 | `n=4 → 4` | ⭐ |
| 5 | House Robber | 🟡 | `[2,7,9,3,1] → 12` | ⭐⭐⭐ |
| 6 | House Robber II (circular) | 🟡 | `[2,3,2] → 3` | ⭐⭐⭐ |
| 7 | Delete and Earn | 🟡 | `[3,4,2] → 6` | ⭐⭐ |
| 8 | Decode Ways | 🟡 | `"226" → 3` | ⭐⭐⭐ |
| 9 | Maximum Subarray (Kadane) | 🟡 | `[-2,1,-3,4,-1,2,1,-5,4] → 6` | ⭐⭐⭐ |
| 10 | Jump Game | 🟡 | `[2,3,1,1,4] → true` | ⭐⭐⭐ |
| 11 | Jump Game II (min jumps) | 🟡 | `[2,3,1,1,4] → 2` | ⭐⭐⭐ |
| 12 | Wiggle Subsequence | 🟡 | `[1,7,4,9,2,5] → 6` | ⭐⭐ |

<a id="p2"></a>
## 2 · 0/1 Knapsack (9)

> 🔍 **Recognize it when…** you choose a subset (each item used **at most once**) to hit a target sum or
> capacity — 2-D dp over `(index, remaining)`.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Subset Sum (does a subset reach target?) | 🟡 | `[3,34,4,12,5,2], sum=9 → true` | ⭐⭐ |
| 2 | Partition Equal Subset Sum | 🟡 | `[1,5,11,5] → true` | ⭐⭐⭐ |
| 3 | Count of Subsets with Given Sum | 🟡 | `[1,1,2,3], sum=4 → 3` | ⭐⭐ |
| 4 | Minimum Subset Sum Difference | 🟡 | `[1,6,11,5] → 1` | ⭐⭐ |
| 5 | Target Sum | 🟡 | `[1,1,1,1,1], target=3 → 5` | ⭐⭐⭐ |
| 6 | Last Stone Weight II | 🟡 | `[2,7,4,1,8,1] → 1` | ⭐⭐ |
| 7 | Ones and Zeroes | 🟡 | `strs, m=5, n=3 → 4` | ⭐⭐ |
| 8 | Tallest Billboard | 🔴 | `[1,2,3,6] → 6` | ⭐ |
| 9 | Profitable Schemes | 🔴 | `n=5, minProfit=3, group, profit → 2` | ⭐ |

<a id="p3"></a>
## 3 · Unbounded Knapsack (8)

> 🔍 **Recognize it when…** you pick items with **unlimited reuse** to reach a target — coins, squares,
> cuts, counts.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Coin Change (fewest coins) | 🟡 | `coins=[1,2,5], amount=11 → 3` | ⭐⭐⭐ |
| 2 | Coin Change II (number of combinations) | 🟡 | `amount=5, coins=[1,2,5] → 4` | ⭐⭐⭐ |
| 3 | Combination Sum IV (count ordered) | 🟡 | `[1,2,3], target=4 → 7` | ⭐⭐ |
| 4 | Perfect Squares | 🟡 | `n=12 → 3` | ⭐⭐⭐ |
| 5 | Integer Break | 🟡 | `n=10 → 36` | ⭐⭐ |
| 6 | Minimum Cost For Tickets | 🟡 | `days, costs → 11` | ⭐⭐ |
| 7 | Number of Dice Rolls With Target Sum | 🟡 | `n=2, k=6, target=7 → 6` | ⭐⭐ |
| 8 | Rod Cutting (max value) | 🟡 | `prices per length → max revenue` | ⭐ |

<a id="p4"></a>
## 4 · Longest Increasing Subsequence (8)

> 🔍 **Recognize it when…** you want the longest/optimal subsequence under an ordering constraint —
> O(n²) DP or O(n log n) patience sorting.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Longest Increasing Subsequence | 🟡 | `[10,9,2,5,3,7,101,18] → 4` | ⭐⭐⭐ |
| 2 | Number of Longest Increasing Subsequences | 🟡 | `[1,3,5,4,7] → 2` | ⭐⭐ |
| 3 | Longest Arithmetic Subsequence | 🟡 | `[3,6,9,12] → 4` | ⭐⭐ |
| 4 | Longest Arithmetic Subsequence of Given Difference | 🟡 | `[1,5,7,8,5,3,4,2,1], diff=-2 → 4` | ⭐⭐ |
| 5 | Maximum Length of Pair Chain | 🟡 | `[[1,2],[2,3],[3,4]] → 2` | ⭐⭐ |
| 6 | Longest String Chain | 🟡 | `["a","b","ba","bca","bda","bdca"] → 4` | ⭐⭐ |
| 7 | Russian Doll Envelopes | 🔴 | `[[5,4],[6,4],[6,7],[2,3]] → 3` | ⭐⭐⭐ |
| 8 | Maximum Height by Stacking Cuboids | 🔴 | `cuboids → max height` | ⭐ |

<a id="p5"></a>
## 5 · Grid / 2-D DP (12)

> 🔍 **Recognize it when…** a grid where each cell's answer depends on its neighbors (up / left /
> diagonal) — path counting or path cost.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Unique Paths | 🟡 | `m=3, n=7 → 28` | ⭐⭐⭐ |
| 2 | Unique Paths II (obstacles) | 🟡 | `[[0,0,0],[0,1,0],[0,0,0]] → 2` | ⭐⭐⭐ |
| 3 | Minimum Path Sum | 🟡 | `[[1,3,1],[1,5,1],[4,2,1]] → 7` | ⭐⭐⭐ |
| 4 | Triangle (min path) | 🟡 | `[[2],[3,4],[6,5,7],[4,1,8,3]] → 11` | ⭐⭐ |
| 5 | Minimum Falling Path Sum | 🟡 | `[[2,1,3],[6,5,4],[7,8,9]] → 13` | ⭐⭐ |
| 6 | Maximal Square | 🟡 | `binary matrix → 4` | ⭐⭐⭐ |
| 7 | Count Square Submatrices with All Ones | 🟡 | `matrix → 15` | ⭐⭐ |
| 8 | Minimum Path Cost in a Grid | 🟡 | `grid, moveCost → minimum` | ⭐ |
| 9 | Dungeon Game | 🔴 | `[[-2,-3,3],[-5,-10,1],[10,30,-5]] → 7` | ⭐⭐ |
| 10 | Maximal Rectangle | 🔴 | `binary matrix → 6` | ⭐⭐ |
| 11 | Cherry Pickup | 🔴 | `grid → max cherries (round trip)` | ⭐⭐ |
| 12 | Cherry Pickup II | 🔴 | `grid → max cherries (two robots)` | ⭐⭐ |

<a id="p6"></a>
## 6 · String DP (10)

> 🔍 **Recognize it when…** you transform or match *two* strings, count subsequences, or find an optimal
> subsequence/partition — 2-D dp over indices `(i, j)`.
> **This is the canonical home** — the [Strings bank](02-strings.md#p4) points here.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Longest Common Subsequence | 🟡 | `"abcde","ace" → 3` | ⭐⭐⭐ |
| 2 | Longest Palindromic Subsequence | 🟡 | `"bbbab" → 4` | ⭐⭐ |
| 3 | Delete Operation for Two Strings | 🟡 | `"sea","eat" → 2` | ⭐⭐ |
| 4 | Word Break | 🟡 | `"leetcode", ["leet","code"] → true` | ⭐⭐⭐ |
| 5 | Minimum ASCII Delete Sum for Two Strings | 🟡 | `"sea","eat" → 231` | ⭐⭐ |
| 6 | Edit Distance | 🔴 | `"horse","ros" → 3` | ⭐⭐⭐ |
| 7 | Distinct Subsequences | 🔴 | `"rabbbit","rabbit" → 3` | ⭐⭐ |
| 8 | Interleaving String | 🔴 | `"aabcc","dbbca","aadbbcbcac" → true` | ⭐⭐ |
| 9 | Regular Expression Matching | 🔴 | `"aa","a*" → true` | ⭐⭐⭐ |
| 10 | Wildcard Matching | 🔴 | `"adceb","*a*b" → true` | ⭐⭐ |

<a id="p7"></a>
## 7 · Interval / Partition DP (8)

> 🔍 **Recognize it when…** `dp[i][j]` covers a range and you try every split point or "last operation"
> inside it — merging subintervals bottom-up.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Stone Game | 🟡 | `[5,3,4,5] → true` | ⭐⭐ |
| 2 | Guess Number Higher or Lower II | 🟡 | `n=10 → 16` | ⭐⭐ |
| 3 | Minimum Score Triangulation of Polygon | 🟡 | `[1,2,3] → 6` | ⭐⭐ |
| 4 | Minimum Cost Tree From Leaf Values | 🟡 | `[6,2,4] → 32` | ⭐⭐ |
| 5 | Palindrome Partitioning II (min cuts) | 🔴 | `"aab" → 1` | ⭐⭐ |
| 6 | Minimum Cost to Cut a Stick | 🔴 | `n=7, cuts=[1,3,4,5] → 16` | ⭐⭐ |
| 7 | Burst Balloons | 🔴 | `[3,1,5,8] → 167` | ⭐⭐⭐ |
| 8 | Remove Boxes | 🔴 | `[1,3,2,2,2,3,4,3,1] → 23` | ⭐ |

<a id="p8"></a>
## 8 · State Machine — Stocks (8)

> 🔍 **Recognize it when…** at each step you're in one of a few states (hold / sold / rest) and you
> transition between them — "best time to buy/sell".

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Best Time to Buy and Sell Stock | 🟢 | `[7,1,5,3,6,4] → 5` | ⭐⭐⭐ |
| 2 | Best Time to Buy and Sell Stock II | 🟡 | `[7,1,5,3,6,4] → 7` | ⭐⭐⭐ |
| 3 | Best Time to Buy and Sell Stock with Cooldown | 🟡 | `[1,2,3,0,2] → 3` | ⭐⭐⭐ |
| 4 | Best Time to Buy and Sell Stock with Transaction Fee | 🟡 | `[1,3,2,8,4,9], fee=2 → 8` | ⭐⭐ |
| 5 | Paint House | 🟡 | `[[17,2,17],[16,16,5],[14,3,19]] → 10` | ⭐⭐ |
| 6 | Best Time to Buy and Sell Stock III (≤ 2 txns) | 🔴 | `[3,3,5,0,0,3,1,4] → 6` | ⭐⭐⭐ |
| 7 | Best Time to Buy and Sell Stock IV (≤ k txns) | 🔴 | `k=2, [2,4,1] → 2` | ⭐⭐ |
| 8 | Maximum Profit in Job Scheduling | 🔴 | `startTime, endTime, profit → max profit` | ⭐⭐ |

<a id="p9"></a>
## 9 · Bitmask DP (6)

> 🔍 **Recognize it when…** n is small (≤ ~20) and you track a **subset** of used/visited items as a
> bitmask in the state.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Beautiful Arrangement | 🟡 | `n=2 → 2` | ⭐⭐ |
| 2 | Partition to K Equal Sum Subsets | 🔴 | `[4,3,2,3,5,2,1], k=4 → true` | ⭐⭐⭐ |
| 3 | Shortest Path Visiting All Nodes | 🔴 | `graph → 4` | ⭐⭐ |
| 4 | Maximum Students Taking Exam | 🔴 | `seats → max seated` | ⭐ |
| 5 | Minimum Incompatibility | 🔴 | `[1,2,1,4], k=2 → 4` | ⭐ |
| 6 | Number of Ways to Wear Different Hats | 🔴 | `hats → count mod 1e9+7` | ⭐ |

<a id="p10"></a>
## 10 · DP on Trees & Digit DP (9)

> 🔍 **Recognize it when…** the "sequence" is a tree (combine children's results in post-order) or the
> **digits** of a number (state = position + tight-bound flag).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Unique Binary Search Trees | 🟡 | `n=3 → 5` | ⭐⭐⭐ |
| 2 | Unique Binary Search Trees II | 🟡 | `n=3 → all structurally unique BSTs` | ⭐⭐ |
| 3 | House Robber III | 🟡 | `[3,2,3,null,3,null,1] → 7` | ⭐⭐⭐ |
| 4 | Longest Univalue Path | 🟡 | `[5,4,5,1,1,5] → 2` | ⭐⭐ |
| 5 | Count Numbers with Unique Digits | 🟡 | `n=2 → 91` | ⭐⭐ |
| 6 | Binary Tree Maximum Path Sum | 🔴 | `[-10,9,20,null,null,15,7] → 42` | ⭐⭐⭐ |
| 7 | Number of Digit One | 🔴 | `n=13 → 6` | ⭐⭐ |
| 8 | Non-negative Integers without Consecutive Ones | 🔴 | `n=5 → 5` | ⭐ |
| 9 | Numbers With Repeated Digits | 🔴 | `n=100 → 10` | ⭐ |

---

## ✅ Definition of Done

- [ ] For a new DP problem I can state the **state, transition, base cases, and order** out loud.
- [ ] I default to **recursion + memoization**, then convert to tabulation and optimize space.
- [ ] I've solved every 🟡 and can name which of the 10 patterns each belongs to.
- [ ] I've attempted every 🔴 (edit distance, burst balloons, stock III/IV, bitmask, digit DP).
- [ ] I recognize DP triggers instantly: *count the ways · min/max cost · is it possible* + overlapping subproblems.

> **Series:** Arrays ✅ · Strings ✅ · Linked List ✅ · Stacks & Queues ✅ · Trees ✅ · Graphs ✅ ·
> Heaps ✅ · Dynamic Programming ✅ · **last up →** `08-backtracking.md`.
