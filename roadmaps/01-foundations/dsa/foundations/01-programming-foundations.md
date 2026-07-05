# 🧰 Programming Foundations

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA roadmap](../../dsa.md) · [Guided path](../README.md) |
| **Status** | ✅ Complete |
| **Kind** | Foundation primer (checklist + warm-ups) |
| **Scope** | the pre-DSA baseline in **Python & JavaScript** |
| **Prerequisites** | None — the starting point |
| **Next** | [Complexity Analysis](02-complexity-analysis.md) |

> **Legend** — Difficulty: 🟢 easy · 🟡 medium.
> Examples show intent (`input → output`), not solutions.

---

## 📖 Read this first

You can't practice DSA without being **fluent** in a language first — every pattern bank ahead
assumes you can turn an idea into working code without fighting syntax. This file is that
pre-check: a checklist to confirm the baseline, plus tiny warm-up drills to shake off rust.

**Dual-language track:** this curriculum uses **Python and JavaScript**. Learn **one deeply
first** — the one you'll solve in during interviews — then know enough of the other to read it
and port a solution. Where the two diverge (built-ins, syntax, I/O, memory model), the
checklists below flag **both** so you can spot the gaps.

**How to use it:** tick every box below before moving to
[Complexity Analysis](02-complexity-analysis.md) — if any box is shaky, close the gap first. The
warm-ups are language-agnostic fluency drills, not interview questions; solve each in a couple of
minutes without looking anything up.

## 🖥️ Language & Setup

- [ ] Pick a **primary** language for interviews; keep the other for reading/porting
- [ ] Local toolchain: run a single file from the command line (Python: `python file.py` · JS: `node file.js`)
- [ ] Online judge setup: how each reads stdin / writes stdout on LeetCode/Codeforces/HackerRank
- [ ] Fast I/O for judges (Python: `sys.stdin` buffered read · JS: `readline` / bulk `fs` read over per-line)
- [ ] Time-limit-friendly idioms (avoid slow I/O; Python: avoid `+=` string concat · JS: avoid repeated array `unshift`)

## 🔤 Core Syntax & Control Flow

- [ ] Numeric types & overflow (Python: arbitrary-precision `int` · JS: one `number`, `Number.MAX_SAFE_INTEGER`, `BigInt`)
- [ ] Block structure (Python: indentation · JS: `{ }` braces and `;`)
- [ ] Arithmetic, comparison, logical, bitwise operators (Python `//` floor-div · JS `/` always float, `Math.floor`)
- [ ] Equality gotchas (JS `==` vs `===` · Python `==` vs `is`)
- [ ] `if` / `elif`/`else if` / `else`, ternary (Python `a if c else b` · JS `c ? a : b`)
- [ ] `for` / `while` loops, `break` / `continue` (Python `range` / `for x in` · JS C-style `for`, `for...of`)
- [ ] `switch`/`match` equivalent (Python `match` · JS `switch`)
- [ ] String formatting (Python f-strings · JS template literals `` `${x}` ``)
- [ ] Truthiness / falsy values (Python: `0`, `""`, `[]`, `{}`, `None` · JS: `0`, `""`, `null`, `undefined`, `NaN`)

## 🔁 Functions & Recursion Syntax

