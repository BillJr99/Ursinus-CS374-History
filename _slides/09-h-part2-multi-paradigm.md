---
transition: zoom
---

## Part II: Paradigms in the Wild

> **Watch out!** Saying "Python is object-oriented" is like saying "New York is a financial city" — true but incomplete. Python has objects everywhere, *and* supports imperative style, *and* ships functional tools like `map`, `filter`, and `lambda`. When you evaluate a language, look for its *defaults* and its *limits*, not just a single label.

## 3. Multi-Paradigm Reality

In practice, the clean four-way taxonomy you just explored is a teaching simplification. Real languages are hybrids shaped by history, performance constraints, and the preferences of their designers. As you read this section, think of the paradigm spectrum as a dial rather than four locked boxes — the interesting design question is where a language sets its dial by default, and how far the user can turn it.

**Pure paradigm languages are rare; blends are the norm.** Python is imperative and OO with a functional toolkit (`map`, `filter`, comprehensions, `lambda`). Java added lambdas and streams in 2014; JavaScript mixes prototypal objects with pervasive higher-order functions; Rust is imperative with functional pattern matching and an ownership discipline. The paradigm question for a designer is not *which one* but *which defaults*: what does the language make easy, and what does it make possible?

A language guarantees that no value can ever be modified after creation and that functions may be stored in variables and passed as arguments. These two guarantees are the signatures of:

- The imperative paradigm
- The object-oriented paradigm
- **✓ The functional paradigm**
- The logic paradigm

A program in language X cannot run a function until every argument is known. Language Y can pass a function as a value and call it later. The property that distinguishes Y from X is:

- Dynamic typing
- Object orientation
- **✓ First-class functions**
- Static scoping
