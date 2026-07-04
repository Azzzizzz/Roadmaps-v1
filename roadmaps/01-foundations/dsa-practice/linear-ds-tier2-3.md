# 📝 Arrays, Strings, Hashing & Linear DS — Tier 2 / Tier 3 Question Bank

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) |
| **Status** | ✅ Complete |
| **Scope** | Arrays · Strings · Hashing (maps/sets) · Linked List · Stack/Queue |
| **Targets** | Tier-2 / Tier-3 companies · startups · service-based & mid MNCs |
| **Questions** | 111 &nbsp;→&nbsp; arrays × 30 · strings × 30 · hashing × 15 · linked list × 12 · stack × 12 · queue × 12 |
| **Related** | [Interview Prep](../../00-meta/interview-preparation.md) |

> **Legend** — Difficulty: 🟢 easy · 🟡 easy-medium &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Examples show **intent** (`input → output`), *not* solutions.
> _Hash maps aren't strictly "linear", but Tier-2/3 rounds bundle them with array/string work — so they get their own section._

---

## 🗺️ What this is

> A curated, ranked list of the **highest-probability questions** for Tier-2/Tier-3 and
> startup interviews. These rounds rarely go past arrays, strings, hashing, and basic linked
> list / stack / queue — this sheet is weighted to match (arrays + strings + hashmaps = ~75%).

**How to use:** work top-down within each table (ordered by frequency). Clear every ⭐⭐⭐ row
first — those are near-guaranteed. Solve from the prompt; use the example only to confirm you
understood the question, not to reverse-engineer the answer.

## 🔑 Core patterns that unlock most of the list

Master these and you can attack ~90% of these questions:

- **Two pointers** (opposite ends / in-place / same-direction)
- **Hashing** — frequency map, set membership, index map
- **Prefix sum** (+ hashmap for subarray-sum problems)
- **Sliding window** (fixed and variable size)
- **Fast & slow pointers** (linked lists)
- **In-place reversal**
- **Stack** (LIFO matching / monotonic stack)

---

## 🔢 Arrays (30)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Two Sum — return indices | Hashing | 🟢 | `[2,7,11,15], t=9 → [0,1]` | ⭐⭐⭐ |
| 2 | Reverse an array in place | Two pointers | 🟢 | `[1,2,3,4] → [4,3,2,1]` | ⭐⭐⭐ |
| 3 | Find max & min in one pass | Linear scan | 🟢 | `[3,1,9,4] → min 1, max 9` | ⭐⭐⭐ |
| 4 | Second largest element | Single pass | 🟢 | `[10,5,8,10,2] → 8` | ⭐⭐⭐ |
| 5 | Missing number (1..n) | Sum / XOR | 🟢 | `[1,2,4,5], n=5 → 3` | ⭐⭐⭐ |
| 6 | Move all zeroes to end | Two pointers | 🟢 | `[0,1,0,3,12] → [1,3,12,0,0]` | ⭐⭐⭐ |
| 7 | Maximum subarray sum | Kadane's | 🟡 | `[-2,1,-3,4,-1,2,1,-5,4] → 6` | ⭐⭐⭐ |
| 8 | Remove duplicates (sorted) | Two pointers | 🟢 | `[1,1,2,2,3] → [1,2,3] (len 3)` | ⭐⭐⭐ |
| 9 | Rotate array by k | Reversal trick | 🟡 | `[1,2,3,4,5], k=2 → [4,5,1,2,3]` | ⭐⭐⭐ |
| 10 | Best time to buy & sell stock | Single pass | 🟢 | `[7,1,5,3,6,4] → 5` | ⭐⭐⭐ |
| 11 | Majority element (> n/2) | Boyer-Moore | 🟡 | `[3,3,4,2,3,3,3] → 3` | ⭐⭐⭐ |
| 12 | Find the duplicate number | Hashing | 🟢 | `[1,3,4,2,2] → 2` | ⭐⭐⭐ |
| 13 | Single number (others twice) | XOR | 🟢 | `[4,1,2,1,2] → 4` | ⭐⭐⭐ |
| 14 | Sort 0s, 1s, 2s (Dutch flag) | Three pointers | 🟡 | `[2,0,2,1,1,0] → [0,0,1,1,2,2]` | ⭐⭐⭐ |
| 15 | Pair with given sum (sorted) | Two pointers | 🟢 | `[1,2,4,7], t=6 → (2,4)` | ⭐⭐⭐ |
| 16 | Max sum subarray of size k | Fixed window | 🟢 | `[2,1,5,1,3,2], k=3 → 9` | ⭐⭐⭐ |
| 17 | Merge two sorted arrays | Merge | 🟢 | `[1,3,5] + [2,4,6] → [1,2,3,4,5,6]` | ⭐⭐ |
| 18 | Product of array except self | Prefix / suffix | 🟡 | `[1,2,3,4] → [24,12,8,6]` | ⭐⭐ |
| 19 | Leaders in an array | Reverse scan | 🟢 | `[16,17,4,3,5,2] → [17,5,2]` | ⭐⭐ |
| 20 | Equilibrium / pivot index | Prefix sum | 🟢 | `[1,7,3,6,5,6] → 3` | ⭐⭐ |
| 21 | Max consecutive ones | Scan | 🟢 | `[1,1,0,1,1,1] → 3` | ⭐⭐ |
| 22 | Intersection of two arrays | Hashing / set | 🟢 | `[1,2,2,1],[2,2] → [2]` | ⭐⭐ |
| 23 | Union of two arrays | Hashing / set | 🟢 | `[1,2,3],[2,3,4] → [1,2,3,4]` | ⭐⭐ |
| 24 | Subarray with given sum (positives) | Sliding window | 🟡 | `[1,2,3,7,5], t=12 → [2,4]` | ⭐⭐ |
| 25 | Running / prefix sum | Prefix sum | 🟢 | `[1,2,3,4] → [1,3,6,10]` | ⭐⭐ |
| 26 | Kth largest element (small n) | Sort / heap | 🟢 | `[3,2,1,5,6,4], k=2 → 5` | ⭐⭐ |
| 27 | Count pairs with sum k | Hashing | 🟢 | `[1,5,7,1], k=6 → 2` | ⭐⭐ |
| 28 | Rearrange +/- alternately | Two pointers | 🟡 | `[1,2,3,-4,-1,4] → [-4,1,-1,2,3,4]` | ⭐⭐ |
| 29 | Find missing & repeating | Math / hashing | 🟡 | `[3,1,3] → repeat 3, missing 2` | ⭐⭐ |
| 30 | Max product of two elements | Scan | 🟢 | `[3,4,5,2] → 20` | ⭐ |

