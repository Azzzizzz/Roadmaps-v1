# ⏱️ Complexity Analysis

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA roadmap](../../dsa.md) · [Guided path](../README.md) |
| **Status** | ✅ Complete |
| **Kind** | Foundation primer (checklist + drills) |
| **Scope** | reason about time & space before you optimize |
| **Prerequisites** | [Programming Foundations](01-programming-foundations.md) |
| **Next** | [Mathematics](03-mathematics.md) |

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard

---

## 📖 Read this first

Every pattern, structure, and paradigm later in this roadmap gets judged through one lens: **how does
it scale?** Complexity analysis is that lens — it's how you compare two working solutions and pick the
one that survives a larger input, and it's how an interviewer checks you understand what you wrote,
not just that it runs on the sample case.

**How to use this file:** work the checklists top to bottom — each is a set of named concepts, not an
explanation. Look each one up until you can derive it yourself, then check it off. When every box is
checked, do the practice drills: read the code pattern, state its time and space complexity out loud
(or on paper), and defend it. No answers are given here — that's the point.

## 📏 Asymptotic Notation

- [ ] Big-O (upper bound / worst case)
- [ ] Big-Θ / Theta (tight bound)
- [ ] Big-Ω / Omega (lower bound / best case)
- [ ] Best case vs. average case vs. worst case — when each matters
- [ ] Dropping constants and lower-order terms
- [ ] Combining complexities across sequential vs. nested code

## 🔁 Analyzing Iterative Code

- [ ] Single loop — counting iterations against the loop bound
- [ ] Nested loops — multiplying bounds
- [ ] Sequential (non-nested) loops — adding, then taking the dominant term
- [ ] Loops with non-unit steps (e.g. `i += 2`, `i *= 2`)
- [ ] Loop bounds that depend on input value vs. input size
- [ ] Early exits / breaks and their effect on worst-case bound

## 🌀 Analyzing Recursion

- [ ] Writing the recurrence relation for a recursive function
- [ ] The recursion tree method
- [ ] The substitution method
- [ ] The Master Theorem — and its three cases (names only, no derivation here)
- [ ] Counting total work across recursion depth × branching factor
- [ ] Call-stack depth as a hidden cost

## ⏳ Amortized Analysis

- [ ] What "amortized" means vs. worst-case-per-operation
- [ ] Dynamic array (vector/ArrayList) doubling — amortized append cost
- [ ] The aggregate method
- [ ] The accounting (banker's) method
- [ ] The potential method
- [ ] Recognizing when a single "expensive" op is masked by many cheap ones

## 💾 Space Complexity

- [ ] Auxiliary space vs. total space
- [ ] Call-stack space in recursive solutions
- [ ] In-place vs. out-of-place algorithms
- [ ] Space cost of common structures built during a solution (hashmap, extra array, visited set)
- [ ] Trading space for time (and vice versa) as a conscious choice

## 📈 Growth-rate Ladder

- [ ] I can order these from slowest- to fastest-growing and place any complexity on the ladder:
      O(1) ⊂ O(log n) ⊂ O(n) ⊂ O(n log n) ⊂ O(n²) ⊂ O(2ⁿ) ⊂ O(n!)
- [ ] I can say, for a given input size, which of these become impractical first

## 🧠 Complexity of Common Operations

I know the time complexity (average and worst case, where they differ) of:
- [ ] Array access, insert, delete (end vs. middle)
- [ ] Dynamic-array append (amortized)
- [ ] Hashmap / hashset get, put, delete
- [ ] Balanced BST insert, delete, search
- [ ] Heap push, pop, peek, build-heap
- [ ] Each common sort (bubble/insertion/selection, merge, quick, heap) — time and space, best/worst

---

## 🧩 Practice — analyze the complexity

> For each row, state the **time and space complexity** yourself (best/worst where they differ) and
> be ready to justify it — no answers are provided here by design.

| # | Analyze the time & space of… | Diff | Freq |
|:--|:--|:--:|:--:|
| 1 | A single loop from `0` to `n` | 🟢 | ⭐⭐⭐ |
| 2 | Two sequential (non-nested) loops, each to `n` | 🟢 | ⭐⭐⭐ |
| 3 | Two nested loops, both to `n` | 🟢 | ⭐⭐⭐ |
| 4 | A loop where the index doubles each iteration (`i *= 2`) | 🟢 | ⭐⭐ |
| 5 | Linear search vs. binary search on a sorted array | 🟢 | ⭐⭐⭐ |
| 6 | Building a hashmap in one pass, then a second pass over it | 🟡 | ⭐⭐⭐ |
| 7 | A nested loop where the inner loop runs `0` to `i` (triangular) | 🟡 | ⭐⭐ |
| 8 | Merge sort — recurrence and recursion-tree total | 🟡 | ⭐⭐⭐ |
| 9 | Quick sort — best/average vs. worst case | 🟡 | ⭐⭐ |
| 10 | Naive recursive Fibonacci vs. memoized Fibonacci | 🔴 | ⭐⭐⭐ |
| 11 | Recursion that makes two calls, each on half the input (`T(n) = 2T(n/2) + O(n)`) | 🔴 | ⭐⭐ |
| 12 | `n` `push_back` calls on a doubling dynamic array — amortized per-call cost | 🔴 | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given any code snippet, I can state its time & space complexity and defend the reasoning.
- [ ] I can set up and solve a recurrence using the recursion tree method or the Master Theorem.
- [ ] I can explain amortized analysis and derive the amortized cost of dynamic-array append.
- [ ] I know the time complexity of every common data-structure operation from memory — array,
      hashmap, BST, heap, and each common sort.
- [ ] I can place any given complexity correctly on the growth-rate ladder.

> Next in foundations → [Mathematics](03-mathematics.md).
