Restoring Division (Binary Division Algorithm)

# Algorithm
![[division_algorithm.png]]

![[divison_illustrtion_registers.png]]

1. Initialize Registers
	1. Place dividend (**N**) in the **lower half** of the remainder register
	2. Set the **upper half** of the remainder register to $0$s 
	3. Load the divisor to register D
	4. Set a counter equal to the number of bits in the dividend
2. Loop until the counter = 0:
	1. Shift the remainder register **left** by 1
	2. Subtract the divisor from the left half of the result (remainder register)
	3. Check the remainder
		1. If $\text{remainder}\geq0$, set the **rightmost quotient bit** to 1 (not add, just set)
		2. If $\text{remainder}<0$ restore the previous value (undo subtraction) by adding the divisor back to the leftmost half of the remainder and set the rightmost quotient bit to 0
	4. Decrement the counter
3. The quotient is the lower half of the remainder register, and the remainder is the upper half

## Example: $9\div2$
1. Initialize registers
	1. Dividend (N) = 1001 (9 in decimal)
	2. Divisor (D) = 0010 (2 in decimal)
	3. Result register = 0000 1001 (remainder & quotient)
	4. Counter = 4
2. Loop:
	1. Left shift product register: 0001 0010
	2. Subtract divisor from left half 0001 - 0010 = -1 in decimal
		1. Negative, so we reset, result register = 0001 0010
		2. Set LSB of quotient to 0
	3. Counter = 3
	4. Left shift result register: 0010 0100
	5. Subtract divisor from left half of register 0010 - 0010 = 0 
		1. not negative, keep subtraction and set LSB to 1
		2. result register = 0000 0101
	6. Counter = 2
	7. Left shift result register: 0000 1010
	8. Subtract 0 - 2 = -2
		1. Negative, so we reset, result register = 0000 1010
		2. Set LSB of quotient to 0
	9. Counter = 1
	10. Left shift result register: 0001 0100
	11. Subtract 1 - 2 = -1
		1. Negative, so we reset, result register = 0001 0100
		2. Set LSB of quotient to 0
	12. Counter = 0
		1. Break
3. Result: quotient is 4 with remainder 1 (correct)

