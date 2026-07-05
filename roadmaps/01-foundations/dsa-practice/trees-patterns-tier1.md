# 🎯 Trees — Pattern-Based Question Bank (Tier-1 / MAANG)

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA Roadmap](../dsa.md) · [Linked List Patterns](linked-list-patterns-tier1.md) · [Stacks & Queues](stacks-queues-patterns-tier1.md) |
| **Status** | ✅ Complete — Trees (5th in the Tier-1 pattern series) |
| **Kind** | Structure file (pattern-organized) |
| **Scope** | Binary trees, BSTs & N-ary trees, organized by **algorithmic pattern**, Tier-1 / MAANG |
| **Coverage** | 10 patterns · 80 questions |
| **Related** | Next in series → `graphs-patterns-tier1.md` |

---

## 📖 Read this first — how to use the bank (and why it's built this way)

**Why pattern-first?** At Tier-1/MAANG the interview is a **pattern-recognition** game — you solve a
*new* problem by matching it to a pattern you know. This bank is organized by the **pattern that
cracks the problem**, not as a flat list.

**The one mental model for all of trees:** almost every tree problem =
**pick a traversal (BFS or DFS) → decide what to compute at each node → decide what to return up the
recursion.** Get fluent in that lens and the 10 patterns below are just variations:
- **BFS** (queue) → anything "per level" or shortest-in-edges.
- **DFS** (recursion) → most everything else; choose **pre / in / post-order** by *when* you need the
  children's results. **Post-order** (return a value up) powers every "measure the tree" problem.

**How to work through it:** per pattern → read the **🔍 recognize it when…** cue, then solve top-down
(easy → hard). Solve from the prompt; the `input → output` example is only to confirm you understood
the question. Goal: **name the pattern in under 60 seconds** on a new problem.

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Trees are drawn in LeetCode level-order array form, e.g. `[3,9,20,null,null,15,7]`. Examples show **intent**, not solutions.

## 🧭 Pattern Index

