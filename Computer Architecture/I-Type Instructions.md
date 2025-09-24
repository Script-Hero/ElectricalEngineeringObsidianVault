Operations on an *immediate*, or a hardcoded value.
- The immediate is a signed number, and can be positive or negative

# Format

| **opcode** | **immediate** |  **Rn**  |  **Rd**  |
| :--------: | :-----------: | :------: | :------: |
| *10 bits*  |   *12 bits*   | *5 bits* | *5 bits* |
## Decimal
For the example
```armasm
ADDI, X9, X9, #1 // X9 += 1
```
The decimal equivalent is 

| 580 |  1  |  9  |  9  |
| :-: | :-: | :-: | :-: |
