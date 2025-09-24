A type of [[Fixed Point Iteration]] root finding algorithm. 
$$
x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}
$$
- Can be extended to complex functions and systems of equations
- Quadratic Convergence

# Applications
-  Solving *n-dimensional problems* using [[Newton's Method in N Dimensions]]
- Solving *constrained optimization problems* using [[Newton's Method for Optimization]]

# Convergence
If:
1. $f(x)$ is continuously differentiable
2. The initial guess $x_0$ is sufficiently close to the root $x^*$
3. $f'(x^*)\neq0$

