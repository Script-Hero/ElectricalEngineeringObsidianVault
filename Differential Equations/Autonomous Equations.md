Equations where there is no additional variable. Only in terms of $y$. 

Example: $\frac{dy}{dt}=(y-2)(y-6)$
- $y=2, y=6$ are [[Equilibrium Solutions]] because $\frac{dy}{dt}=0=$ at equilibrium.
- Finding the intervals that these solutions are increasing / decreasing upon helps us tell if they're stable equilibrium
	- **STABLE** if the solution is *increasing* after the equilibrium point and *decreasing* before the equilibrium
	- **UNSTABLE** if the solution is *decreasing* after the equilibrium point and *increasing* before 
	- In other [[words]], **local minimums are stable and local maximums are unstable**
	- When the slope is 0 around the local minimum, then the solution is **semistable**

---
*Example: $\frac{dy}{dt}=y(2-y)(y-5)$*
- Equilibrium at $y=2, y=5, y=0$
	1. For $y=5: f(6)<0, f(3)>0$ --> **Asymptotically Stable**
	2. For $y=2: f(3) >0, f(1)<0$ --> **Asymptotically Unstable**
	3. For $y=0: f(1)<0, f(-1)>0$ --> **Asymptotically Stable**
	4. **Note that these only are identified as truly *stable* or *unstable* when you check the second derivative and find curvature**
- $\lim_{t\to\infty}f(t)$




