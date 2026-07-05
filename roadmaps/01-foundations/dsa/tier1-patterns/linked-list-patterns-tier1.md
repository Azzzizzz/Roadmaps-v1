# 🎯 Linked List — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../../dsa.md) · [Arrays Patterns](arrays-patterns-tier1.md) · [Strings Patterns](strings-patterns-tier1.md) |
| **Status** | ✅ Complete — Linked List (3rd in the Tier-1 pattern series) |
| **Kind** | Structure file (pattern-organized) |
| **Scope** | Singly / doubly linked lists, organized by **algorithmic pattern**, Tier-1 / MAANG |
| **Coverage** | 6 patterns · 46 questions |
| **Related** | Next in series → `stacks-queues-patterns-tier1.md` |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why pattern-first?** At Tier-1/MAANG the coding interview is a **pattern-recognition** game.
You won't be asked a problem you've memorized — you'll be asked a *new* one that's a variation of a
pattern you know. So these banks are organized by the **pattern that cracks the problem**, not as a
flat problem list. Learn the ~6 linked-list patterns here and you can attack almost any LL question,
seen or unseen.

**How to work through it:**
1. For each pattern, read the **🔍 recognize it when…** cue first — that's the *trigger* you're
   training your brain to fire on.
2. Solve the questions **top-down (easy → hard)**. Each pattern ramps from a 🟢/🟡 warm-up to a 🔴
   capstone, so you build the template before you stress-test it.
3. Solve from the **prompt**; use the `input → output` example only to confirm you understood the
   question — never to reverse-engineer the answer (there are no solutions here, by design).
4. Your goal per pattern: **given a new problem, name the pattern in under 60 seconds** and recall
   its pointer-manipulation template.

**Where this file sits in the suite:** this is a *structure file* — its home is problems whose
subject is the linked list itself. Patterns that merely *use* a list elsewhere (e.g. LRU also uses
hashing) still live here because the list is the core skill. Data-structure fundamentals and
frequency-ranked breadth for easier companies are in the [Tier-2/3 bank](../foundations/06-core-problems-tier2-3.md).

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> **Universal LL tips:** a **dummy/sentinel head** kills most head edge-cases; draw the pointers before you code; always ask if the list is **singly or doubly** and whether you may mutate it.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [In-place Reversal](#p1) | 8 | you must reverse all or part of the list by re-pointing `next` (track prev/curr/next) |
| 2 | [Fast & Slow Pointers](#p2) | 9 | find the middle · detect/locate a cycle · palindrome or reorder |
| 3 | [Dummy Node & Deletion](#p3) | 8 | insert/delete near the head or arbitrary nodes — a sentinel avoids edge-cases |
| 4 | [Merge / Add Lists](#p4) | 8 | combine two (or K) lists · arithmetic across two number-lists |
| 5 | [Recursion](#p5) | 6 | the list has a naturally recursive/nested shape, or reversal/merge reads cleaner recursively |
| 6 | [Design & Copy](#p6) | 7 | build a custom list · O(1) cache · copy a list with extra pointers |

---

<a id="p1"></a>
## 1 · In-place Reversal (8)

> 🔍 **Recognize it when…** you must reverse the whole list or a segment of it by re-pointing `next`
> pointers in place — keep three pointers (prev, curr, next) and watch the boundary nodes.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Reverse Linked List | 🟢 | `1→2→3→null → 3→2→1→null` | ⭐⭐⭐ |
| 2 | Swap Nodes in Pairs | 🟡 | `1→2→3→4 → 2→1→4→3` | ⭐⭐⭐ |
| 3 | Reverse Linked List II (positions m..n) | 🟡 | `1→2→3→4→5, m=2, n=4 → 1→4→3→2→5` | ⭐⭐⭐ |
| 4 | Rotate List (by k) | 🟡 | `1→2→3→4→5, k=2 → 4→5→1→2→3` | ⭐⭐⭐ |
| 5 | Odd Even Linked List | 🟡 | `1→2→3→4→5 → 1→3→5→2→4` | ⭐⭐ |
| 6 | Swapping Nodes in a Linked List (kth from ends) | 🟡 | `1→2→3→4→5, k=2 → 1→4→3→2→5` | ⭐⭐ |
| 7 | Reverse Nodes in k-Group | 🔴 | `1→2→3→4→5, k=2 → 2→1→4→3→5` | ⭐⭐⭐ |
| 8 | Reverse Alternating k Nodes | 🔴 | `1→2→3→4→5→6→7→8, k=2 → 2→1→3→4→6→5→7→8` | ⭐ |

<a id="p2"></a>
## 2 · Fast & Slow Pointers (9)

> 🔍 **Recognize it when…** you need the middle, must detect or locate a cycle, or check
> palindrome/reorder — move two pointers at different speeds.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Middle of the Linked List | 🟢 | `1→2→3→4→5 → 3` | ⭐⭐⭐ |
| 2 | Linked List Cycle (detect) | 🟢 | `3→2→0→-4→(back to 2) → true` | ⭐⭐⭐ |
| 3 | Remove Nth Node From End | 🟡 | `1→2→3→4→5, n=2 → 1→2→3→5` | ⭐⭐⭐ |
| 4 | Linked List Cycle II (cycle start) | 🟡 | `3→2→0→-4→(back to 2) → node 2` | ⭐⭐⭐ |
| 5 | Palindrome Linked List | 🟡 | `1→2→2→1 → true` | ⭐⭐⭐ |
| 6 | Reorder List | 🟡 | `1→2→3→4 → 1→4→2→3` | ⭐⭐⭐ |
| 7 | Maximum Twin Sum of a Linked List | 🟡 | `5→4→2→1 → 6` | ⭐⭐ |
| 8 | Delete the Middle Node of a Linked List | 🟡 | `1→3→4→7→1→2→6 → 1→3→4→1→2→6` | ⭐⭐ |
| 9 | Split Linked List in Parts | 🟡 | `1→2→3, k=5 → [[1],[2],[3],[],[]]` | ⭐⭐ |

<a id="p3"></a>
## 3 · Dummy Node & Deletion (8)

> 🔍 **Recognize it when…** you insert or delete near the head or at arbitrary positions — a sentinel
> `dummy` node before the head removes the "what if I delete the head?" edge-case.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Remove Linked List Elements | 🟢 | `1→2→6→3→4→5→6, val=6 → 1→2→3→4→5` | ⭐⭐ |
| 2 | Delete Node in a Linked List (given only that node) | 🟢 | `4→5→1→9, node=5 → 4→1→9` | ⭐⭐ |
| 3 | Remove Duplicates from Sorted List | 🟢 | `1→1→2→3→3 → 1→2→3` | ⭐⭐ |
| 4 | Remove Duplicates from Sorted List II (all dups) | 🟡 | `1→2→3→3→4→4→5 → 1→2→5` | ⭐⭐⭐ |
| 5 | Partition List (around value x) | 🟡 | `1→4→3→2→5→2, x=3 → 1→2→2→4→3→5` | ⭐⭐ |
| 6 | Merge Nodes in Between Zeros | 🟡 | `0→3→1→0→4→5→2→0 → 4→11` | ⭐⭐ |
| 7 | Remove Zero Sum Consecutive Nodes | 🟡 | `1→2→-3→3→1 → 3→1` | ⭐⭐ |
| 8 | Insert into a Sorted Circular Linked List | 🟡 | `insert 2 into 3→4→1(circular) → 3→4→1→2` | ⭐⭐ |

<a id="p4"></a>
## 4 · Merge / Add Lists (8)

> 🔍 **Recognize it when…** you combine two (or K) lists into one, or perform arithmetic digit-by-digit
> across two number-lists.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Merge Two Sorted Lists | 🟢 | `1→2→4, 1→3→4 → 1→1→2→3→4→4` | ⭐⭐⭐ |
| 2 | Add Two Numbers (reverse-order digits) | 🟡 | `2→4→3, 5→6→4 → 7→0→8` | ⭐⭐⭐ |
| 3 | Add Two Numbers II (forward-order digits) | 🟡 | `7→2→4→3, 5→6→4 → 7→8→0→7` | ⭐⭐ |
| 4 | Intersection of Two Linked Lists | 🟡 | `two lists meeting at 8 → node 8` | ⭐⭐⭐ |
| 5 | Insertion Sort List | 🟡 | `4→2→1→3 → 1→2→3→4` | ⭐⭐ |
| 6 | Merge In Between Linked Lists | 🟡 | `[0,1,2,3,4,5], a=2, b=4, [1000,1001] → 0→1→1000→1001→5` | ⭐ |
| 7 | Sort List (merge sort, O(n log n)) | 🟡 | `4→2→1→3 → 1→2→3→4` | ⭐⭐⭐ |
| 8 | Merge k Sorted Lists | 🔴 | `[1→4→5, 1→3→4, 2→6] → 1→1→2→3→4→4→5→6` | ⭐⭐⭐ |

<a id="p5"></a>
## 5 · Recursion (6)

> 🔍 **Recognize it when…** the list has a naturally recursive/nested shape (child pointers), or a
> reversal/merge reads cleaner as recursion than iteration.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Reverse Linked List (recursive) | 🟢 | `1→2→3 → 3→2→1` | ⭐⭐ |
| 2 | Merge Two Sorted Lists (recursive) | 🟢 | `1→2→4, 1→3→4 → 1→1→2→3→4→4` | ⭐⭐ |
| 3 | Swap Nodes in Pairs (recursive) | 🟡 | `1→2→3→4 → 2→1→4→3` | ⭐⭐ |
| 4 | Flatten a Multilevel Doubly Linked List | 🟡 | `multilevel DLL → single-level DLL` | ⭐⭐⭐ |
| 5 | Flatten a Sorted Multilevel List (child ptrs) | 🟡 | `nested sorted → one sorted list` | ⭐⭐ |
| 6 | Reverse Nodes in k-Group (recursive) | 🔴 | `1→2→3→4→5, k=2 → 2→1→4→3→5` | ⭐⭐ |

<a id="p6"></a>
## 6 · Design & Copy (7)

> 🔍 **Recognize it when…** you build a custom list-backed structure, need O(1) cache operations, or
> deep-copy a list that has extra pointers. *(These lean on a hashmap + doubly linked list — see also
> the Trees bank for the tree↔list conversions.)*

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Design Linked List | 🟡 | `addAtHead/addAtTail/get/deleteAtIndex → correct` | ⭐⭐ |
| 2 | Copy List with Random Pointer | 🟡 | `deep copy including random pointers` | ⭐⭐⭐ |
| 3 | LRU Cache (hashmap + DLL) | 🟡 | `cap=2; put/get → evicts least-recently-used` | ⭐⭐⭐ |
| 4 | Flatten Binary Tree to Linked List | 🟡 | `tree → right-skewed list (preorder)` | ⭐⭐ |
| 5 | Convert Sorted List to BST | 🟡 | `-10→-3→0→5→9 → height-balanced BST` | ⭐⭐ |
| 6 | All O'one Data Structure | 🔴 | `inc/dec/getMaxKey/getMinKey → keys` | ⭐ |
| 7 | LFU Cache (hashmap + freq DLLs) | 🔴 | `cap=2; put/get by frequency → evicts LFU` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given a new linked-list problem, I can **name the pattern** in under 60 seconds.
- [ ] I use a **dummy node** by reflex whenever the head might change, and I never lose a pointer.
- [ ] I've solved every 🟡 and can explain each pattern's pointer template.
- [ ] I've attempted every 🔴 (k-group reversal, merge-k, LFU) and can reconstruct the approach.
- [ ] I handle edge cases: empty list, single node, two nodes, even vs odd length, cycles.

> **Series:** Arrays ✅ · Strings ✅ · Linked List ✅ · next → `stacks-queues-patterns-tier1.md`,
> then trees → graphs → heaps → dp → backtracking.