| # | Pattern | Qs | 🔍 Recognize it when… |
|:--|:--|:--:|:--|
| 1 | [BFS / Level-Order](#p1) | 10 | you need something *per level* — views, averages, zigzag, connect-next |
| 2 | [DFS Traversal (pre/in/post)](#p2) | 8 | produce nodes in a specific order — interviews want the **iterative / Morris** versions |
| 3 | [Depth, Height & Balance](#p3) | 7 | a global measure (depth, diameter, balance) via a **bottom-up post-order** |
| 4 | [Path Sum & Root-to-Leaf](#p4) | 8 | accumulate along downward paths — DFS carrying a running sum/string |
| 5 | [Binary Search Tree (BST)](#p5) | 12 | the BST invariant holds — inorder is sorted; navigate by comparing to node value |
| 6 | [Lowest Common Ancestor](#p6) | 5 | find the deepest shared ancestor of two nodes |
| 7 | [Construct & Serialize](#p7) | 8 | rebuild a tree from traversals, or (de)serialize to/from a string |
| 8 | [Tree DP (return values)](#p8) | 8 | a node's answer depends on its children's — return a tuple up, with include/exclude states |
| 9 | [Structural Modification](#p9) | 8 | change the tree's shape/content — invert, merge, flatten, prune, compare |
| 10 | [Tree Views & Advanced](#p10) | 6 | a non-standard view (vertical/boundary) or an ancestor/distance query |

---

<a id="p1"></a>
## 1 · BFS / Level-Order (10)

> 🔍 **Recognize it when…** you must process nodes **level by level** or produce something per level
> (a view, an average, zigzag order, next-right pointers). Use a queue.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Average of Levels in Binary Tree | 🟢 | `[3,9,20,null,null,15,7] → [3.0,14.5,11.0]` | ⭐⭐ |
| 2 | Minimum Depth of Binary Tree (BFS) | 🟢 | `[3,9,20,null,null,15,7] → 2` | ⭐⭐ |
| 3 | Binary Tree Level Order Traversal | 🟡 | `[3,9,20,null,null,15,7] → [[3],[9,20],[15,7]]` | ⭐⭐⭐ |
| 4 | Level Order Traversal II (bottom-up) | 🟡 | `→ [[15,7],[9,20],[3]]` | ⭐⭐ |
| 5 | Zigzag Level Order Traversal | 🟡 | `[3,9,20,null,null,15,7] → [[3],[20,9],[15,7]]` | ⭐⭐⭐ |
| 6 | Binary Tree Right Side View | 🟡 | `[1,2,3,null,5,null,4] → [1,3,4]` | ⭐⭐⭐ |
| 7 | Find Largest Value in Each Tree Row | 🟡 | `[1,3,2,5,3,null,9] → [1,3,9]` | ⭐⭐ |
| 8 | Populating Next Right Pointers (perfect tree) | 🟡 | `perfect tree → each node.next set` | ⭐⭐⭐ |
| 9 | Populating Next Right Pointers II (any tree) | 🟡 | `any tree → each node.next set` | ⭐⭐ |
| 10 | All Nodes Distance K in Binary Tree | 🔴 | `root, target=5, k=2 → [7,4,1]` | ⭐⭐⭐ |

<a id="p2"></a>
## 2 · DFS Traversal — pre / in / post (8)

> 🔍 **Recognize it when…** you must emit nodes in a specific order. Recursion is trivial — interviews
> push for the **iterative** (stack) and **Morris** (O(1) space) versions.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Binary Tree Preorder Traversal | 🟢 | `[1,null,2,3] → [1,2,3]` | ⭐⭐ |
| 2 | Binary Tree Inorder Traversal | 🟢 | `[1,null,2,3] → [1,3,2]` | ⭐⭐⭐ |
| 3 | Binary Tree Postorder Traversal | 🟢 | `[1,null,2,3] → [3,2,1]` | ⭐⭐ |
| 4 | N-ary Tree Preorder Traversal | 🟢 | `[1,null,3,2,4,null,5,6] → [1,3,5,6,2,4]` | ⭐⭐ |
| 5 | Inorder Traversal (iterative, no recursion) | 🟡 | `→ inorder using an explicit stack` | ⭐⭐⭐ |
| 6 | Preorder Traversal (iterative) | 🟡 | `→ preorder using an explicit stack` | ⭐⭐ |
| 7 | Postorder Traversal (iterative, two-stack) | 🟡 | `→ postorder using two stacks` | ⭐⭐ |
| 8 | Morris Inorder Traversal (O(1) space) | 🔴 | `→ inorder via threaded links` | ⭐⭐ |

<a id="p3"></a>
## 3 · Depth, Height & Balance (7)

> 🔍 **Recognize it when…** you need a global measure (depth, diameter, balance, width) — compute it
> **bottom-up**: each node returns its height/subtree-info to its parent.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Maximum Depth of Binary Tree | 🟢 | `[3,9,20,null,null,15,7] → 3` | ⭐⭐⭐ |
| 2 | Same Tree | 🟢 | `[1,2,3],[1,2,3] → true` | ⭐⭐ |
| 3 | Symmetric Tree | 🟢 | `[1,2,2,3,4,4,3] → true` | ⭐⭐⭐ |
| 4 | Balanced Binary Tree | 🟢 | `[3,9,20,null,null,15,7] → true` | ⭐⭐⭐ |
| 5 | Diameter of Binary Tree | 🟡 | `[1,2,3,4,5] → 3` | ⭐⭐⭐ |
| 6 | Maximum Width of Binary Tree | 🟡 | `[1,3,2,5,3,null,9] → 4` | ⭐⭐ |
| 7 | Count Complete Tree Nodes | 🟡 | `[1,2,3,4,5,6] → 6` | ⭐⭐ |

<a id="p4"></a>
## 4 · Path Sum & Root-to-Leaf (8)

> 🔍 **Recognize it when…** you accumulate a value (sum, number, string) along root-to-leaf or any
> downward path — DFS carrying state down, collecting at leaves.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Path Sum (root-to-leaf == target?) | 🟢 | `[5,4,8,11,null,13,4,7,2], t=22 → true` | ⭐⭐⭐ |
| 2 | Sum of Root To Leaf Binary Numbers | 🟢 | `[1,0,1,0,1,0,1] → 22` | ⭐⭐ |
| 3 | Binary Tree Paths (all root-to-leaf) | 🟢 | `[1,2,3,null,5] → ["1->2->5","1->3"]` | ⭐⭐ |
| 4 | Path Sum II (all paths == target) | 🟡 | `t=22 → [[5,4,11,2],[5,8,4,5]]` | ⭐⭐⭐ |
| 5 | Sum Root to Leaf Numbers | 🟡 | `[1,2,3] → 25` | ⭐⭐⭐ |
| 6 | Path Sum III (count any-start→any-end == target) | 🟡 | `[10,5,-3,3,2,null,11,3,-2,null,1], t=8 → 3` | ⭐⭐⭐ |
| 7 | Longest Univalue Path | 🟡 | `[5,4,5,1,1,5] → 2` | ⭐⭐ |
| 8 | Binary Tree Maximum Path Sum | 🔴 | `[-10,9,20,null,null,15,7] → 42` | ⭐⭐⭐ |

<a id="p5"></a>
## 5 · Binary Search Tree — BST (12)

> 🔍 **Recognize it when…** the BST invariant holds (`left < node < right`). Two superpowers: an
> **inorder** traversal is sorted, and you navigate by comparing the target to the current value.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Search in a Binary Search Tree | 🟢 | `[4,2,7,1,3], val=2 → subtree [2,1,3]` | ⭐⭐ |
| 2 | Insert into a Binary Search Tree | 🟢 | `[4,2,7,1,3], val=5 → inserted BST` | ⭐⭐ |
| 3 | Range Sum of BST | 🟢 | `[10,5,15,3,7,null,18], L=7, R=15 → 32` | ⭐⭐⭐ |
| 4 | Minimum Absolute Difference in BST | 🟢 | `[4,2,6,1,3] → 1` | ⭐⭐ |
| 5 | Convert Sorted Array to BST | 🟢 | `[-10,-3,0,5,9] → height-balanced BST` | ⭐⭐⭐ |
| 6 | Validate Binary Search Tree | 🟡 | `[5,1,4,null,null,3,6] → false` | ⭐⭐⭐ |
| 7 | Kth Smallest Element in a BST | 🟡 | `[3,1,4,null,2], k=1 → 1` | ⭐⭐⭐ |
| 8 | Inorder Successor in BST | 🟡 | `[2,1,3], p=1 → 2` | ⭐⭐ |
| 9 | Delete Node in a BST | 🟡 | `[5,3,6,2,4,null,7], key=3 → valid BST` | ⭐⭐⭐ |
| 10 | Binary Search Tree Iterator | 🟡 | `next()/hasNext() → inorder stream` | ⭐⭐⭐ |
| 11 | Trim a Binary Search Tree | 🟡 | `[1,0,2], low=1, high=2 → [1,null,2]` | ⭐⭐ |
| 12 | Recover Binary Search Tree (two swapped nodes) | 🔴 | `[1,3,null,null,2] → [3,1,null,null,2]` | ⭐⭐ |

<a id="p6"></a>
## 6 · Lowest Common Ancestor (5)

> 🔍 **Recognize it when…** you must find the deepest node that is an ancestor of two targets — recurse
> and bubble up the node where both sides report a match.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Lowest Common Ancestor of a BST | 🟡 | `[6,2,8,0,4,7,9,null,null,3,5], p=2, q=8 → 6` | ⭐⭐⭐ |
| 2 | Lowest Common Ancestor of a Binary Tree | 🟡 | `[3,5,1,6,2,0,8], p=5, q=1 → 3` | ⭐⭐⭐ |
| 3 | LCA of a Binary Tree II (nodes may be absent) | 🟡 | `p or q missing → null` | ⭐⭐ |
| 4 | LCA of a Binary Tree III (with parent pointers) | 🟡 | `p, q have .parent → LCA` | ⭐⭐ |
| 5 | LCA of Deepest Leaves | 🟡 | `[3,5,1,6,2,0,8,null,null,7,4] → [2,7,4]` | ⭐⭐ |

<a id="p7"></a>
## 7 · Construct & Serialize (8)

> 🔍 **Recognize it when…** you rebuild a tree from traversal outputs, or (de)serialize a tree to/from
> a string. **See also:** Convert Sorted List to BST → [Linked List bank](linked-list-patterns-tier1.md#p6).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Construct String from Binary Tree | 🟢 | `[1,2,3,4] → "1(2(4))(3)"` | ⭐⭐ |
| 2 | Construct Binary Tree from Preorder & Inorder | 🟡 | `pre=[3,9,20,15,7], in=[9,3,15,20,7] → tree` | ⭐⭐⭐ |
| 3 | Construct Binary Tree from Inorder & Postorder | 🟡 | `in & post → tree` | ⭐⭐ |
| 4 | Construct BST from Preorder | 🟡 | `[8,5,1,7,10,12] → BST` | ⭐⭐ |
| 5 | Convert Sorted List to BST | 🟡 | `-10→-3→0→5→9 → height-balanced BST` | ⭐⭐ |
| 6 | Maximum Binary Tree | 🟡 | `[3,2,1,6,0,5] → root 6, recursively` | ⭐⭐ |
| 7 | Serialize and Deserialize Binary Tree | 🔴 | `tree ↔ "1,2,3,null,null,4,5"` | ⭐⭐⭐ |
| 8 | Serialize and Deserialize BST | 🔴 | `BST ↔ compact string` | ⭐⭐ |

<a id="p8"></a>
## 8 · Tree DP — bottom-up return values (8)

> 🔍 **Recognize it when…** a node's answer depends on results from its children — do a **post-order**
> and return a tuple/value up, often with include/exclude states (rob-or-skip, covered-or-not).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Binary Tree Tilt | 🟢 | `[1,2,3] → 1` | ⭐⭐ |
| 2 | House Robber III | 🟡 | `[3,2,3,null,3,null,1] → 7` | ⭐⭐⭐ |
| 3 | Count Good Nodes in Binary Tree | 🟡 | `[3,1,4,3,null,1,5] → 4` | ⭐⭐⭐ |
| 4 | Longest ZigZag Path in a Binary Tree | 🟡 | `→ 3` | ⭐⭐ |
| 5 | Distribute Coins in Binary Tree | 🟡 | `[3,0,0] → 2` | ⭐⭐ |
| 6 | Maximum Product of Splitted Binary Tree | 🟡 | `[1,2,3,4,5,6] → 110` | ⭐⭐ |
| 7 | Number of Good Leaf Nodes Pairs | 🟡 | `[1,2,3,null,4], distance=3 → 1` | ⭐⭐ |
| 8 | Binary Tree Cameras | 🔴 | `[0,0,null,0,0] → 1` | ⭐⭐ |

<a id="p9"></a>
## 9 · Structural Modification (8)

> 🔍 **Recognize it when…** you change the tree's shape or content — invert, merge, flatten, prune, or
> compare structures. **See also:** Flatten Binary Tree to Linked List also relates to [Linked List bank](linked-list-patterns-tier1.md#p6).

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Invert Binary Tree | 🟢 | `[4,2,7,1,3,6,9] → [4,7,2,9,6,3,1]` | ⭐⭐⭐ |
| 2 | Merge Two Binary Trees | 🟢 | `[1,3,2],[2,1,3] → [3,4,5,5,4,null,7]` | ⭐⭐ |
| 3 | Subtree of Another Tree | 🟢 | `[3,4,5,1,2],[4,1,2] → true` | ⭐⭐⭐ |
| 4 | Flatten Binary Tree to Linked List | 🟡 | `[1,2,5,3,4,null,6] → 1→2→3→4→5→6` | ⭐⭐⭐ |
| 5 | Delete Nodes And Return Forest | 🟡 | `[1,2,3,4,5,6,7], del=[3,5] → [[1,2,null,4],[6],[7]]` | ⭐⭐ |
| 6 | Add One Row to Tree | 🟡 | `[4,2,6,3,1,5], val=1, depth=2 → new tree` | ⭐⭐ |
| 7 | Binary Tree Pruning (remove all-0 subtrees) | 🟡 | `[1,null,0,0,1] → [1,null,0,null,1]` | ⭐⭐ |
| 8 | Flip Equivalent Binary Trees | 🟡 | `[1,2,3,4,5,6,null,null,null,7,8],[1,3,2,null,6,4,5,null,null,null,null,8,7] → true` | ⭐⭐ |

<a id="p10"></a>
## 10 · Tree Views & Advanced (6)

> 🔍 **Recognize it when…** you produce a non-standard view (vertical, boundary, bottom-left) or answer
> an ancestor/distance query across the whole tree.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Find Bottom Left Tree Value | 🟡 | `[2,1,3] → 1` | ⭐⭐ |
| 2 | Maximum Difference Between Node and Ancestor | 🟡 | `[8,3,10,1,6,null,14,null,null,4,7,13] → 7` | ⭐⭐ |
| 3 | Boundary of Binary Tree | 🟡 | `→ anti-clockwise boundary node list` | ⭐⭐ |
| 4 | Binary Tree Vertical Order Traversal | 🟡 | `[3,9,20,null,null,15,7] → [[9],[3,15],[20],[7]]` | ⭐⭐⭐ |
| 5 | Vertical Order Traversal (with tie-break sort) | 🔴 | `→ columns, ties sorted by value` | ⭐⭐ |
| 6 | Amount of Time for Binary Tree to Be Infected | 🔴 | `root, start node → minutes to infect all` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] Given a new tree problem, I instantly decide **BFS vs DFS** and **which order** (pre/in/post).
- [ ] I can write every traversal **iteratively**, not just recursively.
- [ ] For "measure the tree" problems I default to a **post-order that returns info up**.
- [ ] I've solved every 🟡 and attempted every 🔴 (max path sum, serialize/deserialize, cameras, distance-K).
- [ ] I handle edge cases: empty tree, single node, skewed tree, duplicate values.

> **Series:** Arrays ✅ · Strings ✅ · Linked List ✅ · Stacks & Queues ✅ · Trees ✅ · next →
> `graphs-patterns-tier1.md`, then heaps → dp → backtracking.
