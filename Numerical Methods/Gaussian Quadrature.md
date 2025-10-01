[[Numerical Quadrature]] that achieves the highest possible degree of precision given number of nodes $n$ by selecting both the nodes $x_i$ and weights $w_i$ optimally.
# Nodes and Weights 
- Nodes $x_i$ are the roots of orthogonal polynomials. We use the roots of the $n$th degree [[Legendre Polynomials]] ($P_n$) for standard Gaussian quadrature on $[-1,1]$
- Weights $w_i$ are computed as $w_i=\frac{2}{(1-x_i^2)[P_n'(x_i)]^2}$

From which we construct the Gaussian Quadrature using:
$$
I_{(G)}^{(n)}=\sum\limits_{i=1}^nw_if(x_i)
$$
# Change of Interval
- Since the Gaussian quadrature normally is only defined on $[-1, 1]$, to use it on integrals with a larger domain requires a linear change of variables to map the interval and adjust the weights accordingly. 
Given the integral $\int\limits_a^bf(x)dx$:
- Substitute $x=\frac{b-a}{2}\gamma+\frac{b+a}{2}$ where:
	- $\gamma$ is the new variable in the standard interval $[-1,1]$
	- $\frac{b-a}{2}$ rescales the interval width
	- $\frac{b+a}{2}$ shifts the midpoint of the interval to algin with $\gamma=0$
- Now the differential $dx=\frac{b-a}{2}d\gamma$
- Transforming the integral to $\int\limits_a^bf(x)dx=\int\limits_{-1}^1f(\frac{b-a}{2}\gamma+\frac{b+a}{2})\frac{b-a}{2}d\gamma$
- Transforming the quadrature into $\sum\limits_{i=1}^{n}w_i\cdot f(\frac{b-a}{2}\gamma_i+\frac{b+a}{2})\cdot\frac{b-a}{2}$
- If you are given the complete quadrature (not the prior integral) you replace all $x$ with $\frac{b-a}{2}\gamma+\frac{b+a}{2}$ and transform the weights by *multiplying* with $\frac{b-a}{2}$
# Error and Accuracy
- Error is $E[f]=\frac{f^{(2n)}(\xi)}{(2n)!}\int\limits_{a}^b\prod\limits_{i=1}^n(x-x_i)^2dx$
- Order of accuracy is $O(h^{2n})$
- Degree of precision is $2n+1$
