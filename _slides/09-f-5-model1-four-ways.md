---
transition: zoom
---

## Model 1: Functional

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
