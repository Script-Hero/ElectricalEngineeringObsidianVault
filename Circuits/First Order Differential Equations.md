Equations with [[Inductors]] and [[Capacitors]] result in equations that involve derivatives requiring us to solve differential equations.

General form is:
$$a\frac{dy}{dt}+by(t)=x(t), y(0)=y_0$$
General solution is:
- A homogenous solution
	- We get by finding the solution when $x(t)=0$
	- Will contain an arbitrary constant
- A particular solution (non-homogenous) depends on the form of $x(t)$

## General Approach to Solving
1. Find the **homogenous solution**
2. Find the particular solution
3. Combine the two solutions to find the general solution
4. Apply initial conditions to resolve arbitrary constant

### Finding the Homogeneous Solution
$$a\frac{dy}{dt}+by(t)=0$$
1. Assume a solution of the form $y(t)=Ae^{st}$
2. Plug this solution into the original equation:
	1. $a\frac d {dt}(Ae^{st})+b(Ae^{st})=0$
	2. $Ae^{st}(as+b)=0$
	3. $as+b=0$ *(This is known as the "characteristic equation")*
	4. $s=\frac{-b}{a}$
3. The homogeneous solution is then found to be $$y_H(t)=Ae^{-bt/a}$$
	1. Note that this works for any arbitrary constant $A$

### Finding the Particular Solution
- We use the method of undetermined coefficients to find the particular solution
- Based on the form of $x(t)$ we will guess at the form of $y_p(t)$ as given by this table:
![[undetermined_coeffecients_table.png]]
**Once we have a general guess at the form of the particular solution, we will plug that guess into the differential equation to determine the coefficients.**

### Combining the Particular and Homogeneous Solution
$$y(t)=y_H(t)+y_P(t)$$
*Note: Do not apply the initial condition until after you have formed the complete solution.*

