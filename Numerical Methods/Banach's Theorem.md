Prove that a function is a *contraction mapping*, such that $$\frac{g(x_2)-g(x_1)}{|x_2 - x_1|}<1$$
You can use Banach's Theorem to prove that this holds true for all $x_1$ and $x_2$ 

1. Choose a domain $D=[a,b]$ that the fixed point $x^*$ lies within
2. Verify that $g(x)$ evaluated at each edge of the domain lies within the domain. That is:
	1. $g(a)\in[a,b]$ and
	2. $g(b)\in[a,b]$
3. Find the maximum value of $g(x)$ within the bounds $[a,b]$. If that maximum value is $<1$, then $g(x)$ is a contraction.