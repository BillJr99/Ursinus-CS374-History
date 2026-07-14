---
transition: zoom
---

## Model 1: Imperative

**Imperative — explicit state mutation:**
```python
s = "programming languages are fascinating"

count = 0
for ch in s:
    if ch in "aeiou":
        count = count + 1

print(f"Imperative count: {count}")
```
