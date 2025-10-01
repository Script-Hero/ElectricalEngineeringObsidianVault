
A first order ordinary differential equation $\frac{dy}{dx} = f(x,y)$ can be called separable if it can be written as $M(x)dx + N(y)dy=0$.

- Separable equations are important because we can just *integrate both sides* to solve for $y(t)$

--- 
## Are these equations separable?

$\frac{dy}{dx}=x+y^2$
* *Non*separable

$\frac{dy}{dx}=x\cdot y^2$
- Separable
- We can change to $\int\frac{dy}{y^{2}}=\int xdx$
- Solution $\frac{-1}{y}=\frac{x^2}{2}+C$

---
Example: Show that the equation $\frac{dy}{dx}=\frac{x^2}{1+y^2}$ is separable. Then solve.
- Nonlinear 
- No equilibrium solution because no *constant* $y$ value will make the entire solution 0 for all $x$

$\int(1+y^{2})dy= \int x^{2}dx$ -->
$y + \frac{y^{3}}{3}= \frac{x^3}{3}+C$ is our general implicit solution

It's easier to solve in terms of $x$ than $y$:
$x = \sqrt[3]{3y+y^{3}-\frac{3c}{k}}$

---

$\frac{dy}{dx}=\frac{x^2}{y(1+x^3)}$
$\int y dy = \int\frac{x^2}{1+x^3}$
$\frac{1}{2}y^{2}= \frac{1}{3}\ln|1+x^3|$

---
## We must separate our variables because we must integrate w respect to $x$!

$y'=3y-2$ --> $\frac{y'}{3y-2}=1$ --> $\int\frac{y'}{3y-2}dx=\int1dx$  --> $\frac{1}{3}\ln|3y-2|=x$ 