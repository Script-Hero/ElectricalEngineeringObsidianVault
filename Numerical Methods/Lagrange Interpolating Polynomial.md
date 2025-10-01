The Lagrange Interpolating Polynomial is the unique polynomial of lowest degree that interpolates a given set of data. 

Given $n$ pairs of $(x_i,y_i)$, the Lagrange interpolating polynomial passes through each point exactly and is of degree at most $n-1$. 

**Lagrange Interpolating Polynomial** Defined as 
$$P(x)=\sum\limits_{i=0}^ny_iL_i(x)$$
Where $L_i(x)$ are the *Lagrange Basis Polynomials*, defined as
$$
L_i(x)=\prod\limits_{j=0, j\neq i}^n \frac{x-x_j}{x_i-x_j}
$$
# Methodology

1. Construct basis polynomials for each target $(x_i,y_i)$ Each basis polynomial is constructed to be $1$ at $x=x_i$ and $0$ at all other $x_j (j\neq i)$. This ensures that $P(x)$, the constructed polynomial, matches $y_i$ at $x_i$
	1. For example for $L_0(x)=\frac{(x-x_1)(x-x_2)\dots(x-x_n)}{(x_0-x_1)(x_0-x_2)\dots(x_0-x_n)}$
2. Sum each $L_i$ to construct the Lagrange Interpolating Polynomial

# Properties
 - Has degree of at most $n-1$ 
 - Uniqueness, only one polynomial for any given set of points 

# Error Estimation
Given by: 
$$f(x) - P_n(x)=\frac{f^{(n+1)}(\xi)}{(n+1)!}\prod\limits_{i=0}^{n}(x-x_i)$$
Where:
- $\xi$ is some point in the interval containing $x$ and the interpolation points $x_0,x_1,\dots,x_n$ 
- $f^{(n+1)}(\xi)$ is the $(n+1)$th derivative of $f(x)$ at $\xi$ 
	- If $f(x)$ is smooth (higher derivates are small) the error is small 
	- As $n$ increases (more points) the error decreases
- $\prod\limits_{i=0}^n(x-x_i)$ is the product of the terms involving the interpolation points
	-  When $x$ is farther from the desired interpolation points, the error is larger

### Bounding
$$|f(x)-P_n(x)|\leq \frac{M}{(n+1)!}\max\limits_{x\in[a,b]}|\prod\limits_{i=0}^n(x-x_i)|$$
- If $f^{(n+1)}(\xi)\leq M$ for all $\xi$ in the interval

**For example:** Suppose $f(x) = e^x$ and we interpolate points $x_0=0$ and $x_1=1$ using a Lagrange polynomial $P_1(x)$.
1. The second derivative $f''(x)=e^x$ so $M=e$ on $[0,1]$
2. The error is $f(x)-P_1(x)=\frac{e^\xi}{2!}(x-0)(x-1)$ for some $\xi\in[0,1]$
3. The *maximum error* is $|f(x)-P_1(x)|\leq\frac{e}{2}\cdot\max\limits_{x\in[0,1]}|x(x-1)|$
4. You can plug in specific values of $x$ to evaluate the error at different points
### Interpretation
- Choosing points that are **equally spaced** can lead to large errors for functions with higher curvature (e.g. $\frac{1}{1+x^2}$)
- Using roots of the Chebyshev polynomials (see [[Chebyshev Iteration]]) minimize the error and avoid Runge's phenomenon (see [[Explicit Runge-Kutta Methods]])