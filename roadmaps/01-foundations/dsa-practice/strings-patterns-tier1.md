# 🎯 Strings — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) · [Arrays Patterns](arrays-patterns-tier1.md) · [Tier-2/3 Bank](linear-ds-tier2-3.md) |
| **Status** | ✅ Complete — Strings (2nd in the Tier-1 pattern series) |
| **Scope** | Strings — organized by **algorithmic pattern**, Tier-1 / MAANG difficulty |
| **Targets** | Tier-1 product companies · MAANG / FAANG |
| **Coverage** | 8 in-file patterns · 72 questions (String DP → [DP bank](dp-patterns-tier1.md#p6) · Backtracking → [BT bank](backtracking-patterns-tier1.md)) |
| **Related** | Next in series → `trees-patterns-tier1.md`, `graphs-patterns-tier1.md`, … |

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Rows are ordered **easy → hard within each pattern**. Examples show **intent** (`input → output`), *not* solutions.

---

## 🗺️ How to use this bank

> Strings at Tier-1/MAANG lean heavily on **sliding window** and **DP** — but the meta-skill is the
> same as arrays: map an unseen problem to a pattern in under a minute.

**Workflow:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down (easy → hard).
Internalize the *trigger*, not the solution.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [Sliding Window](#p1) | 12 | longest/shortest substring with a constraint · anagrams/permutations · at-most-K distinct |
| 2 | [Two Pointers](#p2) | 10 | palindrome checks · reverse in place · compare/merge from both ends |
| 3 | [Hashing / Frequency Map](#p3) | 10 | anagrams · char counts · group by signature · char-to-char mapping |
| 4 | [DP on Strings → DP bank](dp-patterns-tier1.md#p6) | — | *moved* — DP is a paradigm; String DP lives in the DP bank |
| 5 | [Palindrome Techniques](#p5) | 10 | longest/count palindromic substrings · partition into palindromes · make a palindrome |
| 6 | [Stack-Based](#p6) | 8 | nested/matching brackets · decode · remove adjacent · evaluate expressions |
| 7 | [Backtracking → BT bank](backtracking-patterns-tier1.md) | — | *moved* — backtracking is a paradigm; lives in the Backtracking bank |
| 8 | [Parsing / Simulation](#p8) | 8 | convert a formatted string · roman/atoi · add/multiply as strings |
| 9 | [Trie / Prefix](#p9) | 8 | many prefix queries · dictionary of words · autocomplete · word search on a grid |
| 10 | [String Matching](#p10) | 6 | find a pattern in text · repeated patterns · prefix-function (KMP) / rolling hash |

---

<a id="p1"></a>
## 1 · Sliding Window (12)

> 🔍 **Recognize it when…** the answer is a *contiguous substring* and you want the longest/shortest,
> an at-most-K-distinct constraint, or to match an anagram/permutation of a pattern.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Longest Substring Without Repeating Characters | 🟡 | `"abcabcbb" → 3` | ⭐⭐⭐ |
| 2 | Find All Anagrams in a String | 🟡 | `s="cbaebabacd", p="abc" → [0,6]` | ⭐⭐⭐ |
| 3 | Permutation in String | 🟡 | `s1="ab", s2="eidbaooo" → true` | ⭐⭐⭐ |
| 4 | Longest Repeating Character Replacement | 🟡 | `"AABABBA", k=1 → 4` | ⭐⭐⭐ |
| 5 | Longest Substring with At Most Two Distinct | 🟡 | `"eceba" → 3` | ⭐⭐ |
| 6 | Longest Substring with At Most K Distinct | 🟡 | `"aabacbebebe", k=3 → 7` | ⭐⭐ |
| 7 | Max Number of Vowels in a Substring of Length k | 🟡 | `"abciiidef", k=3 → 3` | ⭐⭐ |
| 8 | Number of Substrings Containing All Three Chars | 🟡 | `"abcabc" → 10` | ⭐⭐ |
| 9 | Replace the Substring for Balanced String | 🟡 | `"QWER" → 0` | ⭐⭐ |
| 10 | Substring with Concatenation of All Words | 🔴 | `s="barfoothefoobarman", words=["foo","bar"] → [0,9]` | ⭐⭐ |
| 11 | Minimum Window Substring | 🔴 | `s="ADOBECODEBANC", t="ABC" → "BANC"` | ⭐⭐⭐ |
| 12 | Minimum Window Subsequence | 🔴 | `s="abcdebdde", t="bde" → "bcde"` | ⭐⭐ |

<a id="p2"></a>
## 2 · Two Pointers (10)

> 🔍 **Recognize it when…** you compare characters from both ends (palindromes), reverse in place, or
> walk two indices to skip/merge.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Reverse String | 🟢 | `["h","e","l","l","o"] → ["o","l","l","e","h"]` | ⭐⭐ |
| 2 | Valid Palindrome | 🟢 | `"A man, a plan, a canal: Panama" → true` | ⭐⭐⭐ |
| 3 | Reverse Vowels of a String | 🟢 | `"hello" → "holle"` | ⭐⭐ |
| 4 | Is Subsequence | 🟢 | `s="abc", t="ahbgdc" → true` | ⭐⭐ |
| 5 | Merge Strings Alternately | 🟢 | `"abc","pqr" → "apbqcr"` | ⭐⭐ |
| 6 | Valid Palindrome II (delete at most one) | 🟡 | `"abca" → true` | ⭐⭐⭐ |
| 7 | Reverse Words in a String | 🟡 | `"the sky is blue" → "blue is sky the"` | ⭐⭐⭐ |
| 8 | String Compression (in place) | 🟡 | `["a","a","b","b","c","c","c"] → "a2b2c3"` | ⭐⭐ |
| 9 | Backspace String Compare | 🟡 | `"ab#c","ad#c" → true` | ⭐⭐ |
| 10 | Shortest Distance to a Character | 🟡 | `"loveleetcode", 'e' → [3,2,1,0,1,0,0,1,2,2,1,0]` | ⭐⭐ |

<a id="p3"></a>
## 3 · Hashing / Frequency Map (10)

> 🔍 **Recognize it when…** you need character counts, to detect anagrams, group by a signature, or
> map one character set onto another.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Valid Anagram | 🟢 | `"anagram","nagaram" → true` | ⭐⭐⭐ |
| 2 | First Unique Character in a String | 🟢 | `"leetcode" → 0` | ⭐⭐⭐ |
| 3 | Ransom Note | 🟢 | `"aa","aab" → true` | ⭐⭐ |
| 4 | Find the Difference | 🟢 | `"abcd","abcde" → "e"` | ⭐⭐ |
| 5 | Maximum Number of Balloons | 🟢 | `"loonbalxballpoon" → 2` | ⭐⭐ |
| 6 | Group Anagrams | 🟡 | `["eat","tea","tan","ate","nat","bat"] → [[eat,tea,ate],[tan,nat],[bat]]` | ⭐⭐⭐ |
| 7 | Isomorphic Strings | 🟡 | `"egg","add" → true` | ⭐⭐⭐ |
| 8 | Word Pattern | 🟡 | `pattern="abba", s="dog cat cat dog" → true` | ⭐⭐ |
| 9 | Sort Characters By Frequency | 🟡 | `"tree" → "eert"` | ⭐⭐ |
| 10 | Determine if Two Strings Are Close | 🟡 | `"abc","bca" → true` | ⭐⭐ |

<a id="p4"></a>
## 4 · Dynamic Programming on Strings → moved to the DP bank

> 🧭 **String DP now lives in its canonical home:** [Dynamic Programming bank → String DP](dp-patterns-tier1.md#p6).
> That's where the full easy→hard ramp is — Longest Common Subsequence, Edit Distance, Distinct
> Subsequences, Interleaving String, Regular Expression & Wildcard Matching, and more.
>
> **Why moved:** DP is a *paradigm*, not a string technique. Keeping every DP pattern in one file
> (one home per problem, per [CLAUDE.md](../../../CLAUDE.md)) lets you study String DP alongside Grid DP,
> Knapsack, and LIS instead of in isolation.

<a id="p5"></a>
## 5 · Palindrome Techniques (10)

> 🔍 **Recognize it when…** the problem is about palindromic substrings (expand around center),
> partitioning into palindromes, or minimally editing a string into a palindrome.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Longest Palindrome (build from chars) | 🟢 | `"abccccdd" → 7` | ⭐⭐ |
| 2 | Longest Palindromic Substring | 🟡 | `"babad" → "bab"` | ⭐⭐⭐ |
| 3 | Palindromic Substrings (count) | 🟡 | `"aaa" → 6` | ⭐⭐⭐ |
| 4 | Longest Palindromic Subsequence | 🟡 | `"bbbab" → 4` | ⭐⭐ |
| 5 | Palindrome Partitioning (all) | 🟡 | `"aab" → [["a","a","b"],["aa","b"]]` | ⭐⭐⭐ |
| 6 | Minimum Insertion Steps to Make a Palindrome | 🟡 | `"leetcode" → 5` | ⭐⭐ |
| 7 | Palindrome Partitioning II (min cuts) | 🔴 | `"aab" → 1` | ⭐⭐ |
| 8 | Shortest Palindrome | 🔴 | `"aacecaaa" → "aaacecaaa"` | ⭐⭐ |
| 9 | Count Different Palindromic Subsequences | 🔴 | `"bccb" → 6` | ⭐ |
| 10 | Palindrome Pairs | 🔴 | `["abcd","dcba","lls","s"] → [[0,1],[1,0],[2,4],…]` | ⭐⭐ |

<a id="p6"></a>
## 6 · Stack-Based (8)

> 🔍 **Recognize it when…** you handle nested/matching brackets, decode a nested-encoded string,
> collapse adjacent duplicates, or evaluate an expression.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Valid Parentheses | 🟢 | `"()[]{}" → true` | ⭐⭐⭐ |
| 2 | Remove All Adjacent Duplicates In String | 🟢 | `"abbaca" → "ca"` | ⭐⭐ |
| 3 | Remove Outermost Parentheses | 🟢 | `"(()())(())" → "()()()"` | ⭐⭐ |
| 4 | Minimum Remove to Make Valid Parentheses | 🟡 | `"lee(t(c)o)de)" → "lee(t(c)o)de"` | ⭐⭐⭐ |
| 5 | Decode String | 🟡 | `"3[a]2[bc]" → "aaabcbc"` | ⭐⭐⭐ |
| 6 | Remove All Adjacent Duplicates in String II (k) | 🟡 | `"deeedbbcccbdaa", k=3 → "aa"` | ⭐⭐ |
| 7 | Basic Calculator II | 🟡 | `"3+2*2" → 7` | ⭐⭐⭐ |
| 8 | Basic Calculator | 🔴 | `"(1+(4+5+2)-3)+(6+8)" → 23` | ⭐⭐ |

<a id="p7"></a>
## 7 · Backtracking → moved to the Backtracking bank

> 🧭 **String backtracking now lives in its canonical home:** [Backtracking bank](backtracking-patterns-tier1.md).
> Generate Parentheses, Letter Combinations, Restore IP Addresses, String Permutations, Word Search,
> Word Break II, Expression Add Operators — all there, grouped with their non-string siblings
> (subsets, permutations, N-Queens, partitioning) so you learn the paradigm as one thing.
>
> **Why moved:** backtracking is a *paradigm*, not a string technique (one home per problem, per
> [CLAUDE.md](../../../CLAUDE.md)).

<a id="p8"></a>
## 8 · Parsing / Simulation (8)

> 🔍 **Recognize it when…** you interpret or convert a *formatted* string — numeral systems, integer
> parsing, or arithmetic performed directly on string digits.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Roman to Integer | 🟢 | `"MCMXCIV" → 1994` | ⭐⭐⭐ |
| 2 | Length of Last Word | 🟢 | `"Hello World" → 5` | ⭐⭐ |
| 3 | Add Strings | 🟢 | `"11","123" → "134"` | ⭐⭐ |
| 4 | Add Binary | 🟢 | `"11","1" → "100"` | ⭐⭐ |
| 5 | Integer to Roman | 🟡 | `1994 → "MCMXCIV"` | ⭐⭐ |
| 6 | String to Integer (atoi) | 🟡 | `"   -42" → -42` | ⭐⭐⭐ |
| 7 | Multiply Strings | 🟡 | `"123","456" → "56088"` | ⭐⭐⭐ |
| 8 | Compare Version Numbers | 🟡 | `"1.01","1.001" → 0` | ⭐⭐ |

<a id="p9"></a>
## 9 · Trie / Prefix (8)

> 🔍 **Recognize it when…** there are many prefix queries, a dictionary of words to search, autocomplete,
> or a grid word-search that benefits from a shared prefix tree.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Implement Trie (Prefix Tree) | 🟡 | `insert/search/startsWith → booleans` | ⭐⭐⭐ |
| 2 | Design Add and Search Words (with '.') | 🟡 | `addWord("bad"), search("b.d") → true` | ⭐⭐⭐ |
| 3 | Replace Words | 🟡 | `dict=["cat","rat"], "the cattle was rattled" → "the cat was rat"` | ⭐⭐ |
| 4 | Longest Word in Dictionary | 🟡 | `["w","wo","wor","worl","world"] → "world"` | ⭐⭐ |
| 5 | Map Sum Pairs | 🟡 | `insert("apple",3); sum("ap") → 3` | ⭐⭐ |
| 6 | Word Search II (trie + DFS) | 🔴 | `board, words → matched words` | ⭐⭐⭐ |
| 7 | Concatenated Words | 🔴 | `["cat","cats","dog","catsdog"] → ["catsdog"]` | ⭐⭐ |
| 8 | Stream of Characters | 🔴 | `query('a') after words → true if suffix is a word` | ⭐⭐ |

<a id="p10"></a>
## 10 · String Matching — KMP / Rabin-Karp (6)

> 🔍 **Recognize it when…** you search for a pattern inside text, detect repeated/periodic structure,
> or need a prefix-function (KMP) or rolling hash (Rabin-Karp).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Implement strStr() / First Occurrence | 🟢 | `"sadbutsad","sad" → 0` | ⭐⭐⭐ |
| 2 | Repeated Substring Pattern | 🟡 | `"abab" → true` | ⭐⭐ |
| 3 | Repeated String Match | 🟡 | `a="abcd", b="cdabcdab" → 3` | ⭐⭐ |
| 4 | Check If String Has All Binary Codes of Size K | 🟡 | `"00110110", k=2 → true` | ⭐⭐ |
| 5 | Longest Happy Prefix | 🔴 | `"level" → "l"` | ⭐⭐ |
| 6 | Longest Duplicate Substring | 🔴 | `"banana" → "ana"` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given a new string problem, I can **name the pattern** in under 60 seconds.
- [ ] I've solved every 🟡 in each pattern and can explain the pattern's *trigger* and template.
- [ ] I've attempted every 🔴 and can reconstruct the approach from the pattern alone.
- [ ] I can state time/space complexity and handle edge cases (empty string, single char, all-same).

> **Series:** Arrays ✅ · Strings ✅ · next → `trees-patterns-tier1.md`, `graphs-patterns-tier1.md`,
> `dp-patterns-tier1.md`.
