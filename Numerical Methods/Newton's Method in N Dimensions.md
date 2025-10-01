[[Newton's Method]] for solving systems of $n$ unknowns and $n$ functions. 
$$
\vec{x}_{n+1}=\vec{x}_n-J_F(\vec{x}_n)^{-1}F(\vec{x}_n)
$$
Where
- $F:\mathbb{R}^k\to\mathbb{R}^k$
- $J$ is the [[Jacobian]] of $X$ 
	- and $J_{F}(\vec{x}_n)^{-1}$ is the inverse of the [[Jacobian]] 

## Practical Computation

Instead of explicitly computing the inverse of the [[Jacobian]], it's easier to:
1. Solve the linear equation $J_F(x_k)\Delta x_k=-F(x_k)$
	1. Where $\Delta x_k$ is the *update step*
2. Update the solution $x_{k+1} + x_k + \Delta x_k$

