#Phys-EM 

**Magnetic Fields come from moving electric charges!**
- Moving electric charges experience magnetic force
- Newton's Third Law says forces exert equal and opposite force
- Therefore moving charges ([[Current]]) causes magnetic field

**Strength of Magnetic Field** $B=\frac{\mu_{0}}{2\pi}\frac{i}{r}$
- $\mu_{0}$ is $\epsilon_{0}$ for magnetism
- $d\vec{B}=\frac{\mu_{0}i}{4\pi}\frac{d\vec{l}\times\vec{r}}{r^{3}}$
	- $B=\frac{\mu_{0}i}{4\pi}\int_{wire}\frac{d\vec{l}\times \vec{r}}{r^{3}}$
- Exam could have us find straight wires or circles

**Direction of magnetic field**
- Use the right hand rule 


### Example: 
**Find the magnetic field from a thin loop of [[Current]] at an arbitrary distance along the loop's axis of symmetry.**

```
        /----\
        |    |
< - - - |  - - - - - - - - - - - > z 
        |    |                                         \____/
```

$\vec{B}=\frac{\mu_{0}i}{4\pi}\int_{wire}\frac{d\vec{s}\times\vec{r}}{r^{3}}$
$r=\sqrt{R^{2}+L^2}$ (imagine a right triangle where $L$ is your position on the z axis and $R$ is the radius of the loop of wire)
- Break this into components with $\vec{r}=R\cos\phi\hat{i}_{x}+R\sin\phi\hat{i}_{y}+L\hat{i_z}$

$d\vec{s}=-ds\sin\phi\hat{i_{x}}+ds\cos\phi\hat{i_y}$

$|d\vec{s}\times\vec{r}|=rds$
$|d\vec{s}\times\vec{r}|_{z}=rds\sin\theta=Rds$

$\vec{B}=\frac{\mu_{0}i}{4\pi} \int_{wire} \frac{Rds\hat_{z}} {(R^{2}+L^{2})^{\frac{3}{2}}}$    

