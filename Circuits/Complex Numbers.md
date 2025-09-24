Numbers formed of a combination of an *imaginary component* and a *real component*. Example:
$$z=2+4j$$
- $\Re[z]=2$
- $\Im[z]=4$

In *Cartesian* (rectangular form) we define the y-axis for the imaginary part and the x-axis for the real part, and can plot an imaginary number in 2d space.
![[cartesian_imaginary.png]]

In *Polar* form, we write a complex number in terms of its magnitude $r$ and phase $\theta$, stemming from Euler's Identity:
$$re^{j\theta}=r\cos(\theta)+jr\sin(\theta)$$
We can convert between *Cartesian* and *Polar* by:
$$x=\Re[re^{j\theta}]=r\cos(\theta)$$
$$
y=\Im[re^{j\theta}]=r\sin(\theta)
$$

The notation $r\angle\theta$ instead of $re^{j\theta}$ is also valid.

Note that it follows that:
- $r=\sqrt{x^2+y^2}$
- $\theta=\tan^{-1}(\frac{y}{x})$

## Conjugation
The conjugate of $z$, $z^*$ (or $\bar z$) is changing all the $j$s to $-j$s:
- $z=x+jy\rightarrow z^*=x-jy$
- $z=re^{j\theta}\rightarrow z^*=re^{-j\theta}$
- $(z^*)^*=z$
- If $f(z)$ is a polynomial function of $z$ with real coefficients, then $f(z)=0\leftrightarrow f(z^*)=0$
	- Roots of real polynomials occur in complex conjugate pairs

## Arithmetic
### For **adding** and **subtracting** use *Cartesian* form:
- $z_1+z_2=(x_1+jy_1)+(x_2+jy_2)=(x_1+x_2)+j(y_1+y_2)$
- $z_1-z_2=(x_1+jy_1)-(x_2+jy_2)=(x_1-x_2)+j(y_1-y_2)$
#### Implies:
- $\Re[z_1\pm z_2]=\Re[z_1]\pm\Re[z_2]$
- $\Im[z_1\pm z_2]=\Im[z_1]\pm\Im[z_2]$


### For **multiplying** and **dividing** use *Polar* form:
- $z_1z_2=(r_1e^{j\theta_1})(r_2e^{j\theta_2})=r_1r_2e^{j(\theta_1+\theta_2)}$
- $\frac {z_1}{z_2}=\frac{r_1e^{j\theta_1}}{r_2e^{j\theta_2}}=\frac{r_1}{r_2}e^{j(\theta_1-\theta_2)}$ 

#### Implies:
- $|z_1z_2|=|z_1||z_2|$
- $\angle(z_1z_2)=\angle z_1 + \angle z_2$
- $|\frac {z_1} {z_2}|=\frac{|z_1|}{|z_2|}$
- $\angle(\frac{z_1}{z_2})=\angle z_1-\angle z_2$

## Exponentials and Logs
### For **exponentials** use *Cartesian* form:
$$e^z=e^{x+jy}=e^xe^{jy}=e^x\cos(y)+je^x\sin(y)$$

### For **logarithms** use *Polar* form:
$$\ln(z)=\ln(re^{j\theta})=\ln(r)+\ln(e^{j\theta})=\ln(r)+j\theta$$
### Multi-Valued Functions
When a function $f(z)=\ln(z)$ this is called a *multi-valued function*. For example, if we wanted to find $\ln(-5)$, since $-5$ can be written as $-5=e^{j\pi}$ such that $\ln(-5)=\ln(5e^{j\pi})=\ln(5)+j\pi$

## Important relationships
1. $e^{j\theta}=\cos(\theta)+j\sin(\theta)$
2. $e^{-j\theta}=\cos(\theta)-j\sin(\theta)$
3. $\cos(\theta)=\Re[e^{j\theta}]$
4. $\sin(\theta)=\Im[e^{j\theta}]$
5. Adding 1 and 2: $\cos(\theta)=\frac{e^{j\theta}+e^{-j\theta}} 2$
6. Subtracting 1 and 2: $\sin(\theta)=\frac{e^{j\theta}-e^{-j\theta}}{2j}$
7. $\cos^2(\theta)+\sin^2(\theta)=1$