## 🔤 Strings (30)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Reverse a string | Two pointers | 🟢 | `"hello" → "olleh"` | ⭐⭐⭐ |
| 2 | Check palindrome | Two pointers | 🟢 | `"racecar" → true · "hello" → false` | ⭐⭐⭐ |
| 3 | Valid anagram | Hashing / count | 🟢 | `"listen","silent" → true` | ⭐⭐⭐ |
| 4 | First non-repeating character | Frequency map | 🟢 | `"leetcode" → 'l'` | ⭐⭐⭐ |
| 5 | Longest substring w/o repeats | Sliding window | 🟡 | `"abcabcbb" → 3 ("abc")` | ⭐⭐⭐ |
| 6 | Reverse words in a string | Split / two pointers | 🟢 | `"the sky is blue" → "blue is sky the"` | ⭐⭐⭐ |
| 7 | Longest common prefix | Vertical scan | 🟢 | `["flower","flow","flight"] → "fl"` | ⭐⭐⭐ |
| 8 | Valid palindrome (alphanumeric only) | Two pointers | 🟢 | `"A man, a plan, a canal: Panama" → true` | ⭐⭐⭐ |
| 9 | Group anagrams | Hashing | 🟡 | `["eat","tea","tan"] → [[eat,tea],[tan]]` | ⭐⭐⭐ |
| 10 | Balanced parentheses in string | Stack | 🟢 | `"(a[b]{c})" → true` | ⭐⭐⭐ |
| 11 | Character frequency count | Hashing | 🟢 | `"aabbbc" → a:2, b:3, c:1` | ⭐⭐ |
| 12 | String rotation check | Concatenation trick | 🟢 | `"abcde","cdeab" → true` | ⭐⭐ |
| 13 | String compression (RLE) | Counting / two pointers | 🟡 | `"aaabbc" → "a3b2c1"` | ⭐⭐ |
| 14 | Count vowels & consonants | Scan | 🟢 | `"hello" → vowels 2, consonants 3` | ⭐⭐ |
| 15 | Remove duplicate characters | Hashing / set | 🟢 | `"programming" → "progamin"` | ⭐⭐ |
| 16 | Check if all characters unique | Set / bitmask | 🟢 | `"abcde" → true · "hello" → false` | ⭐⭐ |
| 17 | Most frequent character | Frequency map | 🟢 | `"success" → 's'` | ⭐⭐ |
| 18 | Isomorphic strings | Hashing | 🟡 | `"egg","add" → true` | ⭐⭐ |
| 19 | Implement strStr (substring index) | Scan / KMP | 🟢 | `"hello","ll" → 2` | ⭐⭐ |
| 20 | Count occurrences of a substring | Scan | 🟢 | `"ababab","ab" → 3` | ⭐⭐ |
| 21 | Count words in a string | Scan | 🟢 | `"the sky is blue" → 4` | ⭐⭐ |
| 22 | First repeating character | Set | 🟢 | `"abca" → 'a'` | ⭐⭐ |
| 23 | Longest palindromic substring | Expand around center | 🟡 | `"babad" → "bab"` | ⭐⭐ |
| 24 | Capitalize first letter of each word | Scan | 🟢 | `"hello world" → "Hello World"` | ⭐ |
| 25 | Remove all whitespace | Scan | 🟢 | `"a b c" → "abc"` | ⭐ |
| 26 | Longest word in a sentence | Scan | 🟢 | `"I love programming" → "programming"` | ⭐ |
| 27 | String to integer (atoi, basic) | Parsing | 🟡 | `"  -42" → -42` | ⭐⭐ |
| 28 | Reverse only the vowels | Two pointers | 🟢 | `"hello" → "holle"` | ⭐ |
| 29 | Check two strings equal ignoring case | Scan | 🟢 | `"Hello","hello" → true` | ⭐ |
| 30 | Sort characters of a string | Sorting / count | 🟢 | `"dcba" → "abcd"` | ⭐ |

