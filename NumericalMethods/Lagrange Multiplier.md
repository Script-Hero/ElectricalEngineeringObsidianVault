Used for optimization problems (finding the *maxima* or *minima* of a function) subject to constraint equations.
$$
\mathbf{L}(x,\lambda)=f(x)+\langle\lambda,g(x)\rangle
$$
Where:
- $\langle\cdot,\cdot\rangle$ denotes the *inner product*
- $f(x)$ is the function being minimized or maximized
- $g(x)=0$ is a constraint on $f(x)$
- $\lambda$ is the *Lagrange Multiplier*

### Methodology
1. We construct an equation $\mathbf{L}$ as a function of $x$ and the Lagrange Multiplier $\lambda$. 
	1. $L=f(x)+(\lambda \cdot g(x))$
2. Find stationary *saddle points* of $\mathbf{L}$, meaning all partial derivatives should be $0$
	1. $\frac{\delta\mathbf{L}}{\delta x}=0$
	2. $\frac{\delta\mathbf{L}}{\delta \lambda}=0$
	3. or equivalently $\frac{\delta f(x)}{\delta x}+\lambda \cdot \frac{\delta g(x)}{\delta x} =0$ with $g(x)=0$
3. The solution is always a *saddle point* of $\mathbf{L}$, and can be identified using the [[Positive Definite]]ness of the [[Hessian]].
	1. The constructed equation is solved using [[Newton's Method for Optimization]]


