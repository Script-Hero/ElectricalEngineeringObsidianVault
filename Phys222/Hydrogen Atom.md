#Chapter7 
### 7.1 Application to the [[Shrodinger Equation]] 

Because the approximation of potential energy is electrostatic $V(r)=-\frac{e^2}{4\pi\epsilon_0r}$, you can rewrite the three-dimensional time-independent [[Shrodinger Equation]], for hydrongen-like atoms $He^{+}$ or $Li^{++}$ 

![[shrodiner_hydrogen_atom.png]]
- Replacing $e^2$ with $Ze^2$, $Z$ being the atomic number

Because the potential $V(r)$ depends on the distance $r$, we can transform into radial coordinates, and insert the Couloumb potential into the transformed equation:
![[transformed_shrodinger_hydrogen_satom.png]]

### **Ultimately we find that the wave equation is dividable into** $\Psi(r,\theta,\phi)=R(r)f(\theta)g(\phi)$
- Divide and concur!
- We are going to use the **Radial Wave Function** (chart on [[Radial Equation]])
	- function of $n$ and $l$
- and **Normalized Spherical Harmonic Function** (chart on [[Angular Equation]])
	- function of $l$ and $m_l$
- Multiplied together to get the wave function $\Psi(r,\theta,\phi)$
	- See [[Combined Wave Function]]

## 7.2 *Solutions* of the [[Shrodinger Equation]] for Hydrogen Atoms
- Use separation of variables:
![[seperation_of_variables_solve_shrodinger_hydrogen.png]]
- Only $r$ and $\theta$ appear on the left side and only $\phi$ appears on the right side
- The left side of the equation cannot change as $\phi$ changes
- The right side of the equation cannot change with either $r$ or $\theta$ 
- each side needs to be equal to a constant for the equation to be true
	- $\frac{d^2g}{d\phi^2}=-m_l^2g$ the [[Azimuthal Equation]]
	- ![[radial_equation.png]] the [[Radial Equation]]
	- ![[angular_equation.png]] the [[Angular Equation]]
- Allows you to separate everything into 3 ordinary second-order differential equations each containing only one variable 
- it is convenient to choose a solution that is $e^{im_{l}\phi}$


### Energy States
- Determined by $n$ the [[Principal Quantum Number]]
- In the *ground state* $n=1$, an atom cannot emit radiation, but can absorb radiation or gain energy through inelastic collisions with particles
- Using Selection Rules and Wave Functions, we can [[Energy Transitions]] for the electron to change from one state to another.