
- **[[Cross Product]]** is $AB\sin\theta$ or the matrix thing

# ***9***
- Right Hand Rule (Pointer finger is the $\vec{v}$ of charge, the $\vec{F}$ is in the direction of the thumb, and the fingers curl in the direction of $\vec{B}$)
- $F = qvB\sin\theta$
- $\vec{F}=q\vec{v}\times\vec{B}$
- Unit is Tesla, unit of Flux is weber

- For a constant [[Current]] $i$ the drift velocity is $v_{d}=\frac{i}{en_{e}A}$
- Displacement of a small amount of charge is $dq=idt$ and $d\vec{s}=\vec{v}_{d}dt$
	- So that $d\vec{F}=dq(\vec{V}_{d}\times\vec{B})=idt(\vec{v}_{d}\times\vec{B})=i(\vec{v}_{d}dt \times \vec{B})$
- $d\vec{F}=i(d\vec{s}\times\vec{B})$
- Total force on a rigid wire is $\vec{F}=i\int_{wire}(d\vec{s}\times\vec{B})$
	- For a *straight wire* in a uniform $\vec{B}$: $\vec{F}=i\vec{L}\times\vec{B}$

### These problems can either be "Current" problems or "Charge" problems

# *10*

*Note: remember that the magnetic field $\vec{B}$ is **always** perpendicular $\perp$ to $\vec{r}$* 

To find the magnetic field from a [[Current]] carrying wire:
- a) we could use Biot-Savart Law and get $d\vec{B}=\frac{\mu_{0}i}{4\pi}\frac{d\vec{s}\times\vec{r}}{r^{3}}$
	- This is best for ***thin*** wires
	- Note that $d\vec{s}$, our displacement vector, has length $ds$ and points in direction of $i$
	- Note that $\vec{r}$ is the vector from $d\vec{s}$ to the position of interest
	- We ofc solve like $\vec{B}=\frac{\mu_{0}i}{4\pi}\int_{wire}\frac{d\vec{s}\times\vec{r}}{r^{3}}$
	- ***These problems will be straight lines or circular arcs***
- b) The other way is Ampere's Law $\oint\vec{B}\cdot d\vec{r}=\mu_{0}i_{enc}$ where $i_{enc}=\int\vec{J}\cdot d\vec{S}$
	- where $d\vec{S}$ is *a slice of surface area* and $\vec{J}$ is the *[[Current]] density*
	- We can think of this as $\oint\vec{B}\cdot d\vec{r}=\mu_{0}\int\vec{J}\cdot d\vec{S}$
		- make sure you know both ways! sometimes we want it in terms of $i_{enc}$ for a sec
	- Note that $d\vec{r}$ and $d\vec{S}$ are related by the right-hand-rule (we select one and that tells us where the other goes)  
	- We need to **exploit symmetry like Gauss' Law**
	- ***These problems will be either infinitely long wires or solenoids, but Kordell has never seen a solenoid on this exam***
	- In general, the pattern is:
		- 1. set up Amperian loop (like Gauss surface)
		- 2. find the "left hand side" of the law first -- in this case $\oint_{circle}\vec{B}\cdot d\vec{r}=2\pi rB=\mu_{0}i_{enc}$
		- 3. this means $B=\frac{\mu_{0}i_{enc}}{2\pi r}$
		- 4. then we find the enclosed [[Current]] for each section and sub it in for $i_{enc}$!
		- However magnetic field is *not conservative* so no questions about potential functions!

# *11*
- "Ignore self inductance" means FARADAY LAW TIME!
- A wire loop with a ***changing*** magnetic field through it is observed to have an "induced [[Current]]" in it.
- Note $\oint\vec{E}d\vec{r}=-v+iR$ represents electromotive force in a circuit
- $\oint \vec{E}\cdot d\vec{r} = \pm iR$ so if there is induced [[Current]] and resistance, there must be an *[[Electric Field]]* too!
- **Faraday's Law** $\oint \vec{E}\cdot d\vec{r}=-\frac{d\phi_{B}}{dt}=-\frac{d}{dt}\int \vec{B}\cdot d\vec{S}$
	- *Note* that $d\vec{r}$ and $d\vec{S}$ are related by the right-hand rule
		- $d\vec{S}$ is surface area!
	- *Note* that $\vec{B}$ here refers to either self-induction or mutual-induction
- **Lenz's Law** the minus sign in Faraday's Law. The induced [[Current]] *opposes* the magnetic field.
- Since the left-hand side is a closed loop integral, that means the [[Electric Field]] lines formed by changing $\vec{B}$ fluxes form closed loops!

Common mistakes
- Magnetic **flux** needs to change, not the magnetic field!
- For Faraday's Law you must take a **time derivative!**
- DON'T MESS UP THE SIGNS!!


# *12*
- [[Inductors]] are any material with non-negligible self-inductance
- With [[Inductors]] we have to use Faraday's Law for circuit analysis too
- $\oint \vec{E}\cdot d\vec{r}=-\frac{d}{dt}\int\vec{B}\cdot d\vec{S}=-\frac{d}{dt}\int(\vec{B}_{self}+\vec{B}_{ext})\cdot d\vec{S}=-L\frac{di}{dt}-\frac{d}{dt}\int\vec{B}_{ext}\cdot d\vec{S}\neq0$
- Positive electromotive force (*emf*) means *decreasing* [[Voltage]] (**not potential**)
- Creating a [[Voltage]] drop of $L\frac{di}{dt}$ in the direction of $i$ sorta like a resistor

- fuck da loop law, loop law is now Faraday's Law $\oint \vec{E}\cdot d\vec{r}=-\frac{d\phi_{B}}{dt}=-\frac{d}{dt}\int\vec{B}\cdot d\vec{S}$
	- Go around the loop, take [[Current]] direction as $d\vec{r}$ and find $d\vec{S}$ using the right hand rule

No LC [[Circuits]]!


---

Formula sheet has:
- Biot-Savart: $d\vec{B}=\frac{\mu_{0}i}{4\pi}\frac{d\vec{s}\times\vec{r}}{r^{3}}$
- Ampere's Law: $\oint\vec{B}\cdot d\vec{r}=\mu_{0}i_{enclosed}$
- Faraday's Law: $\oint \vec{E}\cdot d\vec{r}=-\frac{d}{dt}\int \vec{B}\cdot d\vec{S}$
- $d\vec{B}=\frac{\mu_{0}i}{4\pi}\frac{d\vec{s}\times\vec{r}}{r^{3}}$

