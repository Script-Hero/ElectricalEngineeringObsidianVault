Accuracy is measured in terms of the number of bits in error in the least significant bit of the significand. This is called the number of **units in last place** (ULP)
- IEEE 754 guarantees that the number will be within one-half ULP


3 extra bits:
- **Guard bit**
	- The first extra bit beyond the precision of the floating point format
	- If we were using 3-digit precision for 1.3764 (decimal), the guard bit would be the 6
- **Round bit**
	- Second extra bit beyond the precision of the floating point format
	- Plays a roll when deciding whether to round up or down if the guard bit is not enough to decide rounding
- **Sticky bit**
	- Set when there are nonzero bits to the right of the round bit
	- Can distinguish between $0.50\dots0_\text{ten}$ and $0,50\dots01_\text{ten}$  when rounding
	- If any discarded bits beyond the round bit are nonzero, the sticky bit is set to 1
	- If the sticky bit is 0, the rounding problem is the **exact halfway case**

You can use these three bits to determine if we round up or down:
$$rs+g(r\text{ OR }s)$$
 Meaning we round up in any of the following cases:
- Both $r$ and $s$ are 1
- If $g=1$ and *either* $r$ *or* $s$ is 1

However, if these conditions don't trigger, that does not guarantee that we *do not* round up. In the **Halfway Case**:
- If the last kept bit is **even** then we do **not** round up
- If the last kept bit is **odd** then we **do** round up

**This is the *Round to Even* rule.**

# Rounding Policy
"Round to nearest, Ties to Even" is the default
- The result is rounded to the nearest representable value
- If the result falls exactly between two representable values, it rounds to the one with **an even least significant digit** in its binary representation
	- 2.5 rounds to 2 because 2 even
	- 3.5 rounds to 4 because 4 is even

# Example
We want to round $1.0110111_2$ to a 3-bit mantissa
1. Truncate
	1. Keep the first 3 bits of the mantissa --> $1.011$
	2. Guard bit is 0
	3. Round bit is 1
	4. Sticky bit (since there are nonzero bits beyond R) is 1
2. Round
	1. Since R = 1 and S = 1, the truncated part is **not** greater than 0.5
	2. This means we round down, **resulting in 1.011**


