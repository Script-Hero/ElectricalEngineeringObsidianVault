#Cal-3 

## 15.1 Double Integrals
- **Partial Integration** is like partial derivation, we integrate while holding one variable as a constant
- So we can do $\int(x^{2}+y^{3})dx$ and also $\int(x^{2}+y^{3})dy$ as partial single integrals
- $\int\int((x^{2}+y^{3})dx)dy$ is called a *iterated integral*
- **Fubini's Theorem**
	- if $f$ is continuous on rectangle $[a,b]\times[c,d]$ then $\int\int_{R}f(x,y)dA=\int^{b}_{a}\int^{d}_{c}f(x,y)dydx=\int^{d}_{c}\int^{b}_{a}f(x,y)dxdy$
	- ***Sexy* Special case** $\int^{b}_{a}\int^{d}_{c}g(x)h(y)dydx=\int^{b}_{a}g(x)dx+\int^{d}_{c}h(y)dy$
	- 