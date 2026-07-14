---
transition: zoom
---

## Model 1: Logic-Style

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