## 🗂️ Hashing / Hashmaps (15)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Frequency count of elements | Frequency map | 🟢 | `[1,2,2,3,3,3] → {1:1, 2:2, 3:3}` | ⭐⭐⭐ |
| 2 | First non-repeating element (array) | Frequency map | 🟢 | `[9,4,9,6,7,4] → 6` | ⭐⭐⭐ |
| 3 | Subarray sum equals K | Prefix sum + map | 🟡 | `[1,1,1], k=2 → 2` | ⭐⭐⭐ |
| 4 | Longest consecutive sequence | Hash set | 🟡 | `[100,4,200,1,3,2] → 4` | ⭐⭐⭐ |
| 5 | Top K frequent elements | Map + heap/bucket | 🟡 | `[1,1,1,2,2,3], k=2 → [1,2]` | ⭐⭐⭐ |
| 6 | Find all duplicates in array | Hashing | 🟢 | `[4,3,2,7,8,2,3,1] → [2,3]` | ⭐⭐ |
| 7 | Count distinct elements | Set | 🟢 | `[1,2,2,3] → 3` | ⭐⭐ |
| 8 | Pair with given difference | Hashing | 🟢 | `[5,20,3,2,50], d=17 → (3,20)` | ⭐⭐ |
| 9 | Longest subarray with sum K | Prefix + map | 🟡 | `[10,5,2,7,1,9], k=15 → 4` | ⭐⭐ |
| 10 | Subarray with 0 sum exists | Prefix + set | 🟡 | `[4,2,-3,1,6] → true` | ⭐⭐ |
| 11 | Count pairs with given sum | Hashing | 🟢 | `[1,5,7,1], k=6 → 2` | ⭐⭐ |
| 12 | Anagram check (two strings) | Frequency map | 🟢 | `"anagram","nagaram" → true` | ⭐⭐ |
| 13 | Isomorphic strings | Two maps | 🟡 | `"egg","add" → true` | ⭐⭐ |
| 14 | Longest substring w/ ≤ K distinct | Sliding window + map | 🟡 | `"eceba", k=2 → 3 ("ece")` | ⭐⭐ |
| 15 | Majority element (map count) | Frequency map | 🟢 | `[3,3,4,2,3] → 3` | ⭐⭐ |

## 🔗 Linked List (12)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Reverse a linked list | Pointer reversal | 🟢 | `1→2→3→null → 3→2→1→null` | ⭐⭐⭐ |
| 2 | Detect a cycle / loop | Floyd's fast/slow | 🟡 | `1→2→3→(back to 2) → true` | ⭐⭐⭐ |
| 3 | Find the middle node | Fast / slow pointers | 🟢 | `1→2→3→4→5 → 3` | ⭐⭐⭐ |
| 4 | Merge two sorted lists | Merge | 🟢 | `1→3→5 , 2→4→6 → 1→2→3→4→5→6` | ⭐⭐⭐ |
| 5 | Remove Nth node from end | Two pointers | 🟡 | `1→2→3→4→5, n=2 → 1→2→3→5` | ⭐⭐⭐ |
| 6 | Detect & remove a loop | Floyd's | 🟡 | `looped list → list without loop` | ⭐⭐ |
| 7 | Check if list is palindrome | Reverse half | 🟡 | `1→2→2→1 → true` | ⭐⭐ |
| 8 | Remove duplicates from sorted list | Traversal | 🟢 | `1→1→2→3→3 → 1→2→3` | ⭐⭐ |
| 9 | Delete a node (given only that node) | Pointer copy | 🟢 | `1→2→3→4, delete 3 → 1→2→4` | ⭐⭐ |
| 10 | Intersection point of two lists | Two pointers | 🟡 | `lists meeting at 8 → 8` | ⭐⭐ |
| 11 | Nth node from beginning | Traversal | 🟢 | `1→2→3→4, n=2 → 2` | ⭐ |
| 12 | Count nodes / length | Traversal | 🟢 | `1→2→3 → 3` | ⭐ |

