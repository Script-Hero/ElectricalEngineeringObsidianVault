$\text{Multiplicand}\times\text{Multiplier}$
- The product is usually longer (more digits) than either the multiplier or the multiplicand. For the worst case:
	- $(n\text{ digits}-\text{multiplicand})\times(m\text{ digits} - \text{multiplier})=(n+m)\text{ digits}-\text{product}$
- If we are limited to either a $0$ or $1$ value, our task is easier:
	- For each $1$ bit of the multiplier, place a copy of the multiplicand in the proper place
	- For each $0$ bit of the multiplier, do nothing

## Algorithm
![[multiplication_algorithm.png]]

![[multiplication_register_view.png]]

1. Initialize [[Registers]]
	1. Store Multiplicand in register M
	2. Store Multiplier in the **lower half** of the product register P
	3. Set the upper half of the product register P to 0
	4. Set a counter to the number of bits in the multiplier
2. Repeat for each bit of the multiplier:
	1. Check if the least significant bit of the product register P0 = 1. 
		1. If yes, add the multiplicand M to the **upper half** of the product register
		2. Otherwise, do nothing
	2. **Right shift** the entire **product register** (preserve sign)
	3. Decrement the counter
3. Repeat until the counter reaches 0
4. Final product is stored in **P** register

## Example: $5\times6$
1. Initialize
	1. Multiplicand = 0101
	2. Multiplier = 0110
	3. Product = 0000 0110
	4. Counter = 4
2. Start loop:
	1. Product LSB is 0
		1. Product = 0000 0011
		2. Counter = 3
	2. Product LSB is 1
		1. Product = 0101 0011 (add multiplicand to left half)
		2. Product =  0010 1001 (right shift product)
		3. Counter = 2
	3. Product LSB is 1
		1. Product = 0111 1001 (add multiplicand to left half)
		2. Product = 0011 1100 (right shift product)
		3. Counter = 1
	4. Product LSB is 0
		1. Product = 0001 1110
		2. Counter = 0
3. Break loop because Counter = 0
4. Product register is 16 + 8 + 4 + 2 = 30 which is the correct answer for 5 times 6