
## Logic Shifts
**LSL** is Logic Shift Left
**LSR** is Logic Shift Right

Takes the source register data, shifts it, and puts it into the destination register


| *opcode* | *Rm* | *Shamt* | *Rn* | *Rd* |
| :------: | :--: | :-----: | :--: | :--: |
- Note that there are only 2 [[Registers]] involved, so **Rm = 0**
- *Shamt* is shift amount
- With 6 bits, we can shift $2^6=64$ 
	- One register is 64 bits long
	- If you shift for $2^6$ bit positions, all the bits originally in the register are gone 

## Example
For the command
```armasm
LSL, X11, X19, #4 // Left shift X19 by 4 bits and store it in register X11
```
In decimal is

| 1961 |  0  |  4  | 19  | 11  |
| :--: | :-: | :-: | :-: | :-: |

# Other Logic Instructions
AND, ANDI : bit-wise AND
OR, ORI : bit-wise OR
EOR EORI : Exclusive OR
- Note that NOT is done by EOR
```armasm
EOR X9, X10, X12 // if X12 is all 1s, then X9 = NOT(X10); if X12 is all 0s, X9 = X10
```

