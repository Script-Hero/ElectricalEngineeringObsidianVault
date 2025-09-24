For a 1-bit binary adder, you have $X$ (number 1), $Y$ (number 2), and $C_\text{in}$ the carry-in, and the output is the sum bit $S$ and a $\text{Carry}_\text{Out}$ bit.
- For the [[Ripple Carry Lookahead Adder]]

This follows the truth table:
![[addition_truth_table.png]]

Which is represented by the logic gate operations:
1. $$\text{Sum} = X\oplus Y\oplus C_\text{in}$$
2. $$\text{Carry}_\text{Out}=XY+C_\text{in}+YC_\text{in}$$

## Overflow
1. When **adding** operands with **different** sign bits, **overflow can *never* occur**
2. When **subtracting** operands with the **same** sign bit, **overflow can *never* occur**
![[addition_subtraction_overflow_table.png]]

### 1-Bit ALU
![[1_bit_alu.png]]


