<u>Has the form:</u> $\frac{dy}{dt}=f(t,y)$

If $f$ is a *linear* function *of $y$* then the equation is a *linear first order* equation.

---
**Ex**
Solve $(4+t^2)\frac{dy}{dt}+2ty=4t$
- Linear
- Not separable :(
- Can't solve w simple integration :(

***We solve the problem by matching the coefficients to the general form***

General form: $A(t)y' + B(t)y = C(t)$
$\frac{d}{dt}[???]=A(t)y'$ --> $\frac{d}{dt}[A(t)y]=A(t)y' + A'(t)y$    (product rule)
This shows us that $B(t)=A'(t)$ shawty

$\frac{d}{dt}[(4+t)^{2}y]=4t$
$\int4tdt+C = (4+t^{2})y$
So $y=\frac{2t^{2}+C}{4+t^{2}}$ --> general implicit solution

---
### Forcing the equation into "standard linear form"
$y' + \frac{3t}{4+t^{2}}y=\frac{4t}{4+t^{2}}$

**Let's find an integrating factor $\mu(t)$**

// **just kidding ignore this**  Multiply by $(4+t^{2}) --> (4+t^{2})y' + 3ty = 4t$

$\mu[y' + py]=\mu g$
$\mu y' + (\mu p)y = (\mu g)$

**Exact solution: $\mu p = \mu'$**
- $p = 2 \rightarrow \mu = e^{2t}$
- $p=t \rightarrow \mu' = t\mu$
- $\frac{\mu'}{\mu}=p\rightarrow\ln\mu=\int p\rightarrow \mu=e^{\int p}$


