#Cal-3 

**(15.1-15.3,15.6-15.9)**

## 15.1 - Double integrals over rectangles
- we can do iterated integrals
- partial integrals are also a things
- *Fubini's Theorem* $\int_{a}^{b} \int_{c}^{d} f(x,y)dydx=\int_{c}^{d}\int_{a}^{b} f(x,y)dxdy$
	- Special case of *Fubini* is $\int_{a}^{b} \int_{c}^{d} f(x)h(y)dydx=\int_{a}^{b}  f(x)dx\int_{c}^{d}h(y)dy$

## 15.2 - Type 1 and Type 2 Integrals

- Type 1 is between 2 continuous functions of $x$
	- $\int_{a}^{b}\int^{g_{2}(x)}_{g_{1}(x)}f(x,y)dydx$
- Type 2 is between 2 continuous functions of $y$
	- $\int_{a}^{b}\int_{h_{1}(y)}^{h_{2}(y)}f(x,y)dxdy$

## 15.3 POLAR COORDINATES BITCH

- $x=r\cos(\theta); y=r\sin(\theta)$
- $\tan(\theta)=\frac{y}{x}$
- $x^{2}+y^{2}=r^{2}$
We can convert basic ass hoes (*double integrals*) into preppy bitches (*polar coordinate double integrals*) using $\int\int_{R}f(x,y)dA=\int_{\alpha}^{\beta}\int^{b}_{a}f(r\cos\theta,r\sin\theta)rdrd\theta$
- **DON'T FORGET DAT EXTRA $r$ JAKOBIAN ASS BITCH

- like half of it boils down to $\int_{0}^{4}\int_{-\sqrt{16-y^2}}^\sqrt{16-y^2}(x+y)dxdy$ well $x=\sqrt{16-y^{2}}\rightarrow x^{2}=16-y^{2}\rightarrow x^2+y^2=4^2$ holy shit it's a circle with $r=4$ and holy shit the $x$ goes from $-r \rightarrow r$ so $\theta$ is $[0,\pi]$ holy shit holy shit holy fuck

## 15.6 OH BABY A TRIPLE (INTEGRAL)

## 15.7 IT'S CYLINDER (COORDINATES) ALL THE WAY DOWN
Points are represented by $(r,\theta,z)$
**To convert *from* cylindrical:**
- $x=r\cos\theta$
- $y=r\sin\theta$
- $z=z$

**To convert *to* cylindrical:**
- $x^{2}+ y^{2}=r^{2}$
- $\tan\theta=\frac{y}{x}$
- $z=z$

And the [[Triple Integral]] is $\int_{\theta=\alpha}^{\theta=\beta}\int_{r=h_{1}(\theta)}^{r=h_{2}(\theta)}\int_{z=u_{1}(r\cos\theta,r\sin\theta)}^{z=u_{2}(r\cos\theta,r\sin\theta)}f(r\cos\theta,r\sin\theta,z)dzdrd\theta$

## 15.8 Sphere Time!
Points represented by $(\rho,\theta,\phi)$
- $\rho=|OP|$ is the distance from the origin to $P$, the point
- $\theta$ is the same as cylindrical coordinates
- $\phi$ is the angle between the *positive* $z$ axis and the line segment $OP$

**To convert:**
- $\rho=\sqrt{x^{2}+y^{2}+z^{2}}$
- $z = \rho\cos\phi$
- $r=\rho\sin\phi$
- $x=\rho\sin\phi\cos\theta$
- $y=\rho\sin\phi\sin\theta$
- $\tan\theta=\frac{y}{x}$

**Spherical coordinate triple integrals:** $\int\int\int f(\rho,\theta,\phi)\cdot \rho^{2}\sin\phi d\rho d\phi \theta$
- *[[Jacobian]]* is $\rho^{2}\sin\phi$

## 15.9 Change of Variables
- We gotta **[[Jacobian]]** on that hoe

If we wanna do a switcheroo so that $x=g(u,v)$ and $y=h(u,v)$:
**[[Jacobian]]** = $\begin{bmatrix}\frac{\delta x}{\delta u}&\frac{\delta x}{\delta v}\\\frac{\delta y}{\delta u}&\frac{\delta y}{\delta v}\end{bmatrix}=\frac{\delta x}{\delta u}\frac{\delta y}{\delta v}-\frac{\delta x}{\delta v}\frac{\delta y}{\delta u}=J$

Let's us transform $\int \int f(x,y)dA=\int \int f(x(u,v),y(u,v))|J|dA$


