---
transition: zoom
---

## Model 2: Paradigm Detective

**Paradigm Detective — run this and read the clues:**
```python
snippets = [
    ("account.deposit(50)",                      "sends a message to an object"),
    ("x := x + 1",                              "named cell changes over time"),
    ("(reduce + 0 prices)",                      "function applied to function applied to list"),
    ("sibling(X,Y) :- parent(P,X), parent(P,Y)", "rule: X and Y share a parent"),
]

paradigm_hints = {
    "sends a message to an object":         "Object-Oriented",
    "named cell changes over time":         "Imperative",
    "function applied to function applied": "Functional",
    "rule: X and Y share a parent":         "Logic/Declarative",
}

for snippet, hint in snippets:
    for key, paradigm in paradigm_hints.items():
        if key in hint:
            print(f"  [{paradigm:20}] {snippet}")
            break
```
