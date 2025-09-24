How would we put a big number (for example, 4 million) into a register?

Do it half at a time.

1. In binary, 4 million is $00000000$ $00111101$ $00001001$ $00000000$
2. The upper half has a decimal value of 61, the lower half is decimal 2304
	1. $61\cdot2^{16}+2304=3997694+2304=4,000,000$
3. First, move the upper half into register X19 using the [[D-Type Instructions]] MOVZ and shift to the left for 16  bit positions
```armasm
MOVZ X19, #61, LSL #16
```
4. This leaves register X19 looking like:

| 0000 0000 0000 0000 | 0000 0000 0000 0000 | 0000 0000 011 1101 | 0000 0000 0000 0000 |
| ------------------- | ------------------- | ------------------ | ------------------- |
1. Second, move the lower half into register X19 using MOVK
```armasm
MOVK X19, #2304, LSL 0
```
Leaving X19 as

| 0000 0000 0000 0000 | 0000 0000 0000 0000 | 0000 0000 011 1101 | 0000 1001 0000 0000 |
| ------------------- | ------------------- | ------------------ | ------------------- |

This makes X19 equal to decimal 4 million.