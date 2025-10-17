---
~
---
### Boolean Algebra
- <underline>Distributive property of Boolean Algebra</underline>
	- $a * (b + c) = (a * b )+ (a * c)$
	- $a + (b*c)=(a+b)*(a+c)$
- DeMorgan's Law
	- $(a+b)'=a'b'$
	- $(ab)'=a'+b'$
* Function's Complement
	* Complement of $f$ is $f'$ ("not $f$")
	* Apply DeMorgan's Law repeatedly
* Canonical Form / Sum of Minterms of a Function
	* Sum of products form where every *term* that is summed together has exactly every single variable in it once (negative form counts)
	* Think of it as a truth table turned into a function
	* Canonical Form is *unique* for every function
	* You can convert sum of minterms into binary!
		* For example $abcde \rightarrow b11010 \rightarrow 26$
		* Can say "sum of minterms for (input)" or $H = \Sigma m(26,32,10)$
- Karnaugh Maps (K-maps)
	- Simplify boolean expressions
	- Given 3 inputs $x,y,z$ we write the truth table formatted like this:
		```
		x|yz
		 | 00 | 01 | 11 | 10
		 |------------------
		0| 1  | 1  | 0  | 0
		1| 0  | 0  | 1  | 1 
		```
		- We can combine adjacent cells that are both 1s by ignoring the difference in the terms.
			- In this example, $(xyz)'$ and $z(xy)'$ are both 1, so we know we can ignore the $z$ (it has no impact on the output) and simplify the term to $(xy)'$
	- You can do this with arbitrary number of variables
	- Draw circles of $2^n$ sizes to combine terms

### Circuit Components 
- Decoder
	- Takes $n$ bit binary input and outputs 1 signal to a corresponding port
	- *Example* if input is $b101$ then only the 5th (of 8) outputs high signal
- Encoder
	- Opposite of decoder ($2^n$ inputs, $n$ outputs)
		- Can use Priority Encoder (extra [[Processor]] tacked in front of encoder to handle simultaneous inputs conflict)
- Multiplexer
	- Like a selector unit
	- Has multiple inputs, one output, and has an extra "select" input to determine which of the multiple inputs to send to the output
- cMOS
	* nMOS [[Transistor]]
		* *Symbol without circle*
		* Sending a 1 into side (gate) means any input signal will pass through
		* Called nMOS because the electrons inside are *negative* and therefore a positive outside charge attracts them to complete the circuit
			* ***Can never work from VCC input due to this!***
			* Used near ground
		* "Pull down circuit"
	* pMOS [[Transistor]]
		* *Symbol with circle*
		* Sending a 1 into side (gate) *blocks* any input signal trying to pass through
		* Positive charge inside so needs negative charge to complete circuit
			* ***Can never work near ground!***
			* Used near VCC
		* "Pull up circuit"
	* If neither the "Pull up circuit" or the "pull down circuit" can contain a path from [[Power]] or ground to $F$, the output is "Floating" and has no value
	* If both output and ground contain a path (as in there is a path from VCC to F to the ground) then the output is ambiguous
* Gate Completeness
	* Can implement any functions
	* {and, or, not} is complete
	* {nand} is complete
* Circuit Costs
	* **Delay** = the time from input changing to correct stable outputs
		* When we chain gates we add this delay
	* **Size** = number of transistors 
		* Each *input* on a gate requires 2 transistors
* NAND [[Implementation]]
	* Just using DeMorgan's law repeatedly.
	* Ex: Implementing $(AB + CD)$
		* $=(AB + CD)''$
		* $=((AB)' \cdot (CD)')'$
		* You can now implement it with 3 NAND gates: NAND(NAND(A,B), NAND(C,D))
	* You're allowed to put the circles (turning AND into NAND) before the input or after the output on the circuit diagram
	* NAND gates are physically more efficient than NOR gates but NOR gates can do it too
* Numbers:
	* [[2's Compliment]]: leftmost digit is signal
		* Flip all bits, add 1, convert binary to decimal and put negative sign in front
	* Fractional binary number
		* Every binary digit to the right of the decimal point is the "$\frac{1}{2^n}$'s place"
		* 101.11 = 5 + ($\frac{1}{2}+\frac{1}{4}$) 
		* If they go 1010101.11111111111111111 (the repeated 1s after decimal) then it's 1-$\epsilon$
		* learn some shit with exponential form with bias and whatever
	* IEEE:
		* Convert the decimal to pure fractional binary.
		* Convert to scientific notation with 8-bit exponent, and add 127 to the exponent to bias it, then remove the leading one from the mantissa (decimal part)
	* Hex
* FPGA / LUT
	* store truth table in [[Memory]], LUT = "Look up table"
	* Select with MUX
	* You have a mux for every column of [[Memory]] / output function