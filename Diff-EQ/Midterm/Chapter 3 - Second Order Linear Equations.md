## 3.1 Homogenous Equations with Constant Coefficients
A second order differential equation has the form $\frac{d^{2}y}{dt^{2}}=f(t,y,y')$

**Standard form:** $p(t)y'' + q(t)y'+r(t)y=g(t)$
- **Homogenous** if $g(t)=0$
- Otherwise **Nonhomogenous**

#### Solving second order homogenous linear differential equations
- Given $ay'' + by' +cy=0$
- We break it into its **characteristic equation** $ar^{2}+br+c=0$
- Once we factor and solve for the roots $r$, we can solve the equation:
- $y=c_{1}e^{r_{1}t}+c_{2}e^{r_{2}t}$

---

## 3.2 Solutions of Linear Homogenous Equations; the Wronskian

#### Existence and Uniqueness
- Initial value problems **where both $(t_{0},y_0)$ AND $(t_0,y'_0)$ are given** on the interval where $p(t), q(t), r(t)$ are continuous $\rightarrow$ *exactly* one solution $y=\phi(t)$ exists
- This holds true for both homogenous and nonhomogeneous problems

#### Superposition Principle
If $y_1$ and $y_2$ are 2 solutions to a homogenous differential equation then the linear combination $c_{1}y_{1}+c_{2}y_{2}$ is also a solution for any values of $c_1$ and $c_2$
- **Significance** is that given any 2 solutions, we can construct an infinite family of solutions given by:
	- $y(t)=c_{1}y_{1}(t)+c_{2}y_{2}(t)$

#### Wronskian
If $y_1$ and $y_{2}$ are two solutions of the differential equation $y'' + p(t)y'+q(t)y=0$ then the **Wronskian** of the solutions is defined by
$W(t) - W(y_{1,}y_2)=\begin{bmatrix}y_{1}(t), y_{2}(t)\\ y_{1}'(t), y_{2}'(t)\end{bmatrix}=y_{1}(t)y_{2}'(t)-y_{1}(t)'y_{2}(t)$
**The Wronskian helps us find the last solutions of a problem:**
	***If and only if*** there is a point $t_0$ where the Wronskian of $y_1$ and $y_2$ *is not zero*, then $y(t)=c_{1}y_{1}(t)+c_{2}y_{2}(t)$ with arbitrary coefficients $c_1$ and $c_2$ capture *every solution* to the differential equation.
- This is called the **fundamental set of solutions**

### Abel's Theorem
If you do not know the solutions $y_1$ and $y_2$ you can still find the Wronskian by $W(y_{1},y_{2})(t)=C e^{-\int p(t)dt}$

----







End of Exam 1 material!

---

## 3.3
- ### Euler's formula
	- $e^{it}=\cos(t)+i\sin(t)$
	- $e^{-it}=\cos(t)-i\sin(t)$

## 3.6 Variations of Parameters
Given nonhomogeneous second-order linear equation $y'' + p(t)y' + q(t)y = g(t)$
- if $y_1$ and $y_2$ are a fundamental set of solutions then the general solutions to a corresponding homogenous equation is $y_{h}(t)=c_{1}y_{1}(t)+c_{2}y_{2}(t)$
- then we can replace $c_1$ and $c_2$ with functions of $t$ to create a solution of the form $y_p(t)=u_1(t)y_1(t)+u_2(t)y_2(t)$ 

We find that $u_{1}=-\int\frac{y_{2}(t)g(t)}{W(y_1,y_2)(t)}dt,u_{2}=\int\frac{y_{1}(t)g(t)}{W(y_1,y_2)(t)}dt$ 
### Example
**Find the general solution of** $y''+4y=3\csc2t$ for $0<t<\frac{\pi}{2}$
1. $r^{2}+ 4 =0 \rightarrow r=\pm2i$
2. $y_1=\cos(2t), y_2=\sin(2t)$
3. $y_{h}=c_{1}\cos(2t)+c_{2}\sin(2t)$
4. $W=\begin{bmatrix}\cos(2t)& \sin(2t) \\ -2\sin(2t)& 2\cos(2t)\end{bmatrix}=2\cos^{2}(2t)+2\sin^{2}(2t)=C=2$
5. $g(t)=3\csc(2t)$ because the ODE is in *standard form*
6. *Lagrange:* $u_{1}=-\int\frac{3\csc2t\cdot\sin(2t)}{2}dt, u_{2}=\int\frac{3\csc2t\cdot\cos2t}{2}dt$
7. $u_{1}=-\frac{3}{2}t$
8. $u_{2}=\frac{3}{2}\int\frac{\cos2t}{\sin2t}=\frac{3}{4}\ln\sin2t$ 
9. $y=y_h+y_p=c_{1}\cos2t+c_{2}\sin2t-\frac{3}{2}t\cos(2t)+\frac{3}{4}\ln\sin2t\cdot\sin2t$
### Example
Given $t^{2}y'' -t(t+2)y' + t(t+2)y=2t^{3,}t>0$
a. Verify that $y_1=t$ and $y_2=te^t$ are solutions of the corresponding homogenous equation
- $y_{1}'=1, y_{1}'' =0 \rightarrow t^{2}y_{1}''-t(t+2)y_{1}'+(t+2)y_{1}'\eqcirc0$
	- $y_{1}=t$ *is* a solution!

