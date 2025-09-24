Conditional Branch instruction. Invokes a branch on a condition.

# Types
## CBZ
**CBZ** (*register*) (*address*)
- Executes the branch stored at *address* if the contents of *register* are zero

## CBNZ
**CBNZ** (*register*) (*address*)
- Executes the branch stored at *address* if the contents of *register* are **not** zero

# Format

| **opcode** |  address  | register |
| :--------: | :-------: | :------: |
|  *8 bits*  | *19 bits* | *5 bits* |
## Decimal
For the example
```armasm
CBNZ X19, Exit // Go to Exit if X19 != 0
```
The decimal equivalent is:

| 181 | Exit | 19  |
| :-: | :--: | :-: |
# Example
A *while* loop constructed in LEGv8 assembler code:
```armasm
Loop:
	LSL X10, X22, #3 // Temp reg X10 = 8 * i (2^3 * i)
	ADD X10, X10, X25 // X10 address of save[i]
	LDUR X9, [X10, #0] // Temp register X9 = save[i]
	SUB X11, X9, X24 // X11 = save[i] - k
	CBNZ X11, Exit // go to Exit if save[i] != k (in other words, X11 != 0)
	ADDI X22, X22, #1 // i = i + 1
	B Loop // Go to Loop (which is at the top of the execution)
Exit:
	// this is intentionally left empty, so we can break the loop by branching here
```
To help, think of the registers as pseudocode variables:
```
X22 : i
X25 : start adr of A[i]
X9 : hold A[i]
X11 : A[i] - k
X24 : k
```
When assembled, the instructions and their addresses are:

| *Address* |      |     |     |     |     |
| :-------: | :--: | :-: | :-: | :-: | :-: |
| **80000** | 1691 |  0  |  3  | 22  | 10  |
| **80004** | 1112 | 25  |  0  | 10  | 10  |
| **80008** | 1896 |  0  |  0  | 10  |  9  |
| **80012** | 1624 | 24  |  0  |  9  | 11  |
| **80016** | 181  |     |  3  |     | 11  |
| **80020** | 580  |  1  |     | 22  | 22  |
| **80024** |  5   |     | -6  |     |     |
| **80028** | ...  | ... | ... | ... | ... |
|    ...    | ...  | ... | ... | ... | ... |
