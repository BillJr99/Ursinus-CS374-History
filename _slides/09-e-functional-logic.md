---
transition: zoom
---

## 2. Functional and Logic

Functional programming treats a program the way a mathematician treats a formula: `f(g(x))` has one answer for a given `x`, no side effects, and no hidden state. Logic programming goes even further — it is like asking a very smart search engine a question ("who are all the ancestors of Tom?") and letting the engine figure out how to find the answer from the facts you gave it; you never write a loop at all.

**Functional: a program is the composition of functions.** The central commitments are **immutability** (values do not change; new values are produced), **first-class functions** (functions are values that can be passed and returned), and **referential transparency** (an expression can be replaced by its value without changing behavior). Where imperative code says *do this, then that*, functional code says *the answer is this transformation of that*. Scheme, Haskell, and increasingly the cores of Python and Java.

**Logic: a program is facts and rules; the runtime searches for proofs.** In Prolog one declares `parent(tom, mary).` and rules like `ancestor(X, Y) :- parent(X, Y).`, then asks queries; the *how* belongs entirely to the engine. Logic programming is the purest case of **declarative** programming, stating what is true rather than what to do.
