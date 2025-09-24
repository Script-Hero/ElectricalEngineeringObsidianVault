---
~
---
- brush up on level curves = whatever shape
## 14.1 Functions of Several variables
- *A function of 2 variables* is $f(x,y)=z$, and the domain of $z$ is a 2-dimensional shape on the $xy$ plane (like a shadow)
- **Level curves** are lines tracing all the points in the $(x,y)$ plane that create a $z$ level of $f(x,y)=k$ where $k$ is some constant.
	- Graph of many level curves = contour plot
- *A function of 3 variables* is $f(x,y,z)=w$ where the function is in 4d space and the domain is some 3D shape

## 14.3 Partial Derivatives
- We take derivatives of multi-variable functions with respect to a single variable, and treat the other variables as constants.
	- *Example* $f(x,y)=x^2+2y^3-4xy$ 
		- $f_{x}(x,y)=2x-4y$
		- $f_{y}=6y^2-4x$
- We can take as many partial derivatives as the equation is based on ($f(x,y,z)$ means we can find $f_{x},f_{y},f_{z}$).
- We can also take the partial derivative of a partial derivative, notated $f_{xx},f_{xy}, f_{yx}$ etc
- **Clairaut's Theorem** says $f_{xy}(a,b)=f_{y,x}(a,b)$ if they're both continuous

## 14.4 Tangent Planes and Differentials
- We use the tangent plane to approximate the surface of a function at a point:
- $z=f_{x}(x_0,y_0)(x-x_0)+f_{y}(x_0,y_0)(y-y_0)$
	- Normal line is $-\frac{1}{z}$
- $dz=f_{x}dx+f_{y}dy$ is change height
- We can use this to approximate a point on a function by $f(x_{0}+dx, y_{0}+dy)\approxeq f(x_{0},y_0)+f_{x}(x_{0},y_{0})dx+f_{yx}(x_{0},y_{0})dy$
## 14.5 The Chain Rule
If $u=f(x_1,x_2,x_3,...,x_n)$ and each $x_i$ is a function of $t_1,t_2,t_3,...,t_n$ then $$\frac{\delta u}{\delta t_1}=\frac{\delta u}{\delta x_{1}}\frac{\delta x_1}{\delta t_1}+\frac{\delta u}{\delta x_{2}}\frac{\delta x_2}{\delta t_2}+...+\frac{\delta u}{\delta x_{n}}\frac{\delta x_n}{\delta t_n}$$
- Implicit differentiation: $\frac{\delta z}{\delta x}=-\frac{\frac{\delta F}{\delta x}}{\frac{\delta F}{\delta z}}$ and $\frac{\delta z}{\delta y}=-\frac{\frac{\delta F}{\delta y}}{\frac{\delta F}{\delta z}}$

## 14.6 Directional Derivatives
- $\nabla f(x_0,y_{0})\cdot u$ where is $u$ is a *unit length* direction vector
	- $\nabla f(x,y) = <f_{x}(x,y),f_{y}(x,y)>$
- Maximum rate of change at $(x_0,y_0)$ when $u$ and $\nabla f$ are in the same direction
	- Shortcut: Maximum at $P=|\nabla f(P)|$
- Minimum when opposite direction of $\nabla f$
- Tangent plane to a level surface = $\nabla F(x_0,y_0,z_{0)}\cdot <x-x_{0}, y-y_{0}, z-z_0>$
	- $F_{x}(x_0,y_0,z_0)(x-x_0)+F_{y}(x_0,y_0,z_0)(y-y_0)+F_{z}(x_0,y_0,z_0)(z-z_0)$
	- **normal line** is the tangent line with perpendicular slope

## 14.7 Maximum and Minimum
1. Find *critical points* where $f_{x}(a,b)=0$ and $f_{y}(a,b)=0$ 
2. Classify these critical points using the *second derivative test*
3. Let $D=D(a,b)=f_{xx}(a,b)f_{yy}(a,b)-(f_{xy}(a,b))^{2}$
	1. $D>0$ means min or max
		1. $f_{xx}(a,b)>0$ then $(a,b,f(a,b))$ is **min**
		2. $f_{xx}(a,b)<0$ then $(a,b,f(a,b))$ is **max**
	2. $D<0$ then $(a,b,f(a,b))$ is a **saddle point**

- **Extreme Value Theorem** if $f$ is closed and continuous on bound then max and min on bound exists 

## 14.8 Lagrange Multipliers
- Maximize or minimize a given function by restricting our bound to a level curve $g(x,y)=k$ 
- Tutorial:
	1. Find all $x,y,\lambda$ such that $\nabla f(x,y) = \lambda \nabla g(x,y)$ and $g(x,y)=k$ 
	2. Evaluate $f$ at all points from step 1, the largest value is absolute max and smallest is absolute minimum
Alternatively
1. Constraint is given as $g(x,y,z)=k$
2. Construct new function $F(x,y,z,\lambda)=f(x,y,z)-\lambda(g(x,y,z)-k)$
3. Solve so that $F_x=0,F_y=0,F_z=0,F_{\lambda}=0$
4. Find $x$ and $y$ in terms of $\lambda$ and solve a system of equations to get $\lambda$
5. Once we have lambda we plug it back into $x$ and $y$ to get the actual values