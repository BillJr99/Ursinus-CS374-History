---
transition: zoom
---

## Model 1: Same Problem, Four Ways

The best way to feel the difference between paradigms is to solve *exactly* the same problem four ways and notice what each version forces you to think about. As you read each block below, ask yourself: what is mutable here? Who controls the loop? Could I run this twice on different inputs simultaneously without the two runs interfering?

Count the vowels in a string. Run each approach and compare:

**Imperative — explicit state mutation:**
```python
s = "programming languages are fascinating"

count = 0
for ch in s:
    if ch in "aeiou":
        count = count + 1

print(f"Imperative count: {count}")
```

**Object-oriented — encapsulated state:**
```python
s = "programming languages are fascinating"

class VowelCounter:
    VOWELS = set("aeiou")

    def __init__(self, text):
        self.text = text
        self._count = None  # lazy computation

    def count(self):
        if self._count is None:
            self._count = sum(1 for ch in self.text if ch in self.VOWELS)
        return self._count

    def __repr__(self):
        return f"VowelCounter({self.text!r}, count={self.count()})"

vc = VowelCounter(s)
print(f"OO count: {vc.count()}")
print(repr(vc))
```

> **Watch out!** "Pure function" and "function" are not the same thing. A pure function's output depends *only* on its arguments and it causes no side effects (no printing, no file writes, no mutation of shared variables). Python's `print()` is a function, but it is *not* pure — it changes the state of the terminal. Keep this distinction sharp as you read the functional version below.

**Functional — composition of pure functions:**
```python
from functools import reduce

s = "programming languages are fascinating"

# No variables mutated; each step is a pure function
is_vowel  = lambda ch: ch in "aeiou"
to_one    = lambda _: 1
add       = lambda a, b: a + b

count = reduce(add, map(to_one, filter(is_vowel, s)), 0)
print(f"Functional count: {count}")

# Even more compact with sum + generator:
count2 = sum(1 for ch in s if ch in "aeiou")
print(f"Comprehension count: {count2}")
```

**Logic-style — simulate Prolog with constraint search:**
```python
# Python simulation of logic-style declarative counting
s = "programming languages are fascinating"

# "Facts" — vowel membership
vowels = {"a", "e", "i", "o", "u"}

# "Rule" — count is cardinality of {ch | ch in s AND vowel(ch)}
count = len({i: ch for i, ch in enumerate(s) if ch in vowels})
print(f"Logic-style count: {count}")

# More Prolog-like: unification via list comprehension
answer = [ch for ch in s if ch in vowels]
print(f"Witness list: {answer[:10]}... (length {len(answer)})")
```
