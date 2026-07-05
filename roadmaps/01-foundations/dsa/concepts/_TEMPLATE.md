<!--
CONCEPT CARD TEMPLATE — copy this file to start a new data-structure concept card.
Rules: see ../../../../CLAUDE.md. This is a SKELETON + REFERENCE FACTS:
  ALLOWED  → checklists, exercise prompts, self-test questions, project ideas, interview pointers,
             and small FACTUAL reference tables (complexity, API names, variant names, a compare table).
  FORBIDDEN→ tutorials, prose explanations, worked implementations/solutions, drawn diagrams,
             flashcard ANSWER sides. If you catch yourself teaching, stop and turn it into a prompt.
Shape: 4 acts — ① Grasp it · ② Look it up · ③ Build it · ④ Drill it. Keep the ⚡ At a Glance strip
  and 🗂️ Card Map so the file is scannable and referable, never a flat bullet wall.
Anti-duplication: question banks live in ../tier1-patterns/ and ../foundations/. Here we LINK to
  them — never restate the questions. After any link change, run the link-checker over all .md.
Level tags: mark items 🟢 Fresher / 🟡 Mid / 🔴 Senior throughout.
-->

# <emoji> <Structure> — Concept Card

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Layer** | Concepts (the *why & when*) — companion to the practice banks |
| **Status** | 🚧 Stub |
| **Question banks** | [Tier-1 patterns](../tier1-patterns/NN-<structure>.md) · [Tier-2/3 breadth](../foundations/06-core-problems-tier2-3.md) |
| **Prerequisite cards** | [<structure>](<structure>.md) |
| **Unlocks** | [<structure>](<structure>.md) |

> **Legend** — 🟢 Fresher (0–1y) · 🟡 Mid (2–5y) · 🔴 Senior (5+y) &nbsp;•&nbsp; Reference tables state **facts**; everything else is a **prompt you complete** — no solutions here, by design.

---

## ⚡ At a Glance

| | |
|---|---|
| **It is** | <one breath: what it is> |
| **Mental model** | 🗺️ <think of it as …> |
| **Superpower** | ⚡ <the one thing it's great at> |
| **Weakness** | 🐢 <the price you pay> |
| **Reach for it** | <signal · signal · signal> |
| **Skip it** | <anti-signal · anti-signal> |
| **Must-know patterns** | <pattern · pattern> → [drill them](../tier1-patterns/NN-<structure>.md) |

> 🧭 **Rule of thumb:** *<memorable one-line decision heuristic>.*

## 🗂️ Card Map

**①  [Grasp it](#grasp)**  →  **②  [Look it up](#reference)**  →  **③  [Build it](#build)**  →  **④  [Drill it](#drill)**

`Why · When · vs <alt> · Internals · Real uses`  ·  `Complexity · Variants · APIs`  ·  `Draw · Implement · Mistakes · Projects`  ·  `Patterns · Recall · Self-check`

---

<a id="grasp"></a>
# ①  Grasp it

### 🤔 Why It Exists — *be able to make these claims*

- [ ] 🟢 What problem does it solve that the simpler structure couldn't?
- [ ] 🟡 What does it trade away to buy that? (state the cost)
- [ ] 🔴 When is that trade a *win* in a real system — and what has no good substitute?

### 🎯 When to Reach for It

| ✅ Reach for it when… | 🚫 Avoid it / prefer <X> when… |
|---|---|
| <signal> | <anti-signal> |
| <signal> | <anti-signal> |

### ⚔️ <Structure> vs <closest alternative> — *the decision, side by side*

| | <this> | <alternative> |
|---|:--:|:--:|
| <dimension> | | |
| <dimension> | | |

### ⚙️ Internal Model & Invariants — *be able to explain, unprompted*

- [ ] 🟢 Memory layout — how elements physically sit / connect.
- [ ] 🟢 The invariant(s) every operation must preserve.
- [ ] 🟡 What makes each core op cheap or expensive (tie to the complexity table).
- [ ] 🔴 Cache / locality / concurrency behaviour vs the alternatives.

### 🌍 Real-World Uses

> <system/place it shows up> · <another> · <another>

---

<a id="reference"></a>
# ②  Look it up  · *reference facts*

### 🔧 Operations & Complexity

| Operation | Best | Avg | Worst | Notes |
|---|:--:|:--:|:--:|---|
| Access / index | | | | |
| Search | | | | |
| Insert (front / middle / end) | | | | |
| Delete (front / middle / end) | | | | |
| **Space** | | | | |

### 🔀 Variants — *names + when to use*

| Variant | Use when… |
|---|---|
| <variant> | <one line> |

### 📚 Language APIs — *names only; look up the usage yourself*

| Language | Built-in type(s) |
|---|---|
| 🐍 Python | |
| ☕ Java | |
| ⚙️ C++ | |
| 🟨 JavaScript | |
| 🐹 Go | |

---

<a id="build"></a>
# ③  Build it

### 🖼️ Draw It First — *you draw, we don't*

> **Notation:** <a compact node/cell notation the learner can reuse>.

- ✍️ Sketch a small instance, then redraw it after each core operation.
- ✍️ Circle exactly which pointers/indices change — that picture is your debugger.

### 🧩 Implement From Scratch — *prompts, no code*

- [ ] 🟢 Core structure + core operations.
- [ ] 🟡 <the harder variant / operation>.
- [ ] 🔴 <a stress / scale / concurrency variant>.

### ⚠️ Common Mistakes — *recognise, don't re-explain*

> <pitfall> · <pitfall> · <pitfall>

### 🚀 Optimization Levers

> <lever> · <lever> · <lever>

### 🛠️ Projects — *build something that forces the structure*

> **<name>** `🟡` — <what to build + why it needs this structure>.
> **Acceptance:** <criteria> · <criteria>

---

<a id="drill"></a>
# ④  Drill it

### 🎤 Interview Patterns & Question Banks — *pointers, no questions restated*

**Master these patterns:** <pattern> · <pattern> · <pattern>.

- 🔗 **Tier-1 / MAANG** → [<Structure> pattern bank](../tier1-patterns/NN-<structure>.md)
- 🔗 **Tier-2/3 / startups** → [Core-problems breadth bank](../foundations/06-core-problems-tier2-3.md)

### 🃏 Recall Drills — *test yourself; expand only to check you're on target*

<details><summary>🟢 <one-line prompt>?</summary>

↳ *<what a right answer must contain / where to verify — never the answer itself>.*
</details>

<details><summary>🟡 <prompt>?</summary>

↳ *<check-yourself pointer>.*
</details>

<details><summary>🔴 <prompt>?</summary>

↳ *<check-yourself pointer>.*
</details>

### ✅ Self-Assessment

- [ ] 🟢 I can <concrete, testable claim>.
- [ ] 🟡 I can <claim>.
- [ ] 🔴 I can <claim>.
