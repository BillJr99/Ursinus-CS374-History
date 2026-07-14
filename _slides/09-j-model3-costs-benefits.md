---
transition: zoom
---

## Model 3: Paradigm Costs and Benefits

Paradigm choice is not just an aesthetic preference — it has measurable consequences for memory use, parallelizability, and readability. The functional generator in this model never materializes a full intermediate list, while the imperative version builds one in memory before summing it. This difference seems trivial at 100 items but matters enormously at 100 million. Keep an eye on the memory numbers printed at the end.

The choice of paradigm shapes what is easy and what is hard. Run this performance comparison:

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

### Critical Thinking Questions

8. The functional version uses a generator expression. What does "lazy evaluation" mean in this context, and why does it save memory?
9. For a list of 100,000 elements, which approach do you expect to be faster? Run it and report your findings.
10. If you wanted to parallelize this computation across 4 CPU cores, which style (imperative or functional) is easier to split safely? Why?
