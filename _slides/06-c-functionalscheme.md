---
transition: zoom
---

## Declarative Paradigms: Functional Programming

- 1970's: Scheme - Descendent of List Processor (LISP, 1958)
- Composition of local functions that operate on tuples with minimal side effects

```
(define square
  (lambda(n)
    (* n n)))
      
(square 5)
```
