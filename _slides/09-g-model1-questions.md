---
transition: zoom
---

## Critical Thinking Questions

1. Identify the mutable state in each version (there may be none). Which versions could safely run on two halves of the string in parallel and add the results, and why?
2. The OO version wraps the same logic in a class with lazy computation. Name one situation where that wrapping pays for itself, and one where it is ceremony without benefit.
3. In the logic-style version, where is the loop? What does its absence tell you about who owns control flow in a declarative style?
4. Your team's language project must choose: mutable variables or immutable bindings (or both). List one implementation consequence of each choice for the *interpreter* you will build.
