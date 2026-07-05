# 🔢 Mathematics for DSA

|  |  |
|---|---|
| **Pillar** | `01 · Foundations` |
| **Companion to** | [DSA roadmap](../../dsa.md) · [Guided path](../README.md) |
| **Status** | ✅ Complete |
| **Kind** | Foundation primer (checklist + practice) |
| **Scope** | The math that shows up in coding interviews — number theory, modular arithmetic, combinatorics, probability, sequences |
| **Prerequisites** | [Programming Foundations](01-programming-foundations.md) |
| **Next** | [Bit Manipulation](04-bit-manipulation.md) |

> **Legend** — Difficulty: 🟢 easy · 🟡 medium · 🔴 hard &nbsp;•&nbsp; Frequency: ⭐⭐⭐ asked constantly · ⭐⭐ common · ⭐ occasional
> Examples show intent (`input → output`), not solutions.

---

## 📖 Read this first

A small, fixed set of math ideas keeps resurfacing across interviews — primes, mod arithmetic, and
counting. Learn these once and a whole class of "clever" problems collapses into "oh, it's just this
trick." This file is a **checklist, not a course**: skim each section, look up anything unfamiliar
elsewhere, then drill the practice table below. Solve every row from the prompt — the example only
confirms you understood the question.

---

## 🧮 Number Theory

> Underlies primality, factorization, and divisor-counting questions.

- [ ] Prime numbers — definition, primality test (trial division up to √n)
- [ ] Sieve of Eratosthenes — generate all primes up to n
- [ ] GCD & LCM — Euclidean algorithm, relation between GCD and LCM
- [ ] Prime factorization — trial division up to √n
- [ ] Divisors of a number — count divisors, sum of divisors, enumerate in O(√n)

## ➗ Modular Arithmetic

> Shows up whenever an answer must be returned "mod 1e9+7" — i.e. constantly.

- [ ] Mod properties — `(a+b)%m`, `(a*b)%m`, `(a-b)%m` (handling negative results)
- [ ] Modular addition & multiplication under a modulus
- [ ] Fast modular exponentiation (binary exponentiation)
- [ ] Modular inverse — Fermat's little theorem / extended Euclid
- [ ] Why 1e9+7 — overflow avoidance in interview/competitive problems

## 🎲 Combinatorics

> Counting problems ("how many ways…") reduce to a handful of formulas.

- [ ] Factorials — definition, growth rate, why they overflow fast
- [ ] Permutations — nPr
- [ ] Combinations — nCr, relation to Pascal's triangle
- [ ] Pascal's triangle — construction, row/column meaning
- [ ] Stars-and-bars intuition — distributing identical items into buckets

## 🎯 Probability & Expected Value

> Rarer in pure DSA rounds, common in quant/ML-adjacent and randomized-algorithm questions.

- [ ] Basic probability — sample space, independent events
- [ ] Expected value — definition, weighted average over outcomes
- [ ] Linearity of expectation — why it holds even without independence

## 📈 Sequences, Series & Misc

> The background math behind complexity analysis and quick sanity checks.

- [ ] Arithmetic series — sum formula, intuition
- [ ] Geometric series — sum formula, when it converges
- [ ] Powers & logs intuition — why O(log n) shows up (halving), log-base intuition
- [ ] Overflow awareness — int vs long, when to switch, off-by-one in math loops

---

## 🧩 Practice

> **See also:** GCD of Two Numbers also appears in [Recursion Fundamentals](05-recursion-divide-conquer.md#p1);
> Pow(x, n) also appears in [D&C — Arrays & Math](05-recursion-divide-conquer.md#p3). Kept here too since
> both are fundamentally math problems.

| # | Question | Diff | Example `input → output` | Freq |
|:--|:--|:--:|:--|:--:|
| 1 | Count Primes (< n) | 🟢 | `n=10 → 4` | ⭐⭐ |
| 2 | GCD of Two Numbers (Euclidean algorithm) | 🟢 | `48, 18 → 6` | ⭐⭐⭐ |
| 3 | Power of Two / Three / Four | 🟢 | `n=16 → true` | ⭐⭐ |
| 4 | Happy Number | 🟢 | `n=19 → true` | ⭐⭐ |
| 5 | Add Digits (digital root) | 🟢 | `38 → 2` | ⭐⭐ |
| 6 | Excel Sheet Column Number | 🟢 | `"AB" → 28` | ⭐⭐ |
| 7 | Excel Sheet Column Title | 🟢 | `28 → "AB"` | ⭐⭐ |
| 8 | Sieve of Eratosthenes (generate primes up to n) | 🟡 | `n=20 → [2,3,5,7,11,13,17,19]` | ⭐⭐⭐ |
| 9 | Factorial Trailing Zeroes | 🟡 | `n=15 → 3` | ⭐⭐ |
| 10 | Pascal's Triangle (generate first n rows) | 🟡 | `numRows=5 → row 3 = [1,2,1]` | ⭐⭐ |
| 11 | Perfect Number | 🟡 | `num=28 → true` | ⭐ |
| 12 | Sum of Square Numbers | 🟡 | `c=5 → true (1²+2²)` | ⭐ |
| 13 | Pow(x, n) — fast exponentiation | 🟡 | `x=2.0, n=10 → 1024.0` | ⭐⭐⭐ |
| 14 | Modular Exponentiation | 🟡 | `base=2, exp=10, mod=1e9+7 → 1024` | ⭐⭐ |
| 15 | nCr mod p | 🔴 | `n=5, r=2, p=1000000007 → 10` | ⭐⭐ |
| 16 | Fraction to Recurring Decimal | 🔴 | `numerator=1, denominator=3 → "0.(3)"` | ⭐⭐ |

---

## ✅ Definition of Done

- [ ] I can generate primes with a sieve and compute GCD/LCM by hand and in code.
- [ ] I can do fast modular exponentiation and compute nCr mod p.
- [ ] I know why answers get taken mod 1e9+7 and can avoid overflow bugs (int vs long).
- [ ] I recognize when a problem is really a counting/number-theory problem in disguise.
- [ ] I can reason about expected value and linearity of expectation for a random process.

> Next in foundations → [Bit Manipulation](04-bit-manipulation.md).
