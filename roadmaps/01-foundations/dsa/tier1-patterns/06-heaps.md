# 🎯 Heaps / Priority Queue — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../../dsa.md) · [Graphs Patterns](07-graphs.md) · [Arrays Patterns](01-arrays.md) |
| **Status** | ✅ Complete — Heaps (7th in the Tier-1 pattern series) |
| **Kind** | Structure file (pattern-organized) |
| **Scope** | Binary heaps / priority queues, organized by **pattern**, Tier-1 / MAANG |
| **Coverage** | 5 patterns · 35 questions |
| **Related** | Next in series → the paradigm files `09-dynamic-programming.md`, `08-backtracking.md` |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why pattern-first?** At Tier-1/MAANG the interview is a **pattern-recognition** game — you solve a
*new* problem by matching it to a pattern you know. This bank is organized by the **pattern that
cracks the problem**, not as a flat list.

**The one reflex for heaps:** a heap = *"always hand me the current min/max in O(log n)."* Reach for it
whenever a problem **repeatedly needs the best/worst element from a changing set**:
- **Top-K** → keep a size-K heap (for the K *largest*, use a *min*-heap so the smallest falls out).
- **Running median** → two heaps (max-heap of the low half + min-heap of the high half).
- **Merge K sorted** → one heap holding the current head of each sequence.
- **Greedy scheduling** → the heap always yields the next best/most-urgent choice.

