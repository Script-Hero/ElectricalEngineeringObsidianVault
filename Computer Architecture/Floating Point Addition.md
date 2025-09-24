When adding [[Floating Point Number Representation]]s you have to "align the exponents"

## Example
If given $(1.101\times2^2)+(1.0011\times2^3)$, where one exponent is 2 and one exponent is 3, we have to "align the exponent to the bigger one"
- Now the problem looks like $(0.1101\times2^3)+(1.0011\times2^3)$, and both exponents are the same
- The sum here is $10.0000\times2^3$ 
- Because the answer is no longer in scientific notation, we must renormalize it to $1.0\times2^4$
![[floating_point_addition_renormalization.png]]