1. Convert binary number to *scientific notation*
2. Format is $(-1)^s\cdot(1 + \text{significand})\cdot2^{\text{exponent}}$


## Steps
1. Given decimal 5
2. Convert to binary 101
3. Convert to scientific notation $1.01\times2^2$
4. Determine sign bit --> positive 5 so sign bit is 0
5. Add bias (127) to exponent 2 = 129 decimal
6. Convert 129 biased exponent decimal to binary --> 10000001
7. Determine mantissa (fractional part after the leading 1)
	1. Fractional part here is .01 --> mantissa is 01000000000000000000000 (23 bits)
8. Construct floating point notation:
	1. S | E | M
	2. answer is **0 10000001 01000000000000000000000**


### Single Precision

| Sign  | Exponent | Significand |
| :---: | :------: | :---------: |
| 1 bit |  8 bits  |   23 bits   |
- Bias is 127
### Double Precision
| Sign  | Exponent | Significand |
| :---: | :------: | :---------: |
| 1 bit | 11 bits  |   52 bits   |
