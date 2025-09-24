A differential equation that describes a physical process in the real world.

- Any **constant** solution to a differential equation is called *equilibrium* or sometimes *steady state*
---

Random note: fraction variables aren't always $\ln$!
$\int\frac{dy}{y^{2}+1} = \arctan(y)+K$

---


**Example**: a drug is being administered via IV. The fluid contains **5 mg/cm^3** and enters the bloodstream at a rate of **100 cm^3 / hr**. The drug is absorbed into the body's tissues at a rate proportional to the amount present w a rate constant of **0.4 / h**.

<u>Find a diferential equation of the amount of drug in the patient's bloodstream.</u>

* So we know we want to solve for $y(t)$ which is unknown.
* We can model this problem like this: [[Math Modeling Example 1]]

Now that we have a differential equation that models this problem, $y' = 5(100) - (0.4 \cdot y)$ , we can find possible solutions.

- First order
- Linear
- Nonhomogenous

Let's find equilibrium:
* $y' = 500 - 0.4y$
* Equilibrium: $0 = 500 - 0.4y$ --> $y = 1250$mg
	* This is at equillibrium because $y'$ (the rate of change of y) will be 0 at this value of y. The output remains constant given that particular input value.
* The significance of this is that once the patient hits 1250mg, he will *always* have 1250mg in the patients tissues. It is an equilibrium state and won't change as long as the input and output also remain constant. 

Let's solve:
*  $y' = 500 - 0.4y$
* Rewrite to $\frac{y'}{500-0.4y}=1$
* Now we can integrate w respect to time (t): $\int{\frac{y'}{500-0.4y}}dt=\int1dt$
* **CALLED SEPERATION OF VARIABLES**
* Solve w u substitution (somehow)
* $du = -0.4dy$
* Therefore $\int\frac{dy}{500 - 0.4y} = \frac{1}{-0.4}\ln|500-0.4y| = t + k$ --> $k$ is any real number
* This is called an "implicit general solution" which relates t and y, but does not yet solve for $y(t)$
* Next $\ln|500-0.4y|=-0.4t -0.4k$
* $|500 -0.4y| = e^{-0.4k -0.4k} = e^{-0.4k} \cdot e^{-0.4t}$
* $500 - 0.4y = (\pm e^{-0.4k})\cdot e^{-0.4t}$
* $0.4y = 500 - (\pm e^{-0.4k})e^{-0.4t}$ --> $y = 1250 - (\frac{\pm e^{-0.4k}}{0.4})e^{-0.4t}$
* Final: $y = 1250 + Ce^{-0.4t}$ because k is just a constant so the whole term becomes a constant $C$
* By inspecting our term $(\frac{\pm e^{-0.4k}}{0.4})$ we find that $C$ can be any real number but *must be **nonzero*** because there is no value of $k$ that makes the term $0$
* So our solutions to the problem show either $y=1250$ or $y=1250 + Ce^{-0.4t}$ where C is nonzero
	* But actually if $C$ is zero it is our equillibrium solution so...
* ***We can just say $y=1250+Ce^{-0.4t}$ where $C$ is any real number*
* Because $C$ can be infinitely many things, there are technically infinitely many solutions to the differential equations
* When plotted, these infinitely many solutions create something called "integral curves"
* The decaying exponential term means that all the curves eventually tend towards 1250.

What if initially the patient has 0mg of drug in their bloodstream. Find the solution to the differential equation.
* This means when $y(0)=0$, or the integral curve passes through the origin
* Take our general solution and set $y=0$ and $t=0$ to represent the solution at the origin, so $0 = 1250 + Ce^{-0.4(0)}$
* We find that $C=-1250$

---

# **Example 2**

*Newton's Law of Cooling states that the temperature of an object changes at a rate proportional to the difference between the temperature of the object itself and the temperature of its surroundings (ambient air temperature).*

1. <u>Find a differential equation for the temperature of the object at any time.</u>
	1. $\frac{dy}{dt}=-k(y-A)=k(A-y)$ where $y$ is the temperature of the object, $A$ is the ambient temperature of the room, and $k$ is some physical constant that we assume to be *positive*.
	2. Note that $y$ varies in time, and that the rate of change, $\frac{dy}{dy}$, depends on the value of $y$ itself.
	3. Note that this equation is:
		- Order = 1
		- ODE
		- Autonomous
		- Linear
		- Nonhomogeous
2. <u>Suppose the ambient temperature = 70F and the rate constant is 0.01 / min, and that the initial temperature of the object is 80F. Find the temperature of the object at any time.</u>
	1. So $A=70\degree F$ , $k=0.01$/min, and $y(0)=80\degree F$
	2. Go from $\frac{dy}{dt} = k(A-y)$ to $y' + ky = kA$
	3. $\begin{cases}y' = 0.01(70-y)\\y(0)=80\end{cases}$
	4. We can see that if $y=70$ then $y'=0$ $\rightarrow$ $y=70=$ equilibrium
	5. Rearrange so that $\int\frac{dy}{70=y}=\int0.01dt$
	6. $\ln|70-y|=0.01t+k$
	7. $y=70+Ce^{-0.01t}$
	8. Since we know that $y(0) = 80$ we can solve that $C=10$
	9. **Final solution: $y(t)=70+10e^{-0.01t}$
	10. 