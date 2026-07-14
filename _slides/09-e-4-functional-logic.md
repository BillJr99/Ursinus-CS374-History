---
transition: zoom
---

## Logic Programming

**Logic: a program is facts and rules; the runtime searches for proofs.** In Prolog one declares `parent(tom, mary).` and rules like `ancestor(X, Y) :- parent(X, Y).`, then asks queries; the *how* belongs entirely to the engine. Logic programming is the purest case of **declarative** programming, stating what is true rather than what to do.
