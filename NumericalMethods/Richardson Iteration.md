A type of [[Fixed Point Iteration]] 
# Richardson Iteration in 1 Dimension
## Definition
For 1 dimension, the iteration can be written as:	$$x_{n+1} = x_n - \alpha f(x_n)$$- Where $\alpha$ is a constant step size
## Convergence
For $\alpha$ chosen such that $|1-\alpha f'(x^*)|<1$, convergence is **linear.**
- Otherwise there is **no convergence at all**
# Richardson Iteration in $n$ dimensions
Fixed point iteration for solving systems of linear equations. Specifically:
- Given a set of linear equations in matrix form $Ax=b$
- The **Richardson Iteration** is $x_{k+1} = x_{k} + \omega(b-Ax_{(k)})$ 
	- Where $\omega$ is a *scalar parameter* that has to be *chosen* so that the sequence $x^{(k)}$ converges

If the iteration converges to a fixed point, that fixed point will be the approximate solution to $Ax=b$.
### Convergence
- Using error analysis, we find that if $||I-\omega A|| < 1$ then the system will converge
- If $A$ is *symmetric [[Positive Definite]], the error converges to 0 if $|1-\omega\lambda_j|<1$ for all eigenvalues $\lambda_j$. If all eigenvalues are positive, the optimal choice for $\omega_\text{opt}=\frac{2}{\lambda_\text{min}(A) + \lambda_\text{max}(A)}$ which gives the simplest [[Chebyshev Iteration]]. 

**The Richardson Iteration is equivalent to *Gradient Descent* where $\omega$ is replaced by a learning rate instead of calculated using the Jacobian.**




