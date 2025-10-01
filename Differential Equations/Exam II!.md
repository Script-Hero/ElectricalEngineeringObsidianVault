#Diff-EQ 

# EXAM ONLY COVERS UP TO 6.2 AND NO CHAPTA 5!



# Laplussy table is provided on exam!
## 3.3 Euler's formula
Remember $ay'' +by' +cy =0\rightarrow ar^{2}+br+c=0\rightarrow y(t)=c_{1}e^{r_{1}t}+c_{2}e^{r_{2}t}$

Well if they're complex we can do
	- $e^{it}=\cos(t)+i\sin(t)$
	- $e^{-it}=\cos(t)-i\sin(t)$
	- 

If the roots are complex:
- $r_{1}=a_{1}+\beta_{1} i$
- $r_{2}=a_{2}+\beta_{2} i$

So the general solution:
$y(t)=c_{1}e^{at}\cos(\beta t)+c_{2}e^{at}\sin(\beta t)$

####   **Ignore this stuff**
	So we get the solutions like
	- $y_{1}(t)=e^{\alpha +\beta i}t=e^{at}(\cos(\beta t)+i\sin(\beta t))$
	- $y_{2}(t)=e^{\alpha -\beta i}t=e^{at}(\cos(\beta t)-i\sin(\beta t))$
	
	Using superposition:
	$u_{1}=\frac{1}{2}[y_{1}(t)+y_{2}(t)]=e^{at}\cos(\beta t)$
	$u_{2}=\frac{1}{2i}[y_{1}(t)-y_{2}(t)]=e^{at}\sin(\beta t)$
	- $u_{1}$ and $u_{2}$ form the fundamental set of solutions
	




## 3.4 Repeat Roots and Reduction of Order
**Repeated Roots**
If $ay''+by'+cy=0\rightarrow ar^{2}+br +c=0\rightarrow r_{1}=r_{2}$
	- And $r_1$ and $r_2$ are real
	- Then $y(t)=c_{1}e^{r_{1}t}+c_{2}te^{r_{1}t}$ is the general solution to the differential equation