Rule of thumb: **if you find yourself re-sorting inside a loop, you probably want a heap.**

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the `input → output` example is only to confirm you understood
the question. Goal: **name the pattern in under 60 seconds** on a new problem.

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Most languages give a **min-heap**; negate keys (or use a max-heap) as needed. For "remove arbitrary element", pair the heap with **lazy deletion**.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Top-K Elements](#p1) | 9 | you need the K largest / smallest / most-frequent — keep a size-K heap |
| 2 | [Two Heaps (Median)](#p2) | 5 | you need the median / balance point of a growing or sliding dataset |
| 3 | [K-way Merge](#p3) | 7 | merge or traverse K sorted sequences at once |
| 4 | [Scheduling & Greedy](#p4) | 8 | repeatedly pick the current best/most-urgent option (cooldowns, deadlines, capacity) |
| 5 | [Design & Streaming](#p5) | 6 | a data structure with priority-based queries over a stream |

---

<a id="p1"></a>
## 1 · Top-K Elements (9)

> 🔍 **Recognize it when…** you need the K largest, smallest, or most-frequent items. Keep a heap of
> size K — a **min-heap** for the K *largest* (the smallest keeps falling out).
> **See also:** Sort Characters By Frequency also lives in [Strings bank](02-strings.md#p3).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Third Maximum Number | 🟢 | `[3,2,1] → 1` | ⭐ |
| 2 | Kth Largest Element in a Stream | 🟢 | `k=3; add stream → kth largest each time` | ⭐⭐ |
| 3 | Kth Largest Element in an Array | 🟡 | `[3,2,1,5,6,4], k=2 → 5` | ⭐⭐⭐ |
| 4 | K Closest Points to Origin | 🟡 | `[[1,3],[-2,2]], k=1 → [[-2,2]]` | ⭐⭐⭐ |
| 5 | Top K Frequent Elements | 🟡 | `[1,1,1,2,2,3], k=2 → [1,2]` | ⭐⭐⭐ |
| 6 | Top K Frequent Words | 🟡 | `["i","love","leetcode","i","love","coding"], k=2 → ["i","love"]` | ⭐⭐ |
| 7 | Sort Characters By Frequency | 🟡 | `"tree" → "eert"` | ⭐⭐ |
| 8 | Find K Closest Elements | 🟡 | `[1,2,3,4,5], k=4, x=3 → [1,2,3,4]` | ⭐⭐ |
| 9 | Least Number of Unique Integers after K Removals | 🟡 | `[5,5,4], k=1 → 1` | ⭐⭐ |

<a id="p2"></a>
## 2 · Two Heaps — running median (5)

> 🔍 **Recognize it when…** you need the median (or a balance point) of a growing/sliding dataset —
> a **max-heap** for the lower half + a **min-heap** for the upper half, kept balanced.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Find Right Interval | 🟡 | `[[1,2]] → [-1]` | ⭐ |
| 2 | Furthest Building You Can Reach | 🟡 | `heights, bricks, ladders → furthest index` | ⭐⭐ |
| 3 | Find Median from Data Stream | 🔴 | `add 1,2,3 → findMedian → 2.0` | ⭐⭐⭐ |
| 4 | Sliding Window Median | 🔴 | `[1,3,-1,-3,5,3,6,7], k=3 → [1,-1,-1,3,5,6]` | ⭐⭐ |
| 5 | IPO (maximize capital) | 🔴 | `k=2, w=0, profits=[1,2,3], capital=[0,1,1] → 4` | ⭐⭐ |

<a id="p3"></a>
## 3 · K-way Merge (7)

> 🔍 **Recognize it when…** you merge or traverse K sorted sequences at once — push each sequence's
> head into a min-heap, pop the smallest, push its successor.
> **See also:** Merge k Sorted Lists also lives in [Linked List bank](03-linked-list.md#p4).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Ugly Number II | 🟡 | `n=10 → 12` | ⭐⭐ |
| 2 | Super Ugly Number | 🟡 | `n=12, primes=[2,7,13,19] → 32` | ⭐ |
| 3 | Kth Smallest Element in a Sorted Matrix | 🟡 | `[[1,5,9],[10,11,13],[12,13,15]], k=8 → 13` | ⭐⭐⭐ |
| 4 | Find K Pairs with Smallest Sums | 🟡 | `nums1=[1,7,11], nums2=[2,4,6], k=3 → [[1,2],[1,4],[1,6]]` | ⭐⭐ |
| 5 | Merge k Sorted Lists | 🔴 | `[1→4→5, 1→3→4, 2→6] → 1→1→2→3→4→4→5→6` | ⭐⭐⭐ |
| 6 | Smallest Range Covering Elements from K Lists | 🔴 | `k sorted lists → [20,24]` | ⭐⭐ |
| 7 | Kth Smallest Number in Multiplication Table | 🔴 | `m=3, n=3, k=5 → 3` | ⭐ |

<a id="p4"></a>
## 4 · Scheduling & Greedy (8)

> 🔍 **Recognize it when…** you repeatedly pick the current best/most-urgent option under cooldowns,
> deadlines, or capacity — a heap gives O(log n) "next best".
> **See also:** Meeting Rooms II also relates to [Arrays bank → Merge Intervals](01-arrays.md#p7).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Last Stone Weight | 🟢 | `[2,7,4,1,8,1] → 1` | ⭐⭐ |
| 2 | Task Scheduler | 🟡 | `["A","A","A","B","B","B"], n=2 → 8` | ⭐⭐⭐ |
| 3 | Reorganize String | 🟡 | `"aab" → "aba"` | ⭐⭐⭐ |
| 4 | Meeting Rooms II (min rooms) | 🟡 | `[[0,30],[5,10],[15,20]] → 2` | ⭐⭐⭐ |
| 5 | Maximum Number of Events That Can Be Attended | 🟡 | `[[1,2],[2,3],[3,4]] → 3` | ⭐⭐ |
| 6 | Single-Threaded CPU | 🟡 | `tasks=[[1,2],[2,4],[3,2],[4,1]] → [0,2,3,1]` | ⭐⭐ |
| 7 | Minimum Cost to Hire K Workers | 🔴 | `quality, wage, k → 30.66667` | ⭐⭐ |
| 8 | Maximum Performance of a Team | 🔴 | `n, speed, efficiency, k → 60` | ⭐⭐ |

<a id="p5"></a>
## 5 · Design & Streaming (6)

> 🔍 **Recognize it when…** you design a structure answering priority-based queries over a stream —
> backed by one or two heaps, often with lazy deletion.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Design Twitter (merge K feeds) | 🟡 | `postTweet/follow/getNewsFeed → 10 most recent` | ⭐⭐ |
| 2 | Seat Reservation Manager | 🟡 | `reserve → smallest free seat; unreserve(n)` | ⭐⭐ |
| 3 | Stock Price Fluctuation | 🟡 | `update/current/maximum/minimum → values` | ⭐⭐ |
| 4 | Maximum Average Pass Ratio | 🟡 | `classes, extraStudents → max avg ratio` | ⭐⭐ |
| 5 | Process Tasks Using Servers | 🟡 | `servers, tasks → server index per task` | ⭐⭐ |
| 6 | The Skyline Problem | 🔴 | `buildings → skyline key points` | ⭐⭐⭐ |

---

## ✅ Definition of Done

- [ ] When a problem repeatedly needs the min/max of a changing set, I reach for a **heap** by reflex.
- [ ] I know the counter-intuitive trick: **min-heap of size K** for the K *largest*.
- [ ] I can build the **two-heap median** structure and keep the halves balanced.
- [ ] I've solved every 🟡 and attempted every 🔴 (median stream, merge-K, hire-K-workers, skyline).
- [ ] I handle edge cases: fewer than K elements, ties, empty heap, duplicate keys.

> **Series:** Arrays ✅ · Strings ✅ · Linked List ✅ · Stacks & Queues ✅ · Trees ✅ · Graphs ✅ ·
> Heaps ✅ · next → the **paradigm files**: `09-dynamic-programming.md`, then `08-backtracking.md`.
