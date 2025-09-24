#Phys-EM 

- Electric charges exert forces on one another at a distance
- Imagine that a charge impacts the space around it by generating an "electric field"
- We can measure an electric field by examing its effect on a small "test" charge:
	- $\vec{E}(\vec{r})=\lim_{q_0\to0}\frac{\vec{F}(\vec{r})}{q_0}$
	- When we put a test charge into our system we *do not* want our test charge to introduce a significant electric field of its own.
	- Imagine how we can test Earth's gravitational field by dropping a "test rock" and seeing how it falls. Technically our test rock has its own gravitational field but its not much.

Coulomb Field from charge $q$
$\vec{E}(\vec{r})=\frac{1}{4\pi\epsilon_0}\frac{q}{r^2}\hat{r}$
- Extremely similar to [[Coulomb's Law]]
- Just like the force, the field points radially away (right hand rule) in the $\hat{r}$ direction
- falls off as $\frac{1}{r^2}$
- is proportional to the charge $q$
- Negative fields act as "sinks", positive fields act as "repellents"

---

We can use superposition and [[Distributed Charge]] on fields exactly the same. 

If we have multiple points, we can add each electric field from each point together

---

**Example:**
- 2 point charges, one w a charge of $-q$ and another with a charge of $+2q$ and are separated by a distance of $L$
- Find the electric field at the center of these charges

$\vec{E}=\frac{q}{4\pi\epsilon_0}\frac{1}{r^2}\hat{r}$
Apply formula to each charge: 

- $\vec{E_{-q}}=\frac{|-q|}{4\pi\epsilon_0}\frac{4}{L^2}\hat{i_x}$
- $\vec{E_{+2q}}=\frac{+2q}{4\pi\epsilon_0}\frac{4}{L^2}\hat{i_x}$
Total combined $\vec{E}=\frac{3q}{\pi\epsilon_{0}L^{2}}$
- Found by adding $\vec{E_{-q}}$ and $\vec{E_{+2q}}$

---

**Example:**
Find the electric field from an infinitely long, thin wire w uniform charge density $\lambda$
$dE = \frac{d_q}{4\pi\epsilon_{0}}\frac{1}{r^{2}\hat{r}}\Rightarrow \vec{E}=\frac{1}{4\pi\epsilon_{0}}\int\frac{\lambda}{r^2}\hat{r}dl$

$\vec{E}=\frac{1}{4\pi\epsilon_0}\int^{\infty}_{-\infty}\lambda\frac{-x\hat{i_{x}}+ d\hat{i_r}}{(x^{2}+d^{2})^{\frac{3}{2}}}$

We find that the x component is 0 so $\vec{E}=\frac{\lambda}{4\pi\epsilon_0}\int^{\infty}_{-\infty} \frac{d \partial x \hat{i_{x}} {(x^{2}+ d^2)^{\frac{3}{2}}}}$ 