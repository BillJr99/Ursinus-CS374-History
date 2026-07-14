---
transition: zoom
---

## Model 2: Classify the Snippets

Each paradigm leaves fingerprints in the code. An assignment like `x := x + 1` screams "named mutable cell" — that's an imperative tell. A colon-dash rule like `ancestor(X,Y) :- parent(X,Y).` has no variables at all in the traditional sense — that's logic. Learning to spot these signals in unfamiliar code is the skill that lets you read any language quickly, even before you know its syntax.

| Snippet | Paradigm signal |
|---------|-----------------|
| `account.deposit(50)` | ? |
| `x := x + 1` | ? |
| `(reduce + 0 prices)` | ? |
| `sibling(X,Y) :- parent(P,X), parent(P,Y).` | ? |

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

### Critical Thinking Questions

5. Classify each snippet and name the *single feature* that gave it away.
6. `account.deposit(50)` mutates state *and* sends a message to an object. Is OO a kind of imperative programming with better manners, or something fundamentally different? Take a team position.
7. Modern Python lets you write all four rows' ideas (the fourth via libraries). Does multi-paradigm flexibility help or hurt the *reader* of a program? Connect to the *Evaluating Languages* activity's topic, language evaluation criteria.
