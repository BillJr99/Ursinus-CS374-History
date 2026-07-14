---
transition: zoom
---

## Model 3: Performance Comparison

```python
import time

data = list(range(1, 100001))
target = lambda x: x % 2 == 0

# Imperative
t0 = time.perf_counter()
result_imp = []
for x in data:
    if target(x):
        result_imp.append(x * x)
total_imp = sum(result_imp)
t1 = time.perf_counter()

# Functional (generator — lazy, low memory)
t2 = time.perf_counter()
total_func = sum(x*x for x in data if target(x))
t3 = time.perf_counter()

print(f"Imperative:  {total_imp}  ({(t1-t0)*1000:.2f} ms)")
print(f"Functional:  {total_func}  ({(t3-t2)*1000:.2f} ms)")
print(f"Same result? {total_imp == total_func}")

# Key observation: functional version never builds an intermediate list
import sys
imp_list_size = sys.getsizeof(result_imp)
print(f"Imperative list size in memory: {imp_list_size} bytes")
print(f"Functional generator: no intermediate list (lazy evaluation)")
```