## 🥞 Stacks (12)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Valid parentheses | Stack | 🟢 | `"({[]})" → true · "(]" → false` | ⭐⭐⭐ |
| 2 | Min stack — getMin in O(1) | Stack + aux stack | 🟡 | `push 5,2,1 → getMin → 1` | ⭐⭐⭐ |
| 3 | Next greater element | Monotonic stack | 🟡 | `[4,5,2,25] → [5,25,25,-1]` | ⭐⭐⭐ |
| 4 | Implement stack using array | Array | 🟢 | `push/pop/peek → LIFO order` | ⭐⭐⭐ |
| 5 | Stack using two queues | Two queues | 🟡 | `push 1,2 → pop → 2` | ⭐⭐ |
| 6 | Evaluate postfix expression | Stack | 🟡 | `"231*+9-" → -4` | ⭐⭐ |
| 7 | Infix to postfix conversion | Stack | 🟡 | `"a+b*c" → "abc*+"` | ⭐⭐ |
| 8 | Reverse a stack (recursion) | Stack + recursion | 🟡 | `[1,2,3] → [3,2,1]` | ⭐⭐ |
| 9 | Redundant / balanced brackets | Stack | 🟢 | `"(a+b)" → true · "((a))" → redundant` | ⭐⭐ |
| 10 | Stock span problem | Monotonic stack | 🟡 | `[100,80,60,70,60,75,85] → [1,1,1,2,1,4,6]` | ⭐⭐ |
| 11 | Nearest smaller element to left | Monotonic stack | 🟢 | `[1,6,2] → [-1,1,1]` | ⭐⭐ |
| 12 | Sort a stack | Stack | 🟡 | `[3,1,2] → [1,2,3]` | ⭐ |

## 🚚 Queues (12)

| # | Question | Pattern | Diff | Example `input → output` | Freq |
|:--|:--|:--|:--:|:--|:--:|
| 1 | Implement queue using two stacks | Two stacks | 🟡 | `enqueue 1,2 → dequeue → 1` | ⭐⭐⭐ |
| 2 | Implement queue using array | Array | 🟢 | `enqueue/dequeue → FIFO order` | ⭐⭐⭐ |
| 3 | Circular queue implementation | Array wrap-around | 🟡 | `enqueue/dequeue wrapping → correct order` | ⭐⭐⭐ |
| 4 | First non-repeating char in a stream | Queue + freq map | 🟡 | `"aabc" → 'b'` | ⭐⭐⭐ |
| 5 | Reverse a queue | Queue + stack/recursion | 🟢 | `[1,2,3] → [3,2,1]` | ⭐⭐ |
| 6 | Reverse first k elements of a queue | Queue + stack | 🟡 | `[1,2,3,4,5], k=3 → [3,2,1,4,5]` | ⭐⭐ |
| 7 | Generate binary numbers 1..n | Queue (BFS) | 🟢 | `n=3 → ["1","10","11"]` | ⭐⭐ |
| 8 | Implement a deque | Array / doubly linked | 🟢 | `pushFront/pushBack/popFront/popBack → correct ends` | ⭐⭐ |
| 9 | Sliding window maximum | Deque (monotonic) | 🟡 | `[1,3,-1,-3,5,3,6,7], k=3 → [3,3,5,5,6,7]` | ⭐⭐ |
| 10 | Priority queue basics (insert / extract-min) | Heap / PQ | 🟢 | `insert 5,1,3 → extractMin → 1` | ⭐⭐ |
| 11 | Interleave first & second half of a queue | Queue + stack | 🟡 | `[1,2,3,4] → [1,3,2,4]` | ⭐ |
| 12 | LRU cache (deque + hashmap) | Deque + map | 🟡 | `cap=2, get/put ops → evicts LRU` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] I can solve **every ⭐⭐⭐ question in under ~15 min** without hints.
- [ ] For each, I can name the **pattern** used and state its time/space complexity.
- [ ] I handle the **edge cases** (empty, single element, all-same, negatives, duplicates).
- [ ] I can dry-run my solution on the example `input → output` out loud.

> **Next step after this sheet:** clear the ⭐⭐ rows, then move to non-linear basics
> (recursion, trees, basic graphs) in the main [DSA Roadmap](../dsa.md).
