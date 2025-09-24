### $\int \int \int_{E}y^{2}dV$ bounded by paraboloid $x=2y^{2}+2z^{2}$ and the plane $x=2$.
- $0 \le x \le 2$
- When $x=k$, $2y^{2}+2z^2=k$
	- This is a circle with radius $\sqrt{\frac{k}{2}}$
- $(k,y,z)\in E \therefore y^{2}+z^{2} \le \frac{k}{2}$
	- $y= r\cos\theta$ where $0\le r \le \sqrt{\frac{k}{2}}$ 
	- $z = r\sin\theta$ where $0\le\theta\le2\pi$
- Therefore $dydz=rdrd\theta$
- Finally we evaluate the integral
	- $\int\int\int_{E}y^{2}dV=\int^{2}_{0}\int^{2\pi}_{0}\int_{0}^{\sqrt{\frac{x}{2}}}r^{2}\cos^2\theta\cdot(rdrd\theta)dx$
	- Use *Fubini* to separate into $\int^{2}_{0}(\int_0^{2\pi}\cos^{2}\theta d\theta)(\int_0^{\sqrt{\frac{x}{2}}}r^{3}dr)dx=\frac{\pi}{6}$


### Rewrite the integral $\int_{0}^{1}\int^{1}_{\sqrt{x}}\int_{0}^{1-y}f(x,y,z)dzdydx$ in the 5 different orders
1. $dydzdx:$ $0\le x\le1$, the curve is an intersection of $y=\sqrt{x}$ and $z=1-y$ which also equates to $z=1-\sqrt{x}$ and $x=(1-z)^2$. So we say $0\le z\le1-\sqrt{x}$ (curve) and $\sqrt{x}\le y \le 1-z$ (plane).
2. $dxdzdy:$ $0\le y\le1, 0\le z \le 1-y, 0 \le x\le y^2$.
3. $dxdydz:0\le z\le1, 0\le y \le 1-z, 0 \le x \le y^2$
4. 