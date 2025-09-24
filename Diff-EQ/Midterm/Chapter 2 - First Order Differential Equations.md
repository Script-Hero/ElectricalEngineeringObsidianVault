---
~
---

# ***ALWAYS CONVERT TO STANDARD FORM WITH $y'$ or $y''$ WITH NO COEFFECIENT OR YOU'RE FUCKEDDDDDDDDD

## 2.1 Linear First Order Differential Equations

**General Form of Linear First Order Differential Equation:** $\frac{dy}{dx} + P(x)y=Q(x)$

- Sometimes we can solve these equations by integrating right away.
- Other times, we need to use $\mu(t)$, the **integrating factor**

### Integrating factor

If we multiply both sides of our differential equation by $\mu(t)$, which is unknown, and then solve for $\mu(t)$ we can easily integrate the problem.
- $\mu(t)=e^{\int p(t)dt}$



---

## 2.2 Separable Differential Equations
**Separable Equations** are the form $M(x)dx + N(y)dy=0$
- We can typically solve using $\int M(x)dx=\int N(y)dy$


---

## 2.3 Modeling with First-Order Differential Equations
Boils down to $Amount_{In}-Amout_{Out}=\frac{dy}{dt}$


---

## 2.4 Differences Between Linear and Nonlinear Differential Equations

### **Existence and Uniqueness Theorem** 
**Linear Equation**
If in $y' + p(t)y=g(t)$ both $p(t)$ and $g(t)$ are continuous on an interval containing the given initial value $t=t_0$ then there exists a unique solution $y=\phi(t)$.

**Nonlinear Equation**
If the functions $f$ and $\frac{\delta f}{\delta y}$ are continuous on the $(t,y)$ rectangle containing the point of the initial value $(t_{0}, y_{0})$ then there exists a *unique* solution $y=\phi(t)$ of the initial value problem.
*Note* that we can also establish that a solution exists using ***only*** $f$, but not its uniqueness. 



---

## 2.5 Autonomous Equations (and Population Dynamics)
**Autonomous Equations** are in the form $\frac{dy}{dt}=f(t)$
	*Note* that they depend on only 1 variable

**Equilibrium Solutions** are solutions where $\frac{dy}{dt}=0$
	This means there is no change when $t$ is at the equilibrium point
	 **Asymptotically Stable** has nearby solutions that approach the equilibrium point
	 **Asymptotically Unstable** if nearby solutions go away from the equilibrium point
	 **Semistable Equilibrium** if one side points towards equilibrium and one side points away from it 
- Classify the equilibrium point by looking at $\frac{dy}{dt}$ before and after each equilibrium

**Exponential Growth**
$\frac{dN}{dt}=rN$ where $N(t)$ is the population size at $t$ where $r>0$ is the *intrinsic growth rate*.

**Logistic Growth**
$\frac{dN}{dt}=rN(1-\frac{N}{K})$ where $r$ and $K$ are positive constants

---

## 2.6 Exact Equations and Integrating Factors 
Given a first order differential equation $M(x,y)+N(x,y)y'=0$

The equation is **exact** if there exists $\psi_{x}(x,y)=M(x,y)$ and $\psi_{y}(x,y)=N(x,y)$ and $\psi(x,y)=C$

We can prove the equation to be **exact** by evaluating if $M_{y}(x,y)=N_{x}(x,y)$ where $M_{y}(x,y)$ is $\frac{d}{dy}M$.

### To solve an exact equation:
- Pick one of the two partial derivatives.
	- We'll choose $M(x,y)$ which is attached to $dx$
	- We $(\int M(x,y) dx)+g(y)$ so that $M_{y}(x,y) + g'(y)=N_{x}(x,y) + g'(y)$
	- 

### **If an equation is not exact, we can multiply it by an *integrating factor* $\mu(x,y)$ to make it exact.**

- If $\frac{M_{y}-N_{x}}{N}$ is a function of $x$ only, then:
	- $\mu(x)=e^{\int\frac{M_{y}-N_{x}}{N}dx}$
- Elif $\frac{N_{x}-M_{y}}{M}$ is a function of $y$ only, then:
	- $\mu(y)=e^{\int \frac{ N_{x}-M_{y} }{M}dy}$

---
