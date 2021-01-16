---
transition: zoom
---

## Machine Language

- Look up the opcode and manipulate registers directly
  - Add, subtract, *etc.*

| Instruction Type | Opcode (6 bits) | Data (26 bits)                                                           |
|------------------|-----------------|--------------------------------------------------------------------------|
| R-Type           | xxxxxx          | rs (5 bits), rt (5 bits), rd (5 bits), shift (5 bits), function (6 bits) |
| I-Type           | xxxxxx          | rs (5 bits), rt (5 bits), immediate (16 bits)                            |
| J-Type           | xxxxxx          | 26-bit address                                                           |