#Diff-EQ

- a differential equation is an equation containing the derivative of a function 
- ODE = ordinary differential equation = depends on single variable
- PDE = partial differential equations = depends on multiple variables and therefore partial derivates appear
- Differential equations can either be [[[Linear Differential Equations]]] or nonlinear
---
An algebraic equation is $x^{2}- 3x + 10 = 0$ and it's solution is $\frac{3}{2} \pm \sqrt{31}i$ . We are solving for a **numeric value**.

A differential equation is $\frac{dx}{dt}-3x + 10 = 0$ . We are solving for a **function** of the independent variable (in this case $x(t)$).

---
- The order of a differential equation is the level of the derivative involved. If we are solving for $\frac{dx}{dt}$ then it is a first order differential equation because it's a first derivative
- Example of a second order diffeq is $y'' -ty=0$

- look up Airy's equation (not important just neat lol)
---
Example 1:
	Given $\frac{dy}{dt} = 0$ find $y(t)$ on some interval of $t$
		Solutions: $y(t) =1$, $y(t) =2$, $y(t) = 3$, etc...
		In general the solution is $y(t) = C$
		__NOTE__ that the solution must be a function!

---
Example 2:
	Given $\frac{dy}{dt}  = \sin{(3t)}$ find $y(t)$
		Solution: $y(t) = -\frac{1}{3}\cos{(3t)} + C$
			We can verify that this is correct because $y'(t) = \sin{(3t)}$ which is our starting equation

We found this solution by using the integral

---
* Some differential equations may not have any solutions at all
	* Like $\frac{dy}{dt} = \frac{dy}{dt}+1$ lol
---

Example:

Let's prove that $y_1(t)=e^{-3t}$ and $y_2(t)=e^t$  are solutions of the ODE $y^{n}+2y' -3y =0$
	- First let's find $y_1'$ which is $-3e^{-3t}$ and let's also find $y{_1}''$  which is $9e^{-3t}$
	- Then we find $y_{2}'=e^t$ and $y_{2}''=e^t$
	- With $y_1$ our ODE becomes $e^{-3nt}-6e^{-3t}-3e^{-3t}=0$
	- 