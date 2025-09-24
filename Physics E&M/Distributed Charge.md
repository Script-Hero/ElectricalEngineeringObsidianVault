#Phys-EM 
- Uses [[Coulomb's Law]] 
- Take an infinitesimally small point of the shape and calculate Coulomb's law on it to find charge, then integrate this to take the sum of all the infinitesimally small points which gives the total charge of the shape
- For a 3D shape like a thick cylindrical rod, you use cylindrical shells as your infinitesimal points

### For the exam, know how to solve line distributed charge problems and circular distributed charge problems

Solve with modified Coulomb's law that replaces a constant charge with an integral.

## Example:
A thin ring of radius $R$ has a charge $Q$ uniformly distributed. A charge $q$ is at a distance of $L$ from the center of the ring along its axis of symmetry.
- Find the force on the charge q
$\delta \vec{F} = \frac{1}{4\pi\epsilon_{0}}\frac{q * dq}{r^2}\hat{r}$ and $\delta q = \lambda \delta l$ so $\vec{F}=\frac{q}{4\pi\epsilon_0}\int\frac{\lambda}{r^2}dl$
$\lambda = \frac{Q}{2\pi R}$, $l=s=R\Delta\theta$, $dl = d =Rd\theta$
* note that $dl$ is just an infinitesimal segment of the circle, which works out to be an *arc length*

$\vec{r} = L\hat{i_{x}} + (-Rcos\phi)\hat{i_y} + (-Rsin\phi)\hat{i_z}$
$r^{2}= l^{2} + R^{2}cos^{2}\phi+ R^{2}sin^{2}\phi=l^{2} +r^2$

Final force equation:
$\vec{F}= \frac{q}{4\pi\epsilon_0}\int^{2\pi}_{\pi}\frac{Q}{2\pi R}\frac{L\hat{i_{x}} + (-Rcos\phi)\hat{i_y} + (-Rsin\phi)\hat{i_z}}{(L^{2}+R^{2})^{\frac{3}{2}}}rd\theta = F_{x}\hat{i_x}+F_{y}\hat{i_y}+F_{z}\hat{i_z}$

We find that $F_y$ and $F_z$ both end up being $0$.

Finally,
$\vec{F}=\frac{qQ}{4\pi\epsilon_0}\frac{L}{((r^{2}+R^{2}))^\frac{3}{2}}\hat{i_x}$
