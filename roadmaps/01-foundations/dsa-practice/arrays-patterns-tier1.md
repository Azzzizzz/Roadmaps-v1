# 🎯 Arrays — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) · [Tier-2/3 Bank](linear-ds-tier2-3.md) |
| **Status** | ✅ Complete — Arrays (first in the Tier-1 pattern series) |
| **Scope** | Arrays — organized by **algorithmic pattern**, Tier-1 / MAANG difficulty |
| **Targets** | Tier-1 product companies · MAANG / FAANG |
| **Coverage** | 10 patterns · 90 questions |
| **Related** | Next in series → `strings-patterns-tier1.md`, `trees-patterns-tier1.md`, … |

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Rows are ordered **easy → hard within each pattern** (build the skill progressively). Examples show **intent** (`input → output`), *not* solutions.

---

## 🗺️ How to use this bank

> At Tier-1/MAANG, the interview is a **pattern-recognition** game — the questions are medium/hard,
> and your edge is mapping an unseen problem to a known pattern in under a minute.

**Workflow:** for each pattern → read the **🔍 recognize it when…** cue, then solve the questions
top-down (easy → hard). Your goal isn't to memorize solutions — it's to internalize the *trigger*
so a new problem instantly signals which tool to reach for.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Two Pointers](#p1) | 12 | sorted array · pair/triplet to a target · partition or move in place |
| 2 | [Sliding Window](#p2) | 12 | longest/shortest/at-most-K contiguous subarray · fixed window size k |
| 3 | [Binary Search](#p3) | 10 | sorted/rotated array · "minimize the max / maximize the min" on a monotonic answer |
| 4 | [Hashing / Hash Map](#p4) | 10 | need O(1) lookup/count · complement search · subarray-sum via prefix + map |
| 5 | [Prefix Sum & Difference](#p5) | 8 | many range-sum queries · running totals · range updates |
| 6 | [Kadane / Max Subarray](#p6) | 8 | best contiguous sum/product · running best with reset |
| 7 | [Merge Intervals](#p7) | 8 | intervals with start/end · overlap, merge, scheduling, min rooms |
| 8 | [Monotonic Stack](#p8) | 8 | next/previous greater or smaller · spans · histogram areas |
| 9 | [Matrix / 2D](#p9) | 8 | grid traversal · rotate/transpose · search in row/col-sorted matrix |
| 10 | [Cyclic Sort](#p10) | 6 | array holds values 1..n · find missing/duplicate in O(n) time, O(1) space |

---

<a id="p1"></a>
## 1 · Two Pointers (12)

> 🔍 **Recognize it when…** the array is sorted (or can be), you need a pair/triplet meeting a
> target, or you must partition / move elements in place with O(1) space.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Two Sum II — sorted input | 🟡 | `[2,7,11,15], t=9 → [1,2]` | ⭐⭐⭐ |
| 2 | Squares of a Sorted Array | 🟡 | `[-4,-1,0,3,10] → [0,1,9,16,100]` | ⭐⭐ |
| 3 | Move Zeroes | 🟡 | `[0,1,0,3,12] → [1,3,12,0,0]` | ⭐⭐ |
| 4 | Remove Duplicates from Sorted Array II (≤2) | 🟡 | `[1,1,1,2,2,3] → [1,1,2,2,3] (len 5)` | ⭐⭐ |
| 5 | Boats to Save People | 🟡 | `people=[3,2,2,1], limit=3 → 3` | ⭐⭐ |
| 6 | Max Number of K-Sum Pairs | 🟡 | `[1,2,3,4], k=5 → 2` | ⭐⭐ |
| 7 | 3Sum Closest | 🟡 | `[-1,2,1,-4], t=1 → 2` | ⭐⭐ |
| 8 | Container With Most Water | 🟡 | `[1,8,6,2,5,4,8,3,7] → 49` | ⭐⭐⭐ |
| 9 | Sort Colors (Dutch National Flag) | 🟡 | `[2,0,2,1,1,0] → [0,0,1,1,2,2]` | ⭐⭐⭐ |
| 10 | 3Sum | 🟡 | `[-1,0,1,2,-1,-4] → [[-1,-1,2],[-1,0,1]]` | ⭐⭐⭐ |
| 11 | 4Sum | 🟡 | `[1,0,-1,0,-2,2], t=0 → [[-2,-1,1,2],…]` | ⭐⭐ |
| 12 | Trapping Rain Water | 🔴 | `[0,1,0,2,1,0,1,3,2,1,2,1] → 6` | ⭐⭐⭐ |

<a id="p2"></a>
## 2 · Sliding Window (12)

> 🔍 **Recognize it when…** the answer is a *contiguous* subarray and you want the longest/shortest,
> an at-most-K constraint, or a running aggregate over a fixed window of size k.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Maximum Average Subarray I (fixed k) | 🟡 | `[1,12,-5,-6,50,3], k=4 → 12.75` | ⭐⭐ |
| 2 | Max Consecutive Ones III (flip ≤ k zeros) | 🟡 | `[1,1,0,0,1,1,1,0], k=2 → 6` | ⭐⭐⭐ |
| 3 | Fruit Into Baskets (≤ 2 distinct) | 🟡 | `[1,2,3,2,2] → 4` | ⭐⭐ |
| 4 | Subarray Product Less Than K | 🟡 | `[10,5,2,6], k=100 → 8` | ⭐⭐ |
| 5 | Minimum Size Subarray Sum (≥ target) | 🟡 | `target=7, [2,3,1,2,4,3] → 2` | ⭐⭐⭐ |
| 6 | Longest Subarray of 1's After Deleting One | 🟡 | `[1,1,0,1] → 3` | ⭐⭐ |
| 7 | Binary Subarrays With Sum | 🟡 | `[1,0,1,0,1], goal=2 → 4` | ⭐⭐ |
| 8 | Number of Subarrays with Bounded Maximum | 🟡 | `[2,1,4,3], L=2, R=3 → 3` | ⭐⭐ |
| 9 | Maximum Points From Cards (window on ends) | 🟡 | `[1,2,3,4,5,6,1], k=3 → 12` | ⭐⭐ |
| 10 | Subarrays with K Different Integers | 🔴 | `[1,2,1,2,3], k=2 → 7` | ⭐⭐ |
| 11 | Sliding Window Maximum (deque) | 🔴 | `[1,3,-1,-3,5,3,6,7], k=3 → [3,3,5,5,6,7]` | ⭐⭐⭐ |
| 12 | Shortest Subarray with Sum at Least K | 🔴 | `[2,-1,2], k=3 → 3` | ⭐⭐ |

<a id="p3"></a>
## 3 · Binary Search — modified / on the answer (10)

> 🔍 **Recognize it when…** the array is sorted or rotated, OR you're asked to "minimize the maximum /
> maximize the minimum" and the feasibility of a candidate answer is monotonic.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Binary Search (classic) | 🟢 | `[-1,0,3,5,9,12], t=9 → 4` | ⭐⭐ |
| 2 | Search Insert Position | 🟢 | `[1,3,5,6], t=5 → 2` | ⭐⭐ |
| 3 | Find First and Last Position | 🟡 | `[5,7,7,8,8,10], t=8 → [3,4]` | ⭐⭐⭐ |
| 4 | Find Peak Element | 🟡 | `[1,2,3,1] → 2` | ⭐⭐⭐ |
| 5 | Search in Rotated Sorted Array | 🟡 | `[4,5,6,7,0,1,2], t=0 → 4` | ⭐⭐⭐ |
| 6 | Find Minimum in Rotated Sorted Array | 🟡 | `[3,4,5,1,2] → 1` | ⭐⭐⭐ |
| 7 | Koko Eating Bananas (BS on answer) | 🟡 | `piles=[3,6,7,11], h=8 → 4` | ⭐⭐⭐ |
| 8 | Capacity To Ship Packages Within D Days | 🟡 | `weights=1..10, days=5 → 15` | ⭐⭐ |
| 9 | Split Array Largest Sum | 🔴 | `[7,2,5,10,8], k=2 → 18` | ⭐⭐ |
| 10 | Median of Two Sorted Arrays | 🔴 | `[1,3],[2] → 2.0` | ⭐⭐⭐ |

<a id="p4"></a>
## 4 · Hashing / Hash Map (10)

> 🔍 **Recognize it when…** you need O(1) lookup or counting, a complement search, grouping by key,
> or subarray-sum problems solvable with a running prefix stored in a map.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Two Sum | 🟢 | `[2,7,11,15], t=9 → [0,1]` | ⭐⭐⭐ |
| 2 | Contains Duplicate II (within k indices) | 🟡 | `[1,2,3,1], k=3 → true` | ⭐⭐ |
| 3 | Subarray Sum Equals K | 🟡 | `[1,1,1], k=2 → 2` | ⭐⭐⭐ |
| 4 | Continuous Subarray Sum (multiple of k) | 🟡 | `[23,2,4,6,7], k=6 → true` | ⭐⭐ |
| 5 | Contiguous Array (equal 0s and 1s) | 🟡 | `[0,1,0] → 2` | ⭐⭐ |
| 6 | Subarray Sums Divisible by K | 🟡 | `[4,5,0,-2,-3,1], k=5 → 7` | ⭐⭐ |
| 7 | Longest Consecutive Sequence | 🟡 | `[100,4,200,1,3,2] → 4` | ⭐⭐⭐ |
| 8 | 4Sum II (count tuples) | 🟡 | `A,B,C,D each [.. ] → count` | ⭐⭐ |
| 9 | Maximum Erasure Value (unique subarray) | 🟡 | `[4,2,4,5,6] → 17` | ⭐⭐ |
| 10 | Max Points on a Line | 🔴 | `[[1,1],[2,2],[3,3]] → 3` | ⭐⭐ |

<a id="p5"></a>
## 5 · Prefix Sum & Difference Arrays (8)

> 🔍 **Recognize it when…** there are many range-sum queries, you need running totals, or you must
> apply many range *updates* efficiently (difference array).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Running Sum of 1d Array | 🟢 | `[1,2,3,4] → [1,3,6,10]` | ⭐⭐ |
| 2 | Find Pivot Index | 🟢 | `[1,7,3,6,5,6] → 3` | ⭐⭐ |
| 3 | Range Sum Query — Immutable | 🟢 | `sumRange(0,2) of [-2,0,3,-5,2,-1] → 1` | ⭐⭐ |
| 4 | Product of Array Except Self | 🟡 | `[1,2,3,4] → [24,12,8,6]` | ⭐⭐⭐ |
| 5 | Range Sum Query 2D — Immutable | 🟡 | `region sum of a matrix → value` | ⭐⭐ |
| 6 | Number of Ways to Split Array | 🟡 | `[10,4,-8,7] → 2` | ⭐⭐ |
| 7 | Car Pooling (difference array) | 🟡 | `trips, capacity=4 → true/false` | ⭐⭐ |
| 8 | Corporate Flight Bookings (difference array) | 🟡 | `bookings, n=5 → [10,25,45,20,25]` | ⭐⭐ |

<a id="p6"></a>
## 6 · Kadane / Max Subarray (8)

> 🔍 **Recognize it when…** you want the best (max/min) *contiguous* subarray sum or product —
> track a running best and reset when it stops helping.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Best Time to Buy and Sell Stock | 🟢 | `[7,1,5,3,6,4] → 5` | ⭐⭐⭐ |
| 2 | Maximum Subarray (Kadane's) | 🟡 | `[-2,1,-3,4,-1,2,1,-5,4] → 6` | ⭐⭐⭐ |
| 3 | Maximum Product Subarray | 🟡 | `[2,3,-2,4] → 6` | ⭐⭐⭐ |
| 4 | Maximum Sum Circular Subarray | 🟡 | `[1,-2,3,-2] → 3` | ⭐⭐ |
| 5 | Maximum Absolute Sum of Any Subarray | 🟡 | `[1,-3,2,3,-4] → 5` | ⭐⭐ |
| 6 | Longest Turbulent Subarray | 🟡 | `[9,4,2,10,7,8,8,1,9] → 5` | ⭐⭐ |
| 7 | Maximum Sum of 3 Non-Overlapping Subarrays | 🔴 | `[1,2,1,2,6,7,5,1], k=2 → [0,3,5]` | ⭐⭐ |
| 8 | Maximum Subarray Min-Product | 🔴 | `[1,2,3,2] → 14` | ⭐⭐ |

<a id="p7"></a>
## 7 · Merge Intervals (8)

> 🔍 **Recognize it when…** the input is a set of intervals `[start, end]` and you need to merge
> overlaps, insert, count concurrent events (rooms), or schedule.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Meeting Rooms (can attend all?) | 🟢 | `[[0,30],[5,10],[15,20]] → false` | ⭐⭐ |
| 2 | Merge Intervals | 🟡 | `[[1,3],[2,6],[8,10],[15,18]] → [[1,6],[8,10],[15,18]]` | ⭐⭐⭐ |
| 3 | Insert Interval | 🟡 | `[[1,3],[6,9]], new=[2,5] → [[1,5],[6,9]]` | ⭐⭐⭐ |
| 4 | Non-overlapping Intervals (min removals) | 🟡 | `[[1,2],[2,3],[3,4],[1,3]] → 1` | ⭐⭐ |
| 5 | Meeting Rooms II (min rooms) | 🟡 | `[[0,30],[5,10],[15,20]] → 2` | ⭐⭐⭐ |
| 6 | Interval List Intersections | 🟡 | `A=[[0,2],[5,10]], B=[[1,5],[8,12]] → [[1,2],[5,5],[8,10]]` | ⭐⭐ |
| 7 | Minimum Arrows to Burst Balloons | 🟡 | `[[10,16],[2,8],[1,6],[7,12]] → 2` | ⭐⭐ |
| 8 | Employee Free Time | 🔴 | `schedule → common free intervals` | ⭐⭐ |

<a id="p8"></a>
## 8 · Monotonic Stack (8)

> 🔍 **Recognize it when…** you need the next/previous greater or smaller element, a "span", or a
> histogram-style area — maintain a stack that stays increasing or decreasing.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Next Greater Element I | 🟢 | `nums1=[4,1,2], nums2=[1,3,4,2] → [-1,3,-1]` | ⭐⭐ |
| 2 | Daily Temperatures | 🟡 | `[73,74,75,71,69,72,76,73] → [1,1,4,2,1,1,0,0]` | ⭐⭐⭐ |
| 3 | Next Greater Element II (circular) | 🟡 | `[1,2,1] → [2,-1,2]` | ⭐⭐ |
| 4 | Online Stock Span | 🟡 | `[100,80,60,70,60,75,85] → [1,1,1,2,1,4,6]` | ⭐⭐ |
| 5 | Remove K Digits | 🟡 | `"1432219", k=3 → "1219"` | ⭐⭐ |
| 6 | Sum of Subarray Minimums | 🟡 | `[3,1,2,4] → 17` | ⭐⭐ |
| 7 | Largest Rectangle in Histogram | 🔴 | `[2,1,5,6,2,3] → 10` | ⭐⭐⭐ |
| 8 | Maximal Rectangle | 🔴 | `binary matrix → 6` | ⭐⭐ |

<a id="p9"></a>
## 9 · Matrix / 2D Arrays (8)

> 🔍 **Recognize it when…** input is a grid and you must traverse it in a specific order, rotate /
> transpose in place, or search a matrix whose rows/cols are sorted.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Transpose Matrix | 🟢 | `[[1,2,3],[4,5,6]] → [[1,4],[2,5],[3,6]]` | ⭐⭐ |
| 2 | Rotate Image (90°, in place) | 🟡 | `[[1,2,3],[4,5,6],[7,8,9]] → [[7,4,1],[8,5,2],[9,6,3]]` | ⭐⭐⭐ |
| 3 | Spiral Matrix | 🟡 | `[[1,2,3],[4,5,6],[7,8,9]] → [1,2,3,6,9,8,7,4,5]` | ⭐⭐⭐ |
| 4 | Set Matrix Zeroes (O(1) space) | 🟡 | `[[1,1,1],[1,0,1],[1,1,1]] → [[1,0,1],[0,0,0],[1,0,1]]` | ⭐⭐⭐ |
| 5 | Search a 2D Matrix | 🟡 | `matrix, t=3 → true` | ⭐⭐⭐ |
| 6 | Search a 2D Matrix II (sorted rows & cols) | 🟡 | `matrix, t=5 → true` | ⭐⭐ |
| 7 | Diagonal Traverse | 🟡 | `[[1,2,3],[4,5,6],[7,8,9]] → [1,2,4,7,5,3,6,8,9]` | ⭐⭐ |
| 8 | Game of Life (in place) | 🟡 | `board → next generation` | ⭐⭐ |

<a id="p10"></a>
## 10 · Cyclic Sort / Index-as-Hash (6)

> 🔍 **Recognize it when…** the array holds n values in range 1..n (or 0..n) and you must find a
> missing or duplicate number in O(n) time and O(1) space — place each value at its index.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Missing Number | 🟢 | `[3,0,1] → 2` | ⭐⭐⭐ |
| 2 | Find All Numbers Disappeared in an Array | 🟢 | `[4,3,2,7,8,2,3,1] → [5,6]` | ⭐⭐ |
| 3 | Find the Duplicate Number | 🟡 | `[1,3,4,2,2] → 2` | ⭐⭐⭐ |
| 4 | Find All Duplicates in an Array | 🟡 | `[4,3,2,7,8,2,3,1] → [2,3]` | ⭐⭐ |
| 5 | Set Mismatch (duplicate + missing) | 🟡 | `[1,2,2,4] → [2,3]` | ⭐⭐ |
| 6 | First Missing Positive | 🔴 | `[3,4,-1,1] → 2` | ⭐⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given a new array problem, I can **name the pattern** in under 60 seconds.
- [ ] I've solved every 🟡 in each pattern and can explain the pattern's *trigger* and template.
- [ ] I've attempted every 🔴 and can reconstruct the approach from the pattern alone.
- [ ] I can state time/space complexity and handle edge cases for each.

> **Series:** this is the Arrays file. Next up (same format): `strings-patterns-tier1.md`,
> `trees-patterns-tier1.md`, `graphs-patterns-tier1.md`, `dp-patterns-tier1.md`.
