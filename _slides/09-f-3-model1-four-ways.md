---
transition: zoom
---

## Model 1: Object-Oriented

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
