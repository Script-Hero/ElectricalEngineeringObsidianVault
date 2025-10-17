# Constants
- $\epsilon_0=8.854\cdot10^{-12}\text{ Farads per Meter}$
- $\mu_0=1.257\cdot10^{-6}\text{ Newtons per Ampere}^2$

# Formulas
**Infinite Line Charge**
- $E=\frac{|\lambda|}{2\pi\epsilon_0\rho}\hat{\rho}$
	- $\lambda$ is the linear charge density $\frac{dq}{dl}$
	- $\rho$ is the shortest distance from the point we're measuring from and the line ($\rho=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2}$)
	- $\hat \rho$ is the *unit vector* that is **from the line charge to the point of observation**
**Point Charge**
- $E=\frac{1}{4\pi\epsilon_0}\frac{Q(\vec{r_p}-\vec{r_s})}{|\vec{r_p}-\vec{r_s}|^3}$
	- Where $r_p$ is the point of interest and $r_s$ is the source charge
	- $Q$ is the charge of the *source* (not point of interest)
**Infinite Sheet Charge**
 - $E=\frac{\sigma}{2\epsilon_0}$
	 - direction is away from the sheet on both sides

# Integrals
**Cylindrical**
- $\int\int\int f(r,\theta,z) r drd\theta dz$
**Spherical**
- $\int\int\int f(\rho,\phi\theta)\rho^2\sin(\phi) d\rho d\phi d\theta$

# Misc
![[maxwells.png]]
![[fieldsfromcharges.png]]
![[symmetry.png]]
![[flux_and_gauss.png]]
![[Pasted image 20251017172557.png]]
![[Pasted image 20251017172622.png]]
# Tables
![[tabl1.png]]
![[table2.png]]
![[table3.png]]


# Triple Integrals
Spherical:
$$\int\int\int\rho d\rho$$

# Gradients
Spherical:
$$\nabla f=\frac{\delta f}{\delta r}e_r+\frac 1 r \frac{\delta f}{\delta\theta}e_\theta+\frac{1}{r\sin\theta}\frac{\delta f}{\delta \phi}e_\phi$$
Cylindrical:
$$\nabla f=\frac{\delta f}{\delta \rho}e_\rho+\frac 1 \rho\frac{\delta f}{\delta\phi}e_\phi+\frac{\delta f}{\delta z}e_z$$

# Divergence
Cylinder:
$$\nabla\cdot V=\frac{1}{\rho}\frac \delta {\delta\rho}(\rho V_\rho)+\frac 1 \rho\frac{V_\phi}{\delta \phi}+\frac{\delta V_z}{\delta z}$$
Sphere:
$$\nabla\cdot V=\frac{1}{r^2}\frac \delta {\delta r}(r^2 V_r)+\frac 1 {r\sin\theta}\frac{\delta}{\delta\theta}(\sin\theta V_\theta)+\frac{1}{r\sin\theta}\frac{\delta V_\phi}{\delta\phi}$$


# Curl
Cylinder:
1. $$(\nabla\times V)_\rho=\frac 1 \rho(\frac{\delta V_z}{\delta\phi}-\frac{\delta(\rho V_\phi)}{\delta z})$$
2. $$(\nabla\times V)_\phi=\frac{\delta V_\rho}{\delta z}-\frac{\delta V_z}{\delta \rho}$$
3. $$(\nabla\times V)_z=\frac{1}{\rho}(\frac{\delta(\rho V_\phi)}{\delta\rho}-\frac{\delta V_\rho}{\delta\phi})$$
Spherical:
4. $$(\nabla\times V)_r=\frac{1}{r\sin\theta}\left[\frac{\partial}{\partial\theta}(\sin\theta\,V_\phi)-\frac{\partial V_\theta}{\partial\phi}\right]$$
5. $$(\nabla\times V)_\theta=\frac{1}{r}\left[\frac{1}{\sin\theta}\frac{\partial V_r}{\partial\phi}-\frac{\partial}{\partial r}(rV_\phi)\right]$$
6. $$(\nabla\times V)_\phi=\frac{1}{r}\left[\frac{\partial}{\partial r}(rV_\theta)-\frac{\partial V_r}{\partial\theta}\right]$$
# dS Tutorial
![[Pasted image 20251017172751.png]]![[Pasted image 20251017172814.png]]