- [ ] Function declaration (Python `def` · JS `function` and arrow `=>`)
- [ ] Anonymous / inline functions (Python `lambda` · JS arrow `=>`)
- [ ] Params & default args (Python `def f(x, y=0)` · JS `function f(x, y = 0)`; mind Python's mutable-default trap)
- [ ] Multiple returns (Python tuple return + unpack · JS array/object destructuring)
- [ ] Scope & closures (Python `global`/`nonlocal` · JS `let`/`const` block scope, `var` hoisting)
- [ ] Recursion syntax: base case + recursive case
- [ ] Recursion limits / stack depth (Python default ~1000, `sys.setrecursionlimit` · JS engine stack limit)

## 📦 Built-in Data Structures

- [ ] Dynamic array / list — append, insert, remove, index, slice (Python `list` · JS `Array`)
- [ ] String basics — indexing, slicing, immutability, common methods (both: strings immutable)
- [ ] Hashmap / dictionary (Python `dict` · JS `Map` for keyed data; `Object` only for string keys)
- [ ] Hash set (Python `set` · JS `Set`)
- [ ] Fixed / heterogeneous grouping (Python `tuple` · JS array or object)
- [ ] Stack via built-ins (Python `list` append/pop · JS `Array` push/pop)
- [ ] Queue / deque (Python `collections.deque` for O(1) both ends · JS array shift is O(n) — use a deque class or index pointer)
- [ ] Heap / priority queue (Python `heapq` · **JS has no built-in heap** — implement one or use a library)
- [ ] Sorting + custom keys/comparators (Python `sorted(key=...)` · JS `arr.sort((a,b) => ...)`; note JS default sort is lexicographic)

## 🏗️ OOP Basics

- [ ] Class & constructor (Python `class` + `__init__`, `self` · JS `class` + `constructor`, `this`)
- [ ] Underlying model (JS `class` is sugar over prototypes — know the prototype chain exists)
- [ ] Encapsulation (Python `_name`/`__name` convention · JS `#private` fields)
- [ ] Inheritance & parent calls (Python `super().__init__()` · JS `extends` + `super()`)
- [ ] Polymorphism (method overriding; Python duck typing / ABCs · JS duck typing)
- [ ] When you'll actually need a class in DSA (custom nodes, comparators, iterators)

## 🧠 Memory & Mutability

- [ ] Value vs reference (Python: everything is a reference; JS: primitives by value, objects/arrays by reference)
- [ ] Mutable vs immutable (Python: `list`/`dict`/`set` mutable, `tuple`/`str`/`int` immutable · JS: objects/arrays mutable, primitives immutable)
- [ ] Shallow copy (Python `list.copy()` / `[:]` / `dict.copy()` · JS spread `[...arr]` / `{...obj}`)
- [ ] Deep copy (Python `copy.deepcopy` · JS `structuredClone` or manual/recursive clone)
- [ ] Aliasing pitfalls (two names pointing at the same underlying object)
- [ ] Passing collections into functions — the callee sees mutations in both languages

## 🐞 I/O, Errors & Debugging

- [ ] Read input — single value, a line, N space/newline-separated values, until EOF (Python `input()` / `sys.stdin` · JS Node `readline` / `fs.readFileSync(0)`)
- [ ] Parse tokens (Python `int(...)`, `.split()`, `map` · JS `Number(...)`, `.split(/\s+/)`)
- [ ] Format output (Python `print` · JS `console.log`; watch trailing newlines/spaces judges expect)
- [ ] Exceptions (Python `try/except` · JS `try/catch`; common: index out of range, `None`/`undefined` deref, div by zero)
- [ ] Print-debugging effectively (temp prints, `assert` statements)
- [ ] Using a debugger or REPL to step through a function (Python `pdb` / REPL · JS `node --inspect` / `debugger`)

---

## 🧩 Warm-up exercises

> Tiny fluency drills — confirm you can write these cold, no lookups. Deeper problem practice
> lives in the [Tier-2/3 core problems](06-core-problems-tier2-3.md) bank.

| # | Exercise | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Print numbers 1 to N | 🟢 | `N=5 → 1 2 3 4 5` | ⭐⭐⭐ |
| 2 | Swap two variables (no temp) | 🟢 | `a=3, b=7 → a=7, b=3` | ⭐⭐⭐ |
| 3 | FizzBuzz | 🟢 | `N=15 → 1,2,Fizz,4,Buzz,...,FizzBuzz` | ⭐⭐⭐ |
| 4 | Sum of digits of a number | 🟢 | `12345 → 15` | ⭐⭐⭐ |
| 5 | Reverse a list in place | 🟢 | `[1,2,3,4] → [4,3,2,1]` | ⭐⭐⭐ |
| 6 | Read N ints and print their sum | 🟢 | `[2,4,6] → 12` | ⭐⭐⭐ |
| 7 | Count words in a sentence | 🟢 | `"the sky is blue" → 4` | ⭐⭐ |
| 8 | Build a frequency map of a list | 🟢 | `[1,2,2,3,3,3] → {1:1, 2:2, 3:3}` | ⭐⭐ |
| 9 | Write a class with a method and call it | 🟡 | `Counter().increment() → 1` | ⭐⭐ |
| 10 | Recursive factorial | 🟡 | `n=5 → 120` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] I can implement any small program in my **primary** language without looking up basic syntax
- [ ] I know the built-in list/array API cold in both (Python `list` · JS `Array`) — append, slice, sort with a key
- [ ] I know the built-in map/set APIs cold in both (Python `dict`/`set` · JS `Map`/`Set`)
- [ ] I can build a stack and a queue/deque from built-ins (Python `deque` · JS array or deque class)
- [ ] I know JS has **no built-in heap** and can reach for `heapq` in Python
- [ ] I can write a small class (constructor, method, one level of inheritance) in both
- [ ] I understand mutable vs immutable and value vs reference in both models
- [ ] I can read N values from stdin and format output exactly as a judge expects in my primary language
- [ ] I can write a base case + recursive case without tracing through it on paper first

> Next in foundations → [Complexity Analysis](02-complexity-analysis.md).
