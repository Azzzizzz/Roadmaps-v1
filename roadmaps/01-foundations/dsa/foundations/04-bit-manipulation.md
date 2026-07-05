# 🧮 Bit Manipulation

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA roadmap](../../dsa.md) · [Guided path](../README.md) |
| **Status** | ✅ Complete |
| **Kind** | Foundation primer (checklist + practice) |
| **Scope** | bitwise operators + the classic bit problems |
| **Prerequisites** | [Programming Foundations](01-programming-foundations.md) · [Complexity Analysis](02-complexity-analysis.md) |
| **Next** | [Recursion & Divide-and-Conquer](05-recursion-divide-conquer.md) |

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Examples show intent (`input → output`), not solutions.

---

## 📖 Read this first

A handful of bitwise tricks turn an O(n) pass, an O(n) extra-space set, or a multiply/divide into an
O(1) or O(#bits) operation on the raw representation of a number. Interviewers reach for bit problems
to check you're comfortable one level below the standard library — not because production code needs
XOR swaps, but because "no extra space, no extra pass" often *is* the bit trick.

**How to use this file:** work the checklists top to bottom — each is a named operator or trick, not an
explanation. Look each one up until you can apply it cold, then check it off. Then work the practice
table easy → hard; the example only confirms you understood the question, you write the solution.

## ⚙️ Bitwise Operators

- [ ] AND (`&`)
- [ ] OR (`|`)
- [ ] XOR (`^`)
- [ ] NOT / bitwise complement (`~`)
- [ ] Left shift (`<<`)
- [ ] Right shift (`>>`) — arithmetic (sign-extending) vs. logical (zero-fill), and which one your language gives you by default

## 🔘 Single-bit Operations

- [ ] Get the i-th bit
- [ ] Set the i-th bit
- [ ] Clear the i-th bit
- [ ] Toggle the i-th bit
- [ ] Check whether the i-th bit is set

## 🛠️ Essential Tricks

- [ ] Isolate the lowest set bit: `x & -x`
- [ ] Clear the lowest set bit: `x & (x - 1)`
- [ ] Count set bits (popcount / Brian Kernighan's algorithm)
- [ ] Check if a number is a power of two
- [ ] Swap two variables without a temp (XOR swap)
- [ ] Multiply / divide by a power of two via shifts

## ⊕ XOR Patterns

- [ ] `a ^ a = 0` and `a ^ 0 = a` — self-cancellation and identity
- [ ] Find the single unique element among duplicates via XOR
- [ ] Find a missing element via XOR
- [ ] XOR of a range `[l, r]` (prefix-XOR trick)

## 🎭 Masks & Subset Enumeration

- [ ] Build a bitmask from a set of indices / flags
- [ ] Iterate all subsets of a given bitmask (submask enumeration)
- [ ] Use a bitmask to represent a set (membership, union, intersection, difference)
- [ ] Bitmask as DP state — pointer to [Dynamic Programming → Bitmask DP](../tier1-patterns/09-dynamic-programming.md)

---

## 🧩 Practice

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Number of 1 Bits (Hamming Weight) | 🟢 | `11 (1011) → 3` | ⭐⭐⭐ |
| 2 | Power of Two | 🟢 | `n=16 → true` | ⭐⭐⭐ |
| 3 | Complement of Base 10 Integer | 🟢 | `n=5 (101) → 2 (010)` | ⭐⭐ |
| 4 | Hamming Distance | 🟢 | `x=1, y=4 → 2` | ⭐⭐ |
| 5 | Single Number (others appear twice) | 🟢 | `[4,1,2,1,2] → 4` | ⭐⭐⭐ |
| 6 | Missing Number (0..n) | 🟢 | `[3,0,1] → 2` | ⭐⭐⭐ |
| 7 | Counting Bits (0..n) | 🟢 | `n=5 → [0,1,1,2,1,2]` | ⭐⭐ |
| 8 | Reverse Bits | 🟡 | `43261596 → 964176192` | ⭐⭐ |
| 9 | Add Binary | 🟡 | `"11", "1" → "100"` | ⭐⭐ |
| 10 | Sum of Two Integers (no `+` or `-`) | 🟡 | `a=2, b=3 → 5` | ⭐⭐⭐ |
| 11 | Single Number II (others appear thrice) | 🟡 | `[2,2,3,2] → 3` | ⭐⭐ |
| 12 | Single Number III (two uniques) | 🟡 | `[1,2,1,3,2,5] → [3,5]` | ⭐⭐ |
| 13 | Gray Code | 🟡 | `n=2 → [0,1,3,2]` | ⭐⭐ |
| 14 | Subsets (bitmask enumeration) | 🟡 | `[1,2,3] → [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]` | ⭐⭐⭐ |
| 15 | Maximum XOR of Two Numbers in an Array | 🔴 | `[3,10,5,25,2,8] → 28` | ⭐⭐ |
| 16 | Divide Two Integers (no `*`, `/`, or `%`) | 🔴 | `dividend=10, divisor=3 → 3` | ⭐⭐ |

> **See also:** row 14 (Subsets) gets its full exhaustive-search treatment in
> [Backtracking](../tier1-patterns/08-backtracking.md); row 15 (Maximum XOR) is often reached via a
> bitwise Trie rather than brute force.

---

## ✅ Definition of Done

- [ ] I can get, set, clear, and toggle any bit — and count set bits — without looking it up.
- [ ] I reach for XOR the moment a problem says "every element appears twice except one."
- [ ] I can isolate (`x & -x`) and clear (`x & (x-1)`) the lowest set bit from memory.
- [ ] I know when arithmetic right shift and logical right shift give different results.
- [ ] I can enumerate all subsets of a set (or all submasks of a mask) using a bitmask.

> Next in foundations → [Recursion & Divide-and-Conquer](05-recursion-divide-conquer.md).
