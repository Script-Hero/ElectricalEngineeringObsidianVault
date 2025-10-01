Exchange data in [[Memory]] with data in [[Registers]]. 

**Alignment:** In many computers, *[[words]]* must start at address multiples of 4, and *double-[[words]]* must start at address multiples of 8
- ARMv8 and Intel X86 don't need alignment. 
- ARMv7 and MIPS do need alignment
- ARMv8 Instruction fetch needs alignment (an instruction is 4-byte long) as well as stack access

**Index Register:** related to alignment. For example
```armasm
LDUR X9, [X22, #64]
```
Can have 64 as the start address, and update X22 by X22 + 8 every time, so X22 is the **index register**.

# Operations
## Load
**Load** (*register number*) (*[[Memory]] address*)
- [[Memory]] address = content of base register + offset
```armasm
LDUR X9, [X22 #64] // Load the contents of register X22 + 64 bits into the register X9
```
## Store
**Store** (*register number*) (*[[Memory]] address*)
- [[Memory]] address = content of base register + offset
```armasm
STUR X8, [X19, #4] // Move the contents of register 8 to the memory address that is the contents of register X19 + 4 bits
```

## MOVZ
**MOVZ** (*register*) (*immediate*)
- Move the immediate number to the least quadrant of the destination register, and fill the rest with 0s.
```armasm
MOVZ X9, #255
```
The machine code for this instruction is 

| 110100101 | 0000 0000 1111 1111 | 01001 |
| --------- | ------------------- | ----- |

After this executes, the contents of X9 is:

| 0000 0000 0000 0000 | 0000 0000 0000 0000 | 0000 0000 0000 0000 | 0000 00000 1111 1111 |
| ------------------- | ------------------- | ------------------- | -------------------- |

Afterwards, we perform the [[Logic Instruction]]
```armasm
LSL X9, X9, #16 // shift the data left by 16 bits (1 halfword)
```

Now X9 is

| 0000 0000 0000 0000 | 0000 0000 0000 0000 | 0000 00000 1111 1111 | 0000 0000 0000 0000 |
| ------------------- | ------------------- | -------------------- | ------------------- |
After we do
```armasm
MOVK X9, #255
```

X9 becomes

| 0000 0000 0000 0000 | 0000 0000 0000 0000 | 0000 00000 1111 1111 | 0000 0000 1111 1111 |
| ------------------- | ------------------- | -------------------- | ------------------- |

## MOVK
**MOVK** (*register*) (*immediate*)
- Move the immediate number to the least quadrant of the destination register, *and keep the rest unchanged*
# Format

| **opcode** | **address** | **op2**  |  **Rn**  |  **Rd**  |
| :--------: | :---------: | :------: | :------: | :------: |
| *11 bits*  |  *9 bits*   | *2 bits* | *5 bits* | *5 bits* |
- The address is a *signed number* and can represent $-256$ to $+255$
### Decimal
For the example
```armasm
LDUR X9, [X22 #64] // Load the contents of register X22 + 64 bits into the register X9
```
the decimal opcode is

| 1986 | 64  |  0  | 22  |  9  |
| :--: | :-: | :-: | :-: | :-: |
