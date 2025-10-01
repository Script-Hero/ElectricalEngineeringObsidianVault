We assume that the data are already in [[Registers]] and the results are stored in [[Registers]] too.
```armasm
ADD X8, X17, X18 // if X17 = a and X18 = b, then X8 = a + b
SUB X9, X17, X19 // X9 = X17 - X19
```

If a data item is not in the register but in the [[Memory]], we need to first get it from the [[Memory]] into a register. This is done by [[D-Type Instructions]]
# Format

| **opcode** |  **Rm**  | **shamt** |  **Rn**  |  **Rd**  |
| :--------: | :------: | :-------: | :------: | :------: |
| *11 bits*  | *5 bits* | *6 bits*  | *5 bits* | *5 bits* |
### Decimal

| 1112 | 18  |  0  | 17  |  8  |
| :--: | :-: | :-: | :-: | :-: |
### Binary
| 10001011000 | 10010 | 000000 | 10001 | 01000 |
| :---------: | :---: | :----: | :---: | :---: |