**Reduction of Order**
If we know one solution, $y_{1}(t)$ of $y''+p(t)y' +q(t)y=0$
- We find the solution $y=v(t)y_{1}(t)$
- This gives us the final differential equation $y_{1}v'' + (2y'_{1} +py_{1})v'=0$
	- First we solve for $v'$ then we can solve for $v$ by integrating

## 3.5 Nonhomogeneous Equations, Undetermined Coefficients
$y''+p(t)y'+q(t)y=g(t)$
	- the *corresponding* homogenous equation is $y''+p(t)y'+q(t)y=0$
- if $Y_{1}$ and $Y_2$ are solutions to the *non*homogenous equation then $Y_{1}-Y_{2}$ is a solution to the corresponding *homogenous* equation
- If $y_1$ and $y_2$ are a *fundamental set* of solutions of the *homogenous equation* then $Y_{1}- Y_{2}= c_{1}y_{1}(t)+c_{2}y_{2}(t)$
- and $y'' + p(t)y' +q(t)y =g(t)$ can be written in the form $y(t)=c_{1}y_{1}(t)+c_{2}y_{2}(t)+Y(t)$
	- where $Y$ is some particular solution of the *non*homogenous equation

### **Undetermined Coefficients**
To find the general solution of the nonhomogeneous equation $y'' + p(t)y' +q(t)y=g(t)$:
1. Find the general solution $c_{1}y_{1}(t)+c_{2}y_{2}(t)$ of the *corresponding homogenous equation* -- we call this $y_{h}(t)$
2. Find some solution $Y(t)$ of the nonhomogeneous equation -- called $y_{p}(t)$ -- by making some initial guess about the form of $y_{p}(t)$
3. The general solution is given by $y_{h}(t) + y_{p}(t)$
#### How to choose the $Y_{p}$ form
1. If $g(t)$ is a polynomial in the form $g(t)=a_{0}t^{n}+ a_{1}t^{n-1} + ... + a_{n}$
	- Then $y_{p}(t)=t^{s}(A_{0}t^{n}+ A_{1}t^{n-1}+...+A_{n})$
	- Where $s$ is the number of times $0$ is a [[Electronics/Electronics/Root|Root]] of the characteristic equation
2. If $g(t)=(a_{0}t^{n}+ a_{1}t^{n-1} + ... + a_{n})e^{rt}$
	Then $y_{p}(t)=t^{s}(A_{0}t^{n}+ A_{1}t^{n-1}+...+A_{n})e^{rt}$
	1. If $r$ is *not* a [[Electronics/Electronics/Root|Root]] of the characteristic equation, then $s=0$
	2. If $r$ is a *simple* [[Electronics/Electronics/Root|Root]] of the characteristic equation, then $s=1$
	3. If $r$ is a *double* [[Electronics/Electronics/Root|Root]] of the characteristic equation, then $s=2$
3. If $g(t)=(a_{0}t^{n}+a_{1}t^{n-1}+...+a_{n})e^{at}\sin(\beta t)$ or $g(t)=(a_{0}t^{n}+a_{1}t^{n-1}+...+a_{n})e^{at}\cos(\beta t)$
		Then $y_{p}(t)=t^{s}(A_{0}t^{n}+ A_{1}t^{n-1}+...+A_{n})e^{\alpha t}\sin(\beta t)+t^{s}(B_{0}t^{n}+B_{1}t^{n-1}+...+B_{n})e^{\alpha t}\cos(\beta t)$
		1. If $\alpha \pm \beta i$ are *not* roots of the characteristic equation, then $s=0$
		2. If $\alpha \pm \beta i$ *are* roots then $s=1$
## 3.6 Variations of Parameters / Lagrange Multipliers
Given nonhomogeneous second-order linear equation $y'' + p(t)y' + q(t)y = g(t)$
- if $y_1$ and $y_2$ are a fundamental set of solutions then the general solutions to a corresponding homogenous equation is $y_{h}(t)=c_{1}y_{1}(t)+c_{2}y_{2}(t)$
- then we can replace $c_1$ and $c_2$ with functions of $t$ to create a solution of the form $y_p(t)=u_1(t)y_1(t)+u_2(t)y_2(t)$ 

We find that $u_{1}=-\int\frac{y_{2}(t)g(t)}{W(y_1,y_2)(t)}dt,u_{2}=\int\frac{y_{1}(t)g(t)}{W(y_1,y_2)(t)}dt$ 

- Particular Solution becomes $y_{p}=-y_{1}(t)\int \frac{y_{2}(t)g(t)}{W(y_{1},y_{2})(t)}dt + y_{2}(t)\int\frac{y_{1}(t)g(t)}{W(y_{1}, y_{2})(t)}dt$
- General Solution becomes $y(t)=c_{1}y_{1}(t)+c_{2}y_{2}(t)+y_{p}(t)$


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


## 6.1 Da Laplussy Transform!
- *Exponential order* is when $|f(t)| < Ke^{at}$ for $t\geq M$
- ***Laplace Transform*** is $\mathcal{L}\{f(t)\}=F(s)=\int_{0}^{\infty}e^{-at}f(t)dt$
	- assuming the integral converges
- Any piecewise function continuous on $[0,A]$ and in *exponential order* $|f(t)| \leq Ke^{at}$ for $t\geq M$ then the ***Laplace Transform*** exists for $s>a$
- We can break up ***Laplace Transforms*** like $\mathcal{L}\{c_{1}f_{1}(t)+c_{2}f_{2}(t)\}=c_{1}\mathcal{L}\{f_{1}(t)\}+c_{2}\mathcal{L}\{f_{2}(t)\}$

## 6.2 Solutions of Initial Value Problems (IVP)
- *Lifting property of Laplussy transforms* $\mathcal{L}\{f'(t)\}=s\mathcal{L}\{f(t)\}-f(0)$
	- $\mathcal{L}\{ f''(t) \}=s^{2}\mathcal{L}\{f(t)\}-sf(0)-f'(0)$
	- We can keep continuing this, this is the rectangle thing
- Inverse Laplussies exist
	- They follow the breaking up rule from **6.1**
- Sometimes partial fraction decomp is lit for this


# END EXAM CONTENT!
---



## 6.3 Heaviside Function (step function)
*We **continued** learning this on 11.7.23*
- **Unit Step Function / Heaviside** is $u_{c}(t)\begin{cases}0,t<c\\1,t\geq c\end{cases}$
- $\mathcal{L}\{u_{c}(t)f(t-c)\}=e^{-cs}F(s)$ for $s>a$
	- and $u_{c}(t)f(t-c)=\mathcal{L}^{-1}\{e^{-cs}F(s)\}$
	  
- *Shifting frequency:* $\mathcal{L}\{e^{ct}\}=F(s-c)$ for $s>a+c$
	- and $e^{ct}f(t)=\mathcal{L}^{-1}\{F(s-c)\}$
	- this is not related to **Heaviside functions*** lol

1. **Forward** $\mathcal{L\{u_{c}(t)g(t)}\}=e^{-cs}\mathcal{L}\{g(t+c)\}$
2. **Backward** $\mathcal{L^{-1}}\{e^{-cs}F(s)\}=u_{c}(t)f(t-c)$

***Example:** Find transform of* $f(t)=\begin{cases}0,t<1\\ t^{2}-2t +2, t\geq1\end{cases}$
- *Note that we use $u_{2}(t)$ because $g(t)$ starts at 2*
1. $f(t)\rightarrow e^{-3}(\frac{2}{s^{3}}+\frac{1}{s^2})$
2. $g(t)=\begin{cases}3t,t<2\\ t^{2}-2t + 2, t\geq 2\end{cases}$
3. $g(t)=3t+[(t^{2}-2t + 2)-3t]u_{2}(t)$
4. $G(s)=3\cdot \frac{1}{s^2}+e^{-2s}\mathcal{L}\{(t+2)^{2}-5(t+2) +2\}$
5. $G(s)=\frac{3}{s^{2}}+e^{-2s}(\frac{2}{s^3}-\frac{1}{s^2}-\frac{4}{3})$

**Note: for delay and shift functions, *do not* set up partial fraction decom**

***Example** find the transform of* $F(s)=\frac{e^{-2s}}{s^{2}+ s -2}$
1. Fraction decomp so $\frac{1}{s^{2}+s -2}=\frac{1}{(s+2)(s-1)}=\frac{A}{s+2}+\frac{B}{s-1}$
2. We find $\frac{-1}{3}e^{-2t}+\frac{1}{3}e^t$
3. We find delay $c=2$
4. $u_{2}(t)[-\frac{1}{3}e^{2(t-2)}+\frac{1}{3}e^{t-2}]$

***Example** find the inverse transform of* $F(s)=\frac{1}{s^{2}-6s+13}$
- We can't factor! :(
- Fuck it, complete da square so we got $F(s)=\frac{1}{(s-3)^{2}+4}$
	- Kachow we shifted the frequency *(s-shift)*
- Laplussy it $\mathcal{L}^{-1}\{\frac{3s+17}{(s-3)^{2}+4}\}$
	- now I wanna see the shift everywhere so we're just gonna replace $s$ with $s-3$ everywhere. Fuck it.
- So we get $\mathcal{L}^{-1}\{\frac{3(s-3)+26}{(s-3)^{2}+4}\}$
	- $17\rightarrow26$ because the $3s\rightarrow3(s-3)$ means we have to balance out the extra $-9$ we magically threw in there
- Now we can cancel numerator and denominator to get $\mathcal{L}^{-1}\{\frac{3s+26}{s^{2}+4}\}$
- We get $f(t)=3\cos(2t)+\frac{26}{2}\sin(2t)$

***Example** find $\mathcal{L}^{-1}\{\frac{(3s+17)e^{-5s}}{(s-3)^{2}+4}\}$
- It's obviously a time-delay function
- unshift via $s\rightarrow s+3$
- We get $\frac{3s+26}{s^{2}+4}$
- Inverse Laplussy we get $3\cos(2t)+13\sin(2t)$
- Don't forget multiplying by $e^{-5s}$ from our original problem!
- $e^{3t}[3\cos(2t)+13\sin(2t)]$ but there's a delay of 5 so 
	- **Final answer!** $u_{5}(t)\cdot e^{3t-5}[3\cos(2(t-5))+13\sin(2(t-5))]$


## 6.4 DiffEQS with Discontinuous Forcing Functions
- Functions in the form $ay'' +by'+cy=g(t)$
	- where $g(t)$ is *discontinuous*
- The notes don't say how to solve it lol

## 6.5 Impulse Function 
- Consider $ay'' + by' + cy=g(t)$ where $g(t)$ is high for is large only for a very short interval and is 0 otherwise
	- Think like pulses of [[Voltage]]
- **Dirac Delta Function** $\delta(t)=\begin{cases}0, t\neq0\end{cases}$
	- Think like a ***delay function***
	- $\int_{-\infty}^{\infty}\delta(t)dt=1$
	- $\mathcal{L\{\delta(t-t_{0})\}}=e^{-st_{0}}$
	- and if some $f(t)$ is continuous on $[0,\infty)$, then $\mathcal{L\{\delta(t-t_{0})f(t)\}}=e^{-st_{0}}f(t_{0})$


## 6.6 Convolution Integral
- Can make Laplace Transforms out of 2 other functions
	- Like $H(s)=F(s)G(s)$ when $F(s)$ and $G(s)$ are transforms of known functions $f$ and $g$.
- We can find $H(s)$ like $h(t)=(f*g)(t)=\int^{t}_{0}f(t-\tau)g(\tau)d\tau$
	- $H(s)=\mathcal{L}\{h(t)\}$
- OR $\mathcal{L}\{f*g\}=\mathcal{L\{f\}}\cdot\mathcal{L\{g\}}$
- **Convolutional Properties:**
	- *Communitive Law* $f*g=g*f$
	- *Distributive Law* $f*(g+h)=(f*g)+(f*h)$
	- *Associative Law* $(f*g)*h=f*(g*h)$
	- $f*0=0$

