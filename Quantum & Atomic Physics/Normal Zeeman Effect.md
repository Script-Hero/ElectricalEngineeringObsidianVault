#Chapter7 

**Zeeman Effect** is when the spectral lines emitted by atoms in a magnetic field split into **3** energy levels
- Any more than 3 energy levels and you're dealing with the [[Anomolous Zeeman Effect]]

#### External magnetic fields reduce spherical symmetry in [[Hydrogen Atom]]

##### *Normal* Zeeman Effect
1. A spectral line is split into (not $2l+1$ like I originally thought but) **3** lines
	1. This is the number of possible $m_l$ states!
2. The atom behaves (is modeled) as a small magnet
3. The [[Current]] loop has a magnetic moment at $\mu = IA$ and the period $T=\frac{2\pi r}{v}$
4. The electron behaves (is modeled as) an orbiting circular [[Current]] loop of differential charge $I=\frac{dq}{dt}$ around the nucleus
5. $\vec{\mu}=-\frac{e}{2m}\vec{L}$, where $L=mvr$ is the magnitude of the orbital's angular momentum
6. The dipole has the potential energy $V_B=-\vec{\mu} \cdot \vec{B}$ 
	1. $\vec\mu$ is in a random direction if there is no magnetic field to align it
7. The torque between $\vec\mu$ and $\vec B$ cause a "precession" of $\vec\mu$:
	1. $\mu_z=\frac{e\hbar}{2m}2m_l=-\mu_B m_l$ 
		1. where $\mu_B$ is called a **Bohr magnetron**
8. $\vec\mu$ **cannot align directly in the $z$** direction and has only certain allowed *quantized* orientations: $\vec\mu=-\mu_B\frac{\vec L}{\hbar}$
9. The potential energy is quantized due to the [[Magnetic Quantum Number]] $m_l$:
	1. $V_B=-\mu_ZB=+\mu_Bm_lB$
		1. $\mu_B=\frac{e\hbar}{2m_e}$ is the **Bohr Magnetron**
		2. $B$ is the *strength* of the applied magnetic field
		3. $\Delta m_l$ is the *difference* in the [[Magnetic Quantum Number]]

### Zeeman Example
When a magnetic field of strength $B=1.0\mbox{T}$ is applied, the $2p$ level of atomic hydrogen is split into three different energy states with energy differences of $\Delta E=\mu_BB\Delta m_l$:
- Given in problem that the [[Principal Quantum Number]] $n=2$ and [[Orbital Angular Momentum Quantum Number]] $l=1$
- from this we find that the [[Magnetic Quantum Number]] $m_l=1,0,-1$

| **$m_l$** |  **Energy**  |
| :-------: | :----------: |
|     1     | $E_0+\mu_BB$ |
|     0     |    $E_0$     |
|    -1     | $E_0-\mu_BB$ |

We can then find the exact energies for each of the split lines (where each split corresponds to each allowed $m_l$ configuration) by using 
- the $E_0=-\frac{13.6 \mbox{eV}}{n^2}$ equation with $n=2$ to get $E_0=-3.4\mbox{eV}$, 
- and calculate $\mu_B=\frac{e\hbar}{2m_{e}}=5.79\times10^{-5}\mbox{eV/T}$, giving us the result:
- $\Delta E = \mu_B B \Delta m_l=5.79\times10^{-5}\times1.0\times(+1,0,\mbox{ and }-1)$
	- $=5.79\times10^-5,0,-5.79\times10^-5$  
- causing the answers to be:

| **$m_l$** |  **Energy**   |
| :-------: | :-----------: |
|     1     | -3.3999421 eV |
|     0     |    -3.4 eV    |
|    -1     | -3.4000579 eV |

If you want, you can now solve for the wavelength shift $\Delta \lambda$ by rearranging the equation $\Delta E = hc\frac{\Delta\lambda}{\lambda^2}$

### Transitioning energy states:
![[zeeman_transitioning_energy_states_2.png]]
- We explain the transition from energy state $a$ to $b$ by releasing in 3 burns of different energy, similarly to the table above.
### Inhomogeneous Magnetic Field
An atomic beam of particles in the $l=1$ state pass through a *inhomogeneous* magnetic field along the $z$ direction.
![[inhomogenous_beam.png]]
- $V_B=-\mu_zB$
- $F_z=-(\frac{dV_B}{dz})=\mu_z(\frac{dB}{dz})$
- The $m_l=+1$ state will be deflected down and the $m_l=-1$ state will be reflected up, and the $m_l=0$ state will be undeflected.
- If the *space quantization* was due to the [[Magnetic Quantum Number]] $m_l$, then there should be an *odd* number of spectral lines, as the *number of possible $m_l$ states* $= 2l+1$
