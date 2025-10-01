## Unconstrained Optimization
$x_{k+1}=x_k - [\nabla^2f(x_k)]^{-1}\nabla f(x_k)$

Where:
- $\nabla x_k$ is the gradient of $f(x)$ at $x_k$
- $\nabla ^2 f(x_k)$ is the [[Hessian]] of $f(x)$ at $x_k$

### Practical Computation
1. Evaluate the gradient $\nabla f(x_k)$
2. Evaluate the [[Hessian]] $\nabla^2 f(x_k)$
	1. Ensure the [[Hessian]] is [[Positive Definite]] to ensure that the solution is the local *minimum*. To find the *maximum*, ensure the [[Hessian]] is Negative Definite
3. Solve the linear system $\nabla^2 f(x_k) \Delta x_k=-\nabla f(x_k)$
4. Update the solution $x_{k+1}=x_k+\Delta x_k$


## Constrained Optimization
Use [[Lagrange Multiplier]]s to construct a system of equations. 

1. Given minimization function $f(x)$ and constraint function $h(x)=0$, we construct the system of equations $\nabla f(x)+\sum\limits_{i=1}^m\lambda_i\nabla h_i(x)= 0$.
2. We can solve this using [[Newton's Method]]: $\begin{bmatrix}\nabla^2 f(x_k) & \nabla h(x_k)^T \\ \nabla h(x_k) & 0\end{bmatrix}\begin{bmatrix}\Delta x \\ \Delta \lambda \end{bmatrix} = \begin{bmatrix}-\nabla f(x_k) \\ -h(x_k) \end{bmatrix}$ 
	1. Where $\nabla^2 f(x_k)$ is the [[Hessian]] of the objective function
	2. And $\nabla h(x_k)$ is the [[Jacobian]] of the constraints
3. Finally, we update the variables using $x_{k+1} = x_k + \Delta x$ and $\lambda_{k+1} = \lambda_k + \Delta \lambda$

