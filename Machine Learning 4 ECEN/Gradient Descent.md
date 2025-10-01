If we have weights $w(t)$ and you take a step a step of size $\eta$ in the direction $\hat v$ such that $w(t+1)=w(t)+\eta\hat v$, **gradient descent** is a way to find the direction that minimizes $E_\text{in}(w(t+1))$, the [[In-Sample Error]] at the [[Current]] time step $t$.

The best direction to move is:
$$\hat v = -\frac{\nabla E_\text{in}(w(t))}{||\nabla E_\text{in}(w(t))||}$$
It's also important to keep $\eta$, the learning rate, at a "goldilocks zone" for learning to work.


**Gradient descent can minimize any smooth function.**

## Algorithm
- We define $\eta_t=\eta\cdot||\nabla E_\text{in}(w(t))||$
	- Because $||\nabla E_\text{in}(w(t))||\rightarrow0$ as the algorithm gets closer to the minimum
- Simplifies the gradient descent step to $\eta_t\hat v = -\eta \nabla E_\text{in}(w(t))$


1. Initialize at step $1=0$ to $w(0)$
2. **for** $t=0,1,2,\dots$ **do**
	1. Compute the gradient
		1. $g_t=\nabla E_\text{in}(w(t))$
	2. Move in the direction $v_t=-g_t$
	3. Update the weights:
		1. $w(t+1)=w(t)=\eta v_t$
	4. Iterate 'until it is time to stop'
3. **end for**
4. Return the final weights.