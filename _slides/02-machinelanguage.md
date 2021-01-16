---
transition: zoom
---

## Machine Language

- Look up the opcode and manipulate registers directly
  - Add, subtract, *etc.*

| Instruction Type | Opcode (6 bits) | Data (26 bits)                                                           |
|------------------|-----------------|--------------------------------------------------------------------------|
| R-Type           | xxxxxx          | rs (5), rt (5), rd (5), shift (5), function (6)                          |
| I-Type           | xxxxxx          | rs (5), rt (5), immediate (16)                                           |
| J-Type           | xxxxxx          | 26-bit address                                                           |