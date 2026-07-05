# 🔗 Linked List — Concept Card

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Layer** | Concepts (the *why & when*) — companion to the practice banks |
| **Status** | 🔨 In progress — pilot for the Concepts layer |
| **Question banks** | [Tier-1 patterns](../tier1-patterns/03-linked-list.md) · [Tier-2/3 breadth](../foundations/06-core-problems-tier2-3.md) |
| **Prerequisite cards** | [Array](array.md) |
| **Unlocks** | [Stack](stack.md) · [Queue](queue.md) · [Hash Table](hash-table.md) (LRU) |

> **Legend** — 🟢 Fresher (0–1y) · 🟡 Mid (2–5y) · 🔴 Senior (5+y) &nbsp;•&nbsp; Reference tables state **facts**; everything else is a **prompt you complete** — no solutions here, by design.

---

## ⚡ At a Glance

| | |
|---|---|
| **It is** | A linear chain — each **node** holds a value **+ a pointer to the next**. Order lives in the links, not in memory. |
| **Mental model** | 🗺️ A treasure hunt: each clue says *only* where the next clue is. Can't jump ahead — but you can splice a new clue in anywhere, instantly. |
| **Superpower** | ⚡ O(1) insert/delete at a known spot — no shifting, no resizing. |
| **Weakness** | 🐢 O(n) to reach index *k* · cache-unfriendly pointer-chasing · +1–2 pointers per node. |
| **Reach for it** | Edits at ends / a node you hold · churny size · references that must stay valid (LRU). |
| **Skip it** | Random access by index · tight memory · hot iteration loops. |
| **Must-know patterns** | reversal · fast&slow · dummy node · merge · recursion → [drill them](../tier1-patterns/03-linked-list.md) |

> 🧭 **Rule of thumb:** *edits at a known position → linked list. Reads by index → array.*

## 🗂️ Card Map

