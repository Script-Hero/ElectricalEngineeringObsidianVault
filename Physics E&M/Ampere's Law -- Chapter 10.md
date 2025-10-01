#Phys-EM 

$\oint \vec{B} \cdot d\vec{r} = \mu_{0}i_{enc}$
The magnetic field across the boundary of an area is the [[Current]] through that area times $\mu_{0}$

**We use this a lot like Gauss' Law!**

### Solenoids!
A solenoid is made by looping a wire into a coil characterized by length $L$, number of turn $N$, and loop area $A$.

**Like a *magnetic capacitor***

- Magnetic field is uniform inside (adds together)
	- $\vec{B}$ dies off quickly away from coil's outside

We use rectangular Amperean loops for solenoid problems. 
- $\oint B dr=\mu_{0}i_{enc}$
- Then we create the 4 "legs" of the rectangle and seperate our integral
- Create $\int_{1}\vec{B}d\vec{r}+\int_{2}\vec{B}d\vec{r}+\int_{3}\vec{B}d\vec{r}+\int_{4}\vec{B}d\vec{r}$
- However 1,2, and 3 cancel to 0 
- So $\int_{4}Bdr=Bl=\mu_{0}(\frac{N}{L})li$
- **Finally $B=\mu_{0}i\frac{n}{L}$**

### Toroidal solenoid
We can take a wrap loop of wire around a torus (donut shape)
- Completely contains magnetic field
- Field strength inside is $\vec{B}(r)=\frac{\mu_{0}Ni}{2\pi r}$
	- Nonconstant field strength is disadvantage of this type of solenoid


---
### **Example 1**
A long hollow cylinder with inner radius $a$ and outer radius $b$ carries a current $i$ along its length. Find the magnetic field everywhere:
	*a. if current density is uniformly distributed
	b. if nonuniform current density $j=j_{0}\frac{a}{r}$*
$\oint_{circle}\vec{B}\cdot d\vec{r} = \oint Bdr (\hat{i_{\theta}}\cdot\hat{i_{\theta}})=B\oint_{circle}dr=2\pi rB=\mu_{0}i_{enc}$
- So $\vec{B}=\frac{\mu_{0}i_{enc}}{2\pi r}\hat{i_{\theta}}$
- But $i_{enc}$ varies

We find:
- $r<a \rightarrow i_{enc}=0$
- $r>b\rightarrow i_{enc}=i$
- For $a<r<b$ we must calculate:
	- **Part a** $i_{enc}=\int \vec{j}\cdot d\vec{S}=\int\frac{i}{\pi b^{2}-\pi a^{2}}\hat{i}_{z}\cdot 2\pi r dr=\frac{i}{\pi b^{2}-\pi a^{2}}\cdot\int_{a}^{b}2\pi r dr$
	- **Part b** $i_{enc}=\int_{a}^{r}j_{0}\frac{a}{r}2\pi r dr=2\pi j_{0}a\int_{a}^{r}dr=2\pi j_{0} a (r-a)$
		- $i_{enc_{r>b}} = \int_{a}^{b}j_{0}\frac{a}{r} 2 \pi r dr=2 \pi j_{0}a(b-a)$

### **Example 2**
A long *coaxial* cable carries a uniformly distributed current *i* on the inner and outer wires but in opposite directions.
	Find the magnetic field everywhere.
	Remember:
	- $\oint \vec{B}d\vec{r}=\mu_{0}i_{enc}$
	- $i = \int \vec{j}\cdot d\vec{S}$

$\oint\vec{B}\cdot dr=2\pi rB=\mu_{0}i_{enc}\rightarrow B=\frac{\mu_{0}i_{enc}}{2\pi r}\hat{i}_{\theta}$
- To determine that the direction of $\vec{B}$ is $\hat{i}_{\theta}$ we must assign directions to our diagram, and in this case we define the $z$ direction to the right / left and $\hat{i}_{r}$ radially out.
$i = \int \vec{j}\cdot d\vec{S}$
	$\rightarrow \vec{j}_{1}=\frac{i}{\pi a^{2}}\hat{i}_z$
	$\rightarrow$ as $\vec{j}_{2} \cdot d\vec{S}$ is $<0$,  $\vec{j}_{2}=-\frac{i}{\pi c^{2}-\pi b^{2}}\hat{i}_{z}$
	
So
- $a<r<b \rightarrow i_{enc}=+i$
- $r> c \rightarrow i_{enc}=i-i=0$
- $r<a \rightarrow i_{enc}=\int_{a}^{r}\frac{i}{\pi a^{2}}2\pi r dr=i \frac{\pi r^2}{\pi a^2}$
- $b<r<c\rightarrow i_{enc}=i+\int j_{2} dS = i + \int_{b}^{r}\frac{-i}{\pi c^{2}-\pi b^2}=i-i\frac{\pi r^{2}-\pi b ^{2}}{\pi c^{2} - \pi b^{2}}$
	- *we can simplify this one but you get the picture*


- Note that $F=i\int d\vec{l} \times \vec{B}$ along the length of the wire

---


