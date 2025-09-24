#em-ch-1 

2 charged particles will exert a force on each other.

$|\vec{F_E}|=\alpha\frac{|q_1q_2|}{x^2}$
	- $x=$ separation distance
	- $\alpha =$ constant depending on choice of units

We usually use $\alpha=\frac{1}{4\pi\epsilon_0}$,

### So the coulomb force is $\vec{F_E}=\frac{1}{4\pi\epsilon_0}\frac{q_1q_2}{x^2}\hat{r}_{21}$
- Where $\hat{r}_{21}$ is the *unit vector* direction from charge 1 to charge 2.

This force is significantly bigger than gravity, so we can ignore gravity for all our calculations.

### **Property of superposition:** 
When considering the effect of multiple charges on a single charge. Ex: "there are charges $q_1$, $q_2$, and $q_3$ at positions (...), what is the force upon $q_4$?" you can simply determine the force on $q_1$ upon $q_4$ as though the other charges were not there, do the same for all charges, and sum the vectors.
- **NOTE** whenever doing this in practice, calculate the raw force with Coulomb's Law *first*, then convert the force into a vector by multiplying the force value with $\hat{r}=\frac{\vec{r}}{|\vec{r}|}$, where $\vec{r}$ is the direction vector.


### **Distributed Charge:**
Coulomb's Law only works for a point. If we want to examine an equally distributed charge, we'd have to separate it into point charges and add it together. We do this using the integral.

On a line, it's:
$d\vec{F}=\frac{1}{4\pi\epsilon_0}\frac{q\frac{Q}{L}dx}{x^2}$
or, an infinitesimally small part of the force is equal to the coulomb force at an infinitesimally small segment of the line, so that:
$F=\int^{a+L}_{L}\frac{1}{4\pi\epsilon_0}\frac{q\frac{Q}{L}}{x^2}dx$