**①  [Grasp it](#grasp)**  →  **②  [Look it up](#reference)**  →  **③  [Build it](#build)**  →  **④  [Drill it](#drill)**

`Why · When · vs Array · Internals · Real uses`  ·  `Complexity · Variants · APIs`  ·  `Draw · Implement · Mistakes · Projects`  ·  `Patterns · Recall · Self-check`

---

<a id="grasp"></a>
# ①  Grasp it

### 🤔 Why It Exists — *be able to make these claims*

- [ ] 🟢 What does it give you that a dynamic array can't? → O(1) insert/delete at a known position, no resize/shift.
- [ ] 🟡 What does it trade away to buy that? → O(n) random access, pointer memory, poor cache locality.
- [ ] 🔴 When is that trade a *win* in a real system — and when is an array secretly faster despite worse Big-O?

### 🎯 When to Reach for It

| ✅ Reach for it when… | 🚫 Avoid it / prefer array·deque when… |
|---|---|
| Frequent insert/delete at the ends or a held node | You need random access by index |
| Size is highly dynamic (dodge resize churn) | You iterate hot loops (cache misses dominate) |
| Elements need stable refs across edits (LRU nodes) | Memory is tight / elements are tiny |

### ⚔️ Linked List vs Array — *the decision, side by side*

| | 🔗 Linked List | 🧱 Dynamic Array |
|---|:--:|:--:|
| Access index *k* | 🐢 O(n) | ⚡ O(1) |
| Insert / delete at front | ⚡ O(1) | 🐢 O(n) |
| Insert / delete at back | O(1)* | ⚡ amortized O(1) |
| Memory overhead | +pointers per node | compact |
| Cache locality | ✗ scattered | ✓ sequential |
| Stable element references | ✓ survive edits | ✗ invalidated on resize |

<sub>*O(1) at back only with a tail pointer.</sub>

### ⚙️ Internal Model & Invariants — *be able to explain, unprompted*

- [ ] 🟢 Node = `{ value, next }` (+ `prev` if doubly); nodes scattered in the heap, linked by references.
- [ ] 🟢 Invariant: the chain **terminates** (`next == null`) or **closes** (circular); `head`/`tail` point to real ends.
- [ ] 🟡 Why front-insert is O(1) but index-*k* access is O(n) — you must **walk** the links.
- [ ] 🔴 Pointer-chasing = one cache miss per hop; contrast with an array's sequential prefetch.

### 🌍 Real-World Uses

> 💾 LRU cache (hash map + doubly list) · 🕸️ graph adjacency lists · 🧵 OS free-lists & schedulers
> · ↩️ undo/redo stacks · 🎵 playlists & carousels (circular) · 🌐 browser history.

---

<a id="reference"></a>
# ②  Look it up  · *reference facts*

### 🔧 Operations & Complexity — *singly unless noted*

| Operation | Best | Avg | Worst | Notes |
|---|:--:|:--:|:--:|---|
| Access / index-*k* | O(1) | **O(n)** | O(n) | must walk from head |
| Search by value | O(1) | **O(n)** | O(n) | |
| 🔥 Insert at head | O(1) | **O(1)** | O(1) | the signature win |
| Insert at tail | O(1)* | O(n) | O(n) | *O(1) with a tail pointer |
| Insert after known node | O(1) | **O(1)** | O(1) | you already hold it |
| Delete at head | O(1) | **O(1)** | O(1) | |
| Delete at tail | O(n) | O(n) | O(n) | O(1) for **doubly** + tail |
| Delete a known node | O(n) | O(n) | O(n) | 🔥 O(1) for **doubly** (has `prev`) |
| **Space** | O(n) | O(n) | O(n) | + 1–2 pointers / node |

### 🔀 Variants — *names + when to use*

| Variant | Use when… |
|---|---|
| **Singly** | Minimal memory; forward-only traversal. |
| **Doubly** | O(1) delete-given-node or backward walk (LRU, editors). |
| **Circular** (singly/doubly) | Round-robin / ring buffers where "end" wraps to "start". |
| **+ Tail pointer** | Need O(1) append (queues). |
| **+ Sentinel/dummy head** | Kill head/empty edge-cases in every op. |
| **Skip list** | Probabilistic O(log n) search over a sorted list. |
| **Unrolled / XOR** | Cache-density or memory tricks — niche / senior curiosities. |

### 📚 Language APIs — *names only; look up the usage yourself*

| Language | Built-in type(s) |
|---|---|
| 🐍 Python | *no singly built-in* · `collections.deque` (doubly-linked deque) |
| ☕ Java | `java.util.LinkedList` (doubly; also a `Deque`) |
| ⚙️ C++ | `std::list` (doubly) · `std::forward_list` (singly) |
| 🟨 JavaScript | *none built-in* — arrays, or roll your own node class |
| 🐹 Go | `container/list` (doubly) |

---

<a id="build"></a>
# ③  Build it

### 🖼️ Draw It First — *you draw, we don't*

> **Notation:** a node is `[val|→]`, null is `⌀`. A 3-list: `head → [1|→] [2|→] [3|⌀]`.

- ✍️ Redraw that list after **reverse**, after **insert-at-head(0)**, after **delete-2nd-node**.
- ✍️ On each op, circle **exactly which pointers change**. For deletion, show why a singly list needs the **prev** node — that picture *is* your debugger.

### 🧩 Implement From Scratch — *prompts, no code*

- [ ] 🟢 Singly list: `push_front · push_back · pop_front · find · size · print`.
- [ ] 🟢 Reverse it — iteratively (three-pointer) **and** recursively.
- [ ] 🟡 Doubly list with O(1) delete-given-node and a tail pointer.
- [ ] 🟡 Circular buffer / ring on top of a list.
- [ ] 🔴 Skip list with probabilistic levels — *or* a lock-free / concurrent singly list.

### ⚠️ Common Mistakes — *recognise, don't re-explain*

> 🕳️ Losing the head (no dummy/sentinel) · ignoring empty / single-node cases · forgetting to update
> `tail` on delete-last · off-by-one on fast/slow gaps · creating a cycle by mis-pointing `next`
> · use-after-free / leaks (C++).

### 🚀 Optimization Levers

> 🎛️ Dummy/sentinel head · tail pointer for O(1) append · doubly links for O(1) delete · fast/slow
> for one-pass mid/cycle/nth-from-end · recursion → iteration to dodge stack overflow · skip list for O(log n) search.

### 🛠️ Projects — *build something that forces the structure*

> **💾 LRU Cache** `🟡` — fixed-capacity, O(1) `get`/`put`; hash map for lookup **+** doubly list for recency. You can't hit O(1) eviction without the list.
> **Acceptance:** O(1) get/put under test · correct eviction order · handles update-existing-key.

> **↩️ Text-editor buffer + undo/redo** `🟡` — cursor edits via a doubly list; undo/redo stacks.
> **Acceptance:** insert/delete at cursor in O(1) · unbounded undo/redo · survives fuzz edits.

---

<a id="drill"></a>
# ④  Drill it

### 🎤 Interview Patterns & Question Banks — *pointers, no questions restated*

**Master these 6 patterns:** in-place reversal · fast & slow pointers · dummy node & deletion · merge / add lists · recursion · design & copy.

- 🔗 **Tier-1 / MAANG** → [Linked List pattern bank](../tier1-patterns/03-linked-list.md) · *6 patterns · 46 Qs*
- 🔗 **Tier-2/3 / startups** → [Core-problems breadth bank](../foundations/06-core-problems-tier2-3.md) · *Linked List section · 12 Qs*

### 🃏 Recall Drills — *test yourself; expand only to check you're on target*

<details><summary>🟢 Cost of indexing the middle element — and why?</summary>

↳ *You should be able to state the Big-O and the one-word reason. Check the [complexity table](#reference).*
</details>

<details><summary>🟢 What three pointers does an iterative reverse track?</summary>

↳ *Name all three and their roles. Verify by doing the [reverse exercise](#build).*
</details>

<details><summary>🟡 How does a dummy head remove head/empty edge-cases?</summary>

↳ *Explain it in one sentence, then prove it in your delete implementation.*
</details>

<details><summary>🟡 Detect a cycle in O(1) extra space — which pointers, moving how fast?</summary>

↳ *Name the pattern and the speed ratio. Drill it in the [pattern bank](../tier1-patterns/03-linked-list.md).*
</details>

<details><summary>🔴 Delete a node given only a pointer to it (not the head) in a singly list — trick & catch?</summary>

↳ *There's a copy trick; name the one case it can't handle.*
</details>

<details><summary>🔴 Same Big-O as an array for a task — name a case the array still wins in practice.</summary>

↳ *Think cache lines and prefetch, not asymptotics.*
</details>

### ✅ Self-Assessment

- [ ] 🟢 I can implement singly & doubly lists from scratch and reverse them two ways.
- [ ] 🟢 I can state every operation's best/avg/worst complexity from memory.
- [ ] 🟡 I can justify list vs array for a given workload — both directions.
- [ ] 🟡 I can build an LRU cache and explain why it needs *both* a hash map and a doubly list.
- [ ] 🔴 I can reason about cache / pointer-chasing costs and say when an array beats a list despite Big-O.
