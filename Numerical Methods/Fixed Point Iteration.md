A sequence $x_{n+1} = f(x_n)$ which converges to a fixed point $x_{\text{fixed}}$. You can prove that a point is a fixed point because $x_\text{fixed} = f(x_\text{fixed})$.

# Convergence Criterion
For some fixed point iteration $g(x)$ with fixed point $x^*$ 
## Both
1. Initial guess $x_0$ must be sufficiently close to $x^*$ 
2. $g(x^*)=x^*$
## Linear Convergence
1. $|g'(x^*)|<1$
	1. The magnitude of the derivative at the fixed point determines the *convergent rate*
3. $g(x)$ and $g'(x)$ must be continuous
4. $|g(x_2)-g(x_1)|\leq L|x_2 - x_1|$, where $0<L<1$ is the Lipschitz constant
## Quadratic Convergence
1. $g'(x^*)=0$ 
2. $g''(x^*) \neq 0$ 
3. $g''(x)$ is continuous near $x^*$ 
4. The function must be smooth (at least twice differentiable) near the fixed point $x^*$
