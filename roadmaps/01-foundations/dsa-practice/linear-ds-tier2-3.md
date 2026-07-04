# 📝 Linear Data Structures — Tier 2 / Tier 3 Question Bank

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) |
| **Status** | ✅ Complete |
| **Scope** | Linear DS only — arrays · strings · linked list · stack · queue |
| **Targets** | Tier-2 / Tier-3 companies · startups · service-based & mid MNCs |
| **Questions** | 24 &nbsp;→&nbsp; arrays × 10 · strings × 8 · linked list × 3 · stack/queue × 3 |
| **Related** | [Interview Prep](../../00-meta/interview-preparation.md) |

> **Legend** — Difficulty: 🟢 easy · 🟡 easy-medium &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Examples show **intent** (`input → output`), *not* solutions.

---

## 🗺️ What this is

> A curated, ranked list of the **highest-probability linear-DS questions** for Tier-2/Tier-3
> and startup interviews — where rounds rarely go past arrays, strings, and basic linked
> list / stack / queue. Practice these first; they cover the bulk of what these companies ask.

**How to use:** work top-down within each table (ordered by frequency). Start with every
⭐⭐⭐ row — those are near-guaranteed. Solve from the prompt; use the example only to confirm
you understood the question, not to reverse-engineer the answer.

## 🔑 Core patterns that unlock most of the list

Master these six and you can attack ~90% of these questions:

- **Two pointers** (opposite ends / in-place)
- **Hashing / frequency map**
- **Sliding window**
- **Fast & slow pointers**
- **In-place reversal**
- **Stack** (LIFO matching)

---

## 🔢 Arrays (10)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Two Sum — return indices | Hashing | 🟢 | `nums=[2,7,11,15], target=9 → [0,1]` | ⭐⭐⭐ |
| 2 | Reverse an array in place | Two pointers | 🟢 | `[1,2,3,4] → [4,3,2,1]` | ⭐⭐⭐ |
| 3 | Find max & min in one pass | Linear scan | 🟢 | `[3,1,9,4] → min 1, max 9` | ⭐⭐⭐ |
| 4 | Second largest element | Single pass | 🟢 | `[10,5,8,10,2] → 8` | ⭐⭐⭐ |
| 5 | Missing number (1..n) | Sum / XOR | 🟢 | `[1,2,4,5], n=5 → 3` | ⭐⭐⭐ |
| 6 | Move all zeroes to end | Two pointers (in-place) | 🟢 | `[0,1,0,3,12] → [1,3,12,0,0]` | ⭐⭐⭐ |
| 7 | Maximum subarray sum | Kadane's | 🟡 | `[-2,1,-3,4,-1,2,1,-5,4] → 6` | ⭐⭐⭐ |
| 8 | Remove duplicates (sorted) | Two pointers | 🟢 | `[1,1,2,2,3] → [1,2,3] (len 3)` | ⭐⭐ |
| 9 | Rotate array by k | Reversal trick | 🟡 | `[1,2,3,4,5], k=2 → [4,5,1,2,3]` | ⭐⭐ |
| 10 | Merge two sorted arrays | Merge / two pointers | 🟢 | `[1,3,5] + [2,4,6] → [1,2,3,4,5,6]` | ⭐⭐ |

## 🔤 Strings (8)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 11 | Check palindrome | Two pointers | 🟢 | `"racecar" → true · "hello" → false` | ⭐⭐⭐ |
| 12 | Valid anagram | Hashing / count | 🟢 | `"listen","silent" → true` | ⭐⭐⭐ |
| 13 | First non-repeating character | Frequency map | 🟢 | `"leetcode" → 'l'` | ⭐⭐⭐ |
| 14 | Longest substring w/o repeats | Sliding window | 🟡 | `"abcabcbb" → 3 ("abc")` | ⭐⭐⭐ |
| 15 | Character frequency count | Hashing | 🟢 | `"aabbbc" → a:2, b:3, c:1` | ⭐⭐ |
| 16 | Reverse words in a string | Split / two pointers | 🟢 | `"the sky is blue" → "blue is sky the"` | ⭐⭐ |
| 17 | String rotation check | Concatenation trick | 🟢 | `"abcde","cdeab" → true` | ⭐⭐ |
| 18 | String compression (RLE) | Counting / two pointers | 🟡 | `"aaabbc" → "a3b2c1"` | ⭐⭐ |

## 🔗 Linked List (3)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 19 | Reverse a linked list | Pointer reversal | 🟢 | `1→2→3→null → 3→2→1→null` | ⭐⭐⭐ |
| 20 | Detect a cycle / loop | Floyd's fast/slow | 🟡 | `1→2→3→(back to 2) → true` | ⭐⭐⭐ |
| 21 | Find the middle node | Fast / slow pointers | 🟢 | `1→2→3→4→5 → 3` | ⭐⭐ |

## 🥞 Stack / Queue (3)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 22 | Valid parentheses | Stack | 🟢 | `"({[]})" → true · "(]" → false` | ⭐⭐⭐ |
| 23 | Min stack — getMin in O(1) | Stack + aux stack | 🟡 | `push 5,2,1 → getMin → 1` | ⭐⭐ |
| 24 | Queue using two stacks | Stack / queue | 🟡 | `enqueue 1,2 → dequeue → 1` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] I can solve **every ⭐⭐⭐ question in under ~15 min** without hints.
- [ ] For each, I can name the **pattern** I used and state its time/space complexity.
- [ ] I can handle the **edge cases** (empty input, single element, all-same, negatives).
- [ ] I can dry-run my solution on the example `input → output` out loud.

> **Next step after this sheet:** the ⭐⭐ rows, then jump to non-linear basics
> (hashing depth, recursion, trees) in the main [DSA Roadmap](../dsa.md).
