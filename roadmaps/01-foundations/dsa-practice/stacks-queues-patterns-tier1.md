# 🎯 Stacks & Queues — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) · [Arrays Patterns](arrays-patterns-tier1.md) · [Strings Patterns](strings-patterns-tier1.md) · [Linked List Patterns](linked-list-patterns-tier1.md) |
| **Status** | ✅ Complete — Stacks & Queues (4th in the Tier-1 pattern series) |
| **Kind** | Structure file (pattern-organized) |
| **Scope** | Stacks, queues & deques — structure-native + design problems, Tier-1 / MAANG |
| **Coverage** | 6 patterns · 37 questions |
| **Related** | Next in series → `trees-patterns-tier1.md` |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why pattern-first?** At Tier-1/MAANG the interview is a **pattern-recognition** game — you solve a
*new* problem by matching it to a pattern you know. So this bank is organized by the **pattern that
cracks the problem**, not as a flat list.

**⚠️ This file is deliberately scoped.** A stack or queue is very often just a *tool* inside a problem
whose real subject is an array or string — and by our one-home rule those live in their own banks:

- **Monotonic stack** on arrays (Next Greater Element, Daily Temperatures, Stock Span, Histogram) →
  [Arrays bank → Monotonic Stack](arrays-patterns-tier1.md#p8).
- **Stack-based string parsing** (Valid Parentheses, Decode String, Basic Calculator I/II, Min Remove
  to Make Valid) → [Strings bank → Stack-Based](strings-patterns-tier1.md#p6).
- **List-backed caches** (LRU, LFU) → [Linked List bank → Design & Copy](linked-list-patterns-tier1.md#p6).

So this file covers what's genuinely *about the stack/queue itself*: **design/implementation**,
**advanced monotonic** problems not already listed, **expression/simulation**, and **deque** techniques.
Each section starts with a **see also** link so you know where the sibling problems live.

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the `input → output` example is only to confirm you understood
the question. Goal: **name the pattern in under 60 seconds** on a new problem.

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> **Mental model:** **stack** = LIFO → nesting / undo / "most recent" · **queue** = FIFO → BFS / streaming / fairness · **deque** = both ends → sliding-window extremes.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Parentheses & Bracket Matching](#p1) | 6 | validate / repair / score nested brackets — each closer matches the most recent opener |
| 2 | [Monotonic Stack (advanced)](#p2) | 7 | next/previous greater-or-smaller while keeping order · "collision" or eviction of earlier elements |
| 3 | [Expression & Simulation](#p3) | 6 | evaluate/parse an expression, or simulate nested/undoable operations |
| 4 | [Stack Design](#p4) | 5 | build a stack with an extra O(1) query, or a stack from other structures |
| 5 | [Queue & Deque Design](#p5) | 7 | implement a FIFO / deque / streaming structure at a required complexity |
| 6 | [Monotonic Deque & Queue Simulation](#p6) | 6 | sliding-window extreme, or round-robin / eviction simulated with a queue |

---

<a id="p1"></a>
## 1 · Parentheses & Bracket Matching (6)

> 🔍 **Recognize it when…** you validate, repair, or score nested brackets — each closing bracket
> must resolve against the most recent unmatched opener.
> **See also:** Valid Parentheses & Minimum Remove to Make Valid → [Strings bank](strings-patterns-tier1.md#p6).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Minimum Add to Make Parentheses Valid | 🟡 | `"())" → 1` | ⭐⭐ |
| 2 | Validate Stack Sequences | 🟡 | `pushed=[1,2,3,4,5], popped=[4,5,3,2,1] → true` | ⭐⭐ |
| 3 | Score of Parentheses | 🟡 | `"(())" → 2` | ⭐⭐ |
| 4 | Minimum Insertions to Balance a Parentheses String | 🟡 | `"(()))" → 1` | ⭐⭐ |
| 5 | Check if a Parentheses String Can Be Valid | 🟡 | `s="))()))", locked="010100" → true` | ⭐⭐ |
| 6 | Longest Valid Parentheses | 🔴 | `")()())" → 4` | ⭐⭐⭐ |

<a id="p2"></a>
## 2 · Monotonic Stack — advanced (7)

> 🔍 **Recognize it when…** you keep a stack that stays increasing/decreasing to answer next/previous
> greater-or-smaller, or when later elements "collide with" / evict earlier ones.
> **See also:** Next Greater Element, Daily Temperatures, Stock Span, Largest Rectangle → [Arrays bank](arrays-patterns-tier1.md#p8).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Remove Duplicate Letters (smallest lexicographic) | 🟡 | `"cbacdcbc" → "acdb"` | ⭐⭐ |
| 2 | Asteroid Collision | 🟡 | `[5,10,-5] → [5,10]` | ⭐⭐⭐ |
| 3 | 132 Pattern | 🟡 | `[3,1,4,2] → true` | ⭐⭐ |
| 4 | Next Greater Node In Linked List | 🟡 | `2→1→5 → [5,5,0]` | ⭐⭐ |
| 5 | Car Fleet | 🟡 | `target=12, pos=[10,8,0,5,3], speed=[2,4,1,1,3] → 3` | ⭐⭐ |
| 6 | Sum of Subarray Ranges | 🟡 | `[1,2,3] → 4` | ⭐⭐ |
| 7 | Maximum Frequency Stack | 🔴 | `push 5,7,5,7,4,5; pop×4 → 5,7,5,4` | ⭐⭐ |

<a id="p3"></a>
## 3 · Expression & Simulation (6)

> 🔍 **Recognize it when…** you evaluate or parse an expression, or simulate nested / undoable
> operations where the stack tracks "where you are".
> **See also:** Decode String & Basic Calculator I/II → [Strings bank](strings-patterns-tier1.md#p6).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Make The String Great | 🟢 | `"leEeetcode" → "leetcode"` | ⭐⭐ |
| 2 | Crawler Log Folder | 🟢 | `["d1/","d2/","../","d21/","./"] → 1` | ⭐ |
| 3 | Evaluate Reverse Polish Notation | 🟡 | `["2","1","+","3","*"] → 9` | ⭐⭐⭐ |
| 4 | Simplify Path | 🟡 | `"/a/./b/../../c/" → "/c"` | ⭐⭐ |
| 5 | Exclusive Time of Functions | 🟡 | `n=2, logs → [3,4]` | ⭐⭐ |
| 6 | Basic Calculator III (+ − × ÷ and parens) | 🔴 | `"2*(5+5*2)/3+(6/2+8)" → 21` | ⭐⭐ |

<a id="p4"></a>
## 4 · Stack Design (5)

> 🔍 **Recognize it when…** you must support an extra O(1) query on a stack (min/max), or build a
> stack out of other primitives.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Min Stack | 🟢 | `push -2,0,-3; getMin → -3; pop; top → 0; getMin → -2` | ⭐⭐⭐ |
| 2 | Implement Stack using Queues | 🟢 | `push 1,2; top → 2; pop → 2` | ⭐⭐ |
| 3 | Max Stack | 🟡 | `push 5,1,5; peekMax → 5; popMax → 5; top → 1` | ⭐⭐ |
| 4 | Design a Stack With Increment Operation | 🟡 | `push; increment(k,val); pop → updated values` | ⭐⭐ |
| 5 | Dinner Plate Stacks | 🔴 | `push / pop / popAtStack across capacity-limited stacks` | ⭐ |

<a id="p5"></a>
## 5 · Queue & Deque Design (7)

> 🔍 **Recognize it when…** you implement a FIFO, circular buffer, deque, or streaming aggregate at a
> required amortized complexity.
> **See also:** LRU / LFU list-backed caches → [Linked List bank](linked-list-patterns-tier1.md#p6).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Implement Queue using Stacks | 🟢 | `push 1,2; peek → 1; pop → 1` | ⭐⭐⭐ |
| 2 | Number of Recent Calls | 🟢 | `ping 1,100,3001,3002 → 1,2,3,3` | ⭐⭐ |
| 3 | Moving Average from Data Stream | 🟢 | `size=3; next 1→1, 10→5.5, 3→4.67` | ⭐⭐ |
| 4 | Design Circular Queue | 🟡 | `enQueue/deQueue/Front/Rear/isFull → correct` | ⭐⭐⭐ |
| 5 | Design Circular Deque | 🟡 | `insertFront/insertLast/deleteFront/... → correct` | ⭐⭐ |
| 6 | Design Front Middle Back Queue | 🟡 | `pushFront/pushMiddle/popBack/... → correct` | ⭐⭐ |
| 7 | Design Hit Counter | 🟡 | `hit 1,2,300; getHits(300) → 3; getHits(301) → 2` | ⭐⭐ |

<a id="p6"></a>
## 6 · Monotonic Deque & Queue Simulation (6)

> 🔍 **Recognize it when…** you need a sliding-window max/min, or a fair round-robin / eviction that a
> queue or double-ended queue models directly.
> **See also:** Sliding Window Maximum & Shortest Subarray with Sum ≥ K → [Arrays bank](arrays-patterns-tier1.md#p2).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Time Needed to Buy Tickets | 🟢 | `[2,3,2], k=2 → 6` | ⭐⭐ |
| 2 | Number of Students Unable to Eat Lunch | 🟢 | `students=[1,1,0,0], sandwiches=[0,1,0,1] → 0` | ⭐⭐ |
| 3 | Dota2 Senate | 🟡 | `"RD" → "Radiant"` | ⭐⭐ |
| 4 | Reveal Cards In Increasing Order | 🟡 | `[17,13,11,2,3,5,7] → [2,13,3,11,5,17,7]` | ⭐⭐ |
| 5 | First Unique Number (stream) | 🟡 | `add / showFirstUnique → value or -1` | ⭐⭐ |
| 6 | Jump Game VI (monotonic-deque DP) | 🔴 | `[1,-1,-2,4,-7,3], k=2 → 7` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given a new problem, I can tell whether it's really a **stack/queue** problem or an array/string
      one that merely *uses* one — and I know which bank it lives in.
- [ ] I can implement a **stack, queue, circular queue, and deque** from scratch, and a **min-stack** in O(1).
- [ ] I've solved every 🟡 and can explain each pattern's template.
- [ ] I've attempted every 🔴 (Longest Valid Parentheses, FreqStack, Basic Calculator III, Jump Game VI).
- [ ] I handle edge cases: empty structure, single element, full/wrap-around, interleaved push/pop.

> **Series:** Arrays ✅ · Strings ✅ · Linked List ✅ · Stacks & Queues ✅ · next →
> `trees-patterns-tier1.md`, then graphs → heaps → dp → backtracking.
