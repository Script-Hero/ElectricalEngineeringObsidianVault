[[Multiplication]] with [[Floating Point Number Representation]]s

1. Multiply the sign bit
2. Multiply the real part of the number
3. Add the exponents and subtract the bias term

$$\text{Product}=(s_1\times s_2)\cdot(n_1\times n_2)\cdot 2^{(\text{exp}_1+\text{exp}_2-\text{bias})}$$


![[floating_point_multiplication.png]]