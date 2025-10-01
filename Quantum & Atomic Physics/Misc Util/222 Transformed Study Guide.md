# Equations and Stuff
## Constants and Fundamental Values

- **Speed of Light** ($c$)
    - Value: $c = 3.00 \times 10^{8} \ \text{m/s}$
- **Planck's Constant** ($h$)
    - Value: $h = 6.6261 \times 10^{-34} \ \text{J} \cdot \text{s}$
- **Reduced Planck's Constant** ($\hbar$)
    - Definition: $\hbar = \dfrac{h}{2\pi}$
    - Value: $\hbar = 1.0546 \times 10^{-34} \ \text{J} \cdot \text{s}$
- **Elementary Charge** ($e$)
    - Value: $e = 1.602 \times 10^{-19} \ \text{C}$
- **Electron Mass** ($m_e$)
    - Value: $m_e = 9.109 \times 10^{-31} \ \text{kg}$
- **Proton Mass** ($m_p$)
    - Value: $m_p = 1.673 \times 10^{-27} \ \text{kg}$
- **Neutron Mass** ($m_n$)
    - Value: $m_n = 1.675 \times 10^{-27} \ \text{kg}$
- **Bohr Radius** ($a_0$)
    - Value: $a_0 = 0.529 \ \text{Å} = 0.529 \times 10^{-10} \ \text{m}$
- **Rydberg Constant** ($R$)
    - Value: $R = 1.097 \times 10^{7} \ \text{m}^{-1}$
- **Stefan-Boltzmann Constant** ($\sigma$)
    - Value: $\sigma = 5.670 \times 10^{-8} \ \text{W} / \text{m}^{2} \cdot \text{K}^{4}$
- **Wien's Displacement Constant** ($b$)
    - Value: $b = 2.897 \times 10^{-3} \ \text{m} \cdot \text{K}$
- **Compton Wavelength of Electron** ($\lambda_C$)
    - Value: $\lambda_C = \dfrac{h}{m_e c} = 2.43 \times 10^{-12} \ \text{m}$

---

## Relativistic Mechanics

### Lorentz Factor

**Equation:** $\gamma = \frac{1}{\sqrt{1-\frac{v^{2}}{c^{2}}}}$

- **$\gamma$**: Lorentz factor (dimensionless)
- **$v$**: Velocity of the particle ($\text{m/s}$)
- **$c$**: Speed of light ($3.00 \times 10^{8} \ \text{m/s}$)

**Context:** Used to calculate relativistic effects such as time dilation, length contraction, and increase of mass with velocity.

**Limitations:** Only significant when $v$ is close to $c$. For $v \ll c$, $\gamma \approx 1$ and classical mechanics applies.

### Relativistic Kinetic Energy

**Equation:** $K=(\gamma - 1)mc^{2}$
- **$K$**: Kinetic energy ($\text{J}$ or $\text{eV}$)
- **$m$**: Rest mass ($\text{kg}$)
- **$c$**: Speed of light ($\text{m/s}$)
- **$\gamma$**: Lorentz factor (dimensionless)

**Context:** Used to calculate the kinetic energy of particles moving at relativistic speeds.

**Limitations:** Reduces to classical kinetic energy $K = \dfrac{1}{2} m v^{2}$ when $v \ll c$.

### Relativistic Momentum

**Equation:** $p = \gamma m v$

- **$p$**: Momentum ($\text{kg} \cdot \text{m/s}$)
- **$\gamma$**: Lorentz factor
- **$m$**: Rest mass ($\text{kg}$)
- **$v$**: Velocity ($\text{m/s}$)

**Context:** Used when calculating momentum at relativistic speeds.

**Limitations:** At low speeds, reduces to classical momentum $p = m v$.

---

## Blackbody Radiation

### Wien's Displacement Law

**Equation:** $\lambda_{max}=\frac{b}{T}$

- **$\lambda_{\text{max}}$**: Wavelength of maximum emission ($\text{m}$)
- **$b$**: Wien's displacement constant ($2.897 \times 10^{-3} \ \text{m} \cdot \text{K}$)
- **$T$**: Absolute temperature ($\text{K}$)

**Context:** Determines the wavelength at which a blackbody radiates most intensely.

**Limitations:** Applicable to ideal blackbody emitters; real objects may deviate.

### Stefan-Boltzmann Law

**Equation:** $R=\sigma T^{4}$

- **$R$**: Radiated power per unit area ($\text{W/m}^{2}$)
- **$\sigma$**: Stefan-Boltzmann constant ($5.670 \times 10^{-8} \ \text{W} / \text{m}^{2} \cdot \text{K}^{4}$)
- **$T$**: Absolute temperature ($\text{K}$)

**Context:** Calculates total energy radiated per unit area by a blackbody.

**Limitations:** Assumes perfect blackbody; emissivity of real objects may differ.

---

## Photoelectric Effect

### Einstein's Photoelectric Equation

**Equation:** $K_{max}=hf-\phi$

- **$K_{\text{max}}$**: Maximum kinetic energy of emitted electrons ($\text{J}$ or $\text{eV}$)
- **$h$**: Planck's constant ($6.6261 \times 10^{-34} \ \text{J} \cdot \text{s}$)
- **$f$**: Frequency of incident light ($\text{Hz}$)
- **$\phi$**: Work function of the material ($\text{J}$ or $\text{eV}$)

**Context:** Describes the kinetic energy of photoelectrons emitted from a material when illuminated by light.

**Limitations:** Assumes single-photon absorption; neglects multi-photon processes.

### Threshold Frequency

**Equation:** $f_{0} = \frac{\phi}{h}$

- **$f_{0}$**: Threshold frequency ($\text{Hz}$)
- **$\phi$**: Work function ($\text{J}$)

**Context:** Minimum frequency of light required to eject electrons from a material.

**Limitations:** Below $f_{0}$, no electrons are emitted regardless of light intensity.

### Stopping Potential

**Equation:** $eV_{s}=K_{max}$

- **$e$**: Elementary charge ($1.602 \times 10^{-19} \ \text{C}$)
- **$V_{s}$**: Stopping potential ($\text{V}$)
- **$K_{\text{max}}$**: Maximum kinetic energy ($\text{J}$)

**Context:** Potential required to stop the most energetic photoelectrons.

**Limitations:** Assumes negligible contact potential and space charge effects.

---

## Compton Effect

### Compton Wavelength Shift

**Equation:** $\Delta \lambda = \lambda' - \lambda = \frac{h}{m_{e}c}(1-\cos\theta)$

- **$\Delta \lambda$**: Change in wavelength ($\text{m}$)
- **$\lambda$**: Initial wavelength ($\text{m}$)
- **$\lambda'$**: Scattered wavelength ($\text{m}$)
- **$h$**: Planck's constant
- **$m_e$**: Electron mass
- **$c$**: Speed of light
- **$\theta$**: Scattering angle (radians or degrees)

**Context:** Describes increase in wavelength of photons scattered by electrons.

**Limitations:** Significant for high-energy photons (X-rays, gamma rays); negligible for visible light.

### Energy of Scattered Photon

**Equation:** $E'=\frac{E}{1+\frac{E}{m_{e}c^{2}}(1-\cos\theta)}$

- **$E$**: Initial photon energy ($\text{J}$ or $\text{eV}$)
- **$E'$**: Scattered photon energy ($\text{J}$ or $\text{eV}$)

**Context:** Calculates energy of photon after Compton scattering.

**Limitations:** Requires relativistic treatment; only valid for photon-electron scattering.

---

## Atomic Models and the Hydrogen Atom

### Rydberg Formula

**Equation:** $\frac{1}{\lambda}=R(\frac{1}{n_{f}^{2}}-\frac{1}{n_{i}^{2}})$

- **$\lambda$**: Wavelength of emitted or absorbed light ($\text{m}$)
- **$R$**: Rydberg constant ($1.097 \times 10^{7} \ \text{m}^{-1}$)
- **$n_{i}$**: Initial principal quantum number
- **$n_{f}$**: Final principal quantum number

**Context:** Predicts wavelengths of spectral lines in hydrogen and hydrogen-like atoms.

**Limitations:** Does not account for fine structure or multi-electron interactions.

### Bohr Model Energy Levels

**Equation:** $E_{n}= -\frac{13.6 eV}{n^{2}}$

- **$E_{n}$**: Energy of the electron in the $n$-th orbit ($\text{eV}$)
- **$n$**: Principal quantum number ($n = 1, 2, 3, \dots$)

**Context:** Calculates energy levels of electrons in hydrogen atom.

**Limitations:** Accurate for hydrogen; not applicable to multi-electron atoms without corrections.

### Electron Orbits and Speeds

**Radius of Orbit:** $r_{n}= n^{2}a_{0}$

- **$r_{n}$**: Radius of the $n$-th orbit ($\text{m}$)

**Electron Speed:** $v_{n} = \frac{v_{0}}{n}$

- **$v_{n}$**: Speed of electron in $n$-th orbit ($\text{m/s}$)
- **$v_{0}$**: Speed in ground state ($v_{0} = 2.18 \times 10^{6} \ \text{m/s}$)

**Context:** Describes quantized orbits in the Bohr model.

**Limitations:** Assumes circular orbits; does not account for quantum mechanics beyond Bohr model.

---

## De Broglie Waves and Wave Mechanics

### De Broglie Wavelength

**Equation:** $\lambda = \frac{h}{p}=\frac{h}{mv}$

- **$\lambda$**: De Broglie wavelength ($\text{m}$)
- **$h$**: Planck's constant
- **$p$**: Momentum ($\text{kg} \cdot \text{m/s}$)
- **$m$**: Mass ($\text{kg}$)
- **$v$**: Velocity ($\text{m/s}$)

**Context:** Relates particle's wave properties to its momentum.

**Limitations:** For particles; significant wave properties when $\lambda$ is comparable to system dimensions.

### Bragg's Law

**Equation:** $n\lambda = 2d\sin\theta$

- **$n$**: Order of diffraction (integer)
- **$\lambda$**: Wavelength of incident wave ($\text{m}$)
- **$d$**: Interplanar spacing in crystal ($\text{m}$)
- **$\theta$**: Angle of incidence/reflection ($\text{degrees}$ or $\text{radians}$)

**Context:** Used in X-ray diffraction to determine crystal structures.

**Limitations:** Assumes perfect crystal lattice and coherent monochromatic radiation.

---

## Wave Properties

### Wave Number and Angular Frequency

**Wave Number:**$k=\frac{2\pi}{\lambda}$

- **$k$**: Wave number ($\text{rad/m}$)
- **$\lambda$**: Wavelength ($\text{m}$)

**Angular Frequency:** $\omega = 2\pi f$

- **$\omega$**: Angular frequency ($\text{rad/s}$)
- **$f$**: Frequency ($\text{Hz}$)

### Phase Velocity and Group Velocity

**Phase Velocity:** $v_{p}=\frac{\omega}{k}$

**Group Velocity:** $v_{g}= \frac{d\omega}{dk}$

**Context:** Phase velocity is the speed of wave crests; group velocity is the speed at which the envelope or overall modulation of the waves propagates, often associated with energy transfer.

**Limitations:** In non-dispersive media, $v_{p} = v_{g}$. In dispersive media, they differ.

---

## Uncertainty Principle

### Heisenberg's Uncertainty Principle

**Position-Momentum Uncertainty:** $\Delta x \Delta p \geq \frac{\hbar}{2}$

- **$\Delta x$**: Uncertainty in position ($\text{m}$)
- **$\Delta p$**: Uncertainty in momentum ($\text{kg} \cdot \text{m/s}$)

**Energy-Time Uncertainty:** $\Delta E \Delta t \geq \frac{\hbar}{2}$

- **$\Delta E$**: Uncertainty in energy ($\text{J}$ or $\text{eV}$)
- **$\Delta t$**: Uncertainty in time ($\text{s}$)

**Context:** Fundamental limits on precision of simultaneous measurements of certain pairs of observables.

**Limitations:** Intrinsic property of quantum systems, not due to measurement imperfections.

---

## Quantum Mechanics

### Schrödinger Equation

**Time-Independent Schrödinger Equation (1D):** $-\frac{\hbar^{2}}{2m}\frac{d^{2}\psi(x)}{dx^{2}}+V(x)\psi(x) = E\psi(x)$

- **$\psi(x)$**: Wave function
- **$V(x)$**: Potential energy function ($\text{J}$)
- **$E$**: Energy eigenvalue ($\text{J}$)
- **$m$**: Mass ($\text{kg}$)

**Context:** Fundamental equation of quantum mechanics; describes how quantum state evolves in space.

**Limitations:** Non-relativistic; for high velocities, relativistic quantum mechanics is required.

### Infinite Square Well (Particle in a Box)

**Energy Levels:** $E_{n} = \frac{n^{2}\pi^{2}\hbar^{2}}{2mL^{2}}$
**Wave Functions:** $\psi_{n}(x)=\sqrt{\frac{2}{L}}\sin(\frac{n\pi x}{L})$

- **$n$**: Quantum number ($n = 1, 2, 3, \dots$)
- **$L$**: Width of the well ($\text{m}$)

**Context:** Models a particle confined to a perfectly rigid box with infinitely high walls.

**Limitations:** Idealized model; in reality, potential wells are finite.

### Normalization of Wave Functions

**Normalization Condition:** $\int\limits_{-\infty}^{\infty}|\psi(x)|^{2}dx=1$

**Context:** Ensures total probability of finding the particle somewhere is unity.

**Limitations:** Applicable to normalized wave functions.

---

## Harmonic Oscillator

### Energy Levels

**Equation:** $E_{n}= (n + \frac{1}{2})\hbar\omega$

- **$n$**: Quantum number ($n = 0, 1, 2, \dots$)
- **$\omega$**: Angular frequency ($\omega = \sqrt{\dfrac{k}{\mu}}$)
- **$k$**: Force constant or spring constant ($\text{N/m}$)
- **$\mu$**: Reduced mass ($\text{kg}$)

**Context:** Describes quantized energy levels in systems that can be approximated as harmonic oscillators, such as molecular vibrations.

**Limitations:** Assumes potential energy is quadratic in displacement; deviations at large amplitudes.

### Reduced Mass

**Equation:** $\mu = \frac{m_{1}m_{2}}{m_{1}+ m_{2}}$

- **$m_{1}, m_{2}$**: Masses of two particles ($\text{kg}$)

**Context:** Used when dealing with two-body problems, such as diatomic molecules.

---

## Additional Concepts

### Reduced Mass in Hydrogen-like Atoms

When dealing with systems like muonic hydrogen or positronium, adjust formulas for reduced mass.

**Bohr Radius with Reduced Mass:** $a = \frac{\hbar ^ 2}{\mu k e^{2}}$

- **$a$**: Adjusted Bohr radius ($\text{m}$)
- **$\mu$**: Reduced mass
- **$k$**: Coulomb's constant ($k = \dfrac{1}{4\pi \varepsilon_{0}}$)
- **$e$**: Elementary charge

**Energy Levels with Reduced Mass:** $E_{n}= -\frac{\mu e^{4}}{8\epsilon_{0}^{2}\hbar^{2}n^{2}}$​

**Context:** Necessary when the masses of both particles are comparable.
*dis right?*

---

## Units and Conversions

- **Energy Conversion:** $\text{eV} = 1.602 \times 10^{-19} \ \text{J}$
- **Momentum and Energy Relation (Relativistic):** $E^{2} = (p c)^{2} + (m c^{2})^{2}$
- **Wavelength-Frequency Relation:** $c=\lambda f$
- **Angular Frequency:** $\omega = 2\pi f$
- **Wave Number:** $k = \frac{2\pi}{\lambda}$

---

## When to Use Equations and Limitations

- **Relativistic Equations:** Use when particle speeds are a significant fraction of $c$.
- **Blackbody Radiation Laws:** Use for thermal radiation from idealized blackbodies.
- **Photoelectric Equations:** Apply to photoemission experiments; not valid for multiphoton processes.
- **Compton Effect Equations:** Use for photon scattering involving high-energy photons.
- **Bohr Model Equations:** Applicable to hydrogen and hydrogen-like ions; corrections needed for multi-electron atoms.
- **De Broglie Wavelength:** Significant for particles with small mass or high speed, where wave properties are observable.
- **Uncertainty Principle:** Fundamental limit in quantum mechanics; always applicable.
- **Schrödinger Equation:** Use for quantum systems where potential energy is known; non-relativistic approximation.

---
# Conceptual Stuff

## Fundamental Constants and Unit Conversions

### Universal Constants

1. **Planck's Constant ($h$)**
    
    - Value: $6.6261 \times 10^{-34} \ \text{J} \cdot \text{s}$
    - Significance: Fundamental constant in quantum mechanics, relates the energy of a photon to its frequency.
2. **Speed of Light in Vacuum ($c$)**
    
    - Value: $3.00 \times 10^{8} \ \text{m/s}$
    - Significance: The maximum speed at which all massless particles and associated fields (including light) can travel in a vacuum.
3. **Elementary Charge ($e$)**
    
    - Value: $1.602 \times 10^{-19} \ \text{C}$
    - Significance: The magnitude of the electric charge carried by a single proton or the negative of that carried by a single electron.
4. **Electron Mass ($m_e$)**
    
    - Value: $9.109 \times 10^{-31} \ \text{kg}$
    - Significance: Fundamental particle mass used in calculations involving electrons.
5. **Proton Mass ($m_p$)**
    
    - Value: $1.673 \times 10^{-27} \ \text{kg}$
    - Significance: Fundamental particle mass used in calculations involving protons.
6. **Neutron Mass ($m_n$)**
    
    - Value: $1.675 \times 10^{-27} \ \text{kg}$
7. **Bohr Radius ($a_0$)**
    
    - Value: $0.529 \ \text{Å} = 0.529 \times 10^{-10} \ \text{m}$
    - Significance: Represents the most probable distance between the nucleus and the electron in a hydrogen atom in its ground state.
8. **Rydberg Constant ($R$)**
    
    - Value: $1.097 \times 10^{7} \ \text{m}^{-1}$
    - Significance: Used in calculating the wavelengths of spectral lines in hydrogen.

### Unit Conversions

- **Energy**
    - $1 \ \text{eV} = 1.602 \times 10^{-19} \ \text{J}$
- **Length**
    - $1 \ \text{Å} = 1 \times 10^{-10} \ \text{m}$
    - $1 \ \text{nm} = 1 \times 10^{-9} \ \text{m}$
- **Mass-Energy Equivalence**
    - $1 \ \text{MeV}/c^2 = 1.783 \times 10^{-30} \ \text{kg}$
- **Temperature**
    - $T \ (\text{in Kelvin}) = T \ (\text{in Celsius}) + 273.15$

**Conceptual Note:** Always ensure units are consistent when performing calculations. Convert quantities to SI units unless instructed otherwise.

---

## Discoveries and Key Experiments

### Discovery of X-rays and Electrons

1. **X-rays (Wilhelm Röntgen, 1895)**
    
    - Discovery: Röntgen discovered X-rays while experimenting with cathode rays and fluorescence.
    - Significance: Revealed the existence of high-energy electromagnetic radiation that can penetrate materials opaque to visible light.
2. **Electron (J.J. Thomson, 1897)**
    
    - Discovery: Thomson discovered the electron using cathode ray tubes, showing that cathode rays were composed of negatively charged particles (electrons).
    - Significance: Demonstrated that atoms have internal structure and are divisible.

### Millikan Oil Drop Experiment (Robert Millikan, 1909)

- **Objective:** To measure the elementary electric charge ($e$).
- **Method:** By observing tiny charged oil droplets between two electric plates and balancing gravitational and electric forces.
- **Findings:**
    - Determined the charge of a single electron.
    - Confirmed that charge is quantized in discrete units of $e$.
- **Conceptual Significance:** Provided strong evidence for the quantization of electric charge.

---

## Blackbody Radiation

### Concept

- **Blackbody:** An idealized object that absorbs all incident electromagnetic radiation and re-emits it in a characteristic spectrum dependent on its temperature.
- **Problem in Classical Physics:** The "Ultraviolet Catastrophe" predicted infinite energy emission at short wavelengths, which contradicted experimental observations.

### Planck's Solution

- **Planck's Postulates:**
    
    1. **Quantization of Energy:** Energy is exchanged in discrete amounts called quanta. $E_{n}= nhf$
        - **$E_n$:** Energy of the oscillator.
        - **$n$:** Quantum number (integer).
        - **$h$:** Planck's constant.
        - **$f$:** Frequency of oscillation.
    2. **Energy Emission/Absorption:** Oscillators can only absorb or emit energy in multiples of $h f$.
- **Planck's Radiation Law:** $I(\lambda, T)=\frac{2\pi h c^{2}}{\lambda ^ 5}\frac{1}{e^{\frac{hc}{\lambda k_{B}T}}-1}$
    
    - **$I(\lambda, T)$:** Intensity per unit wavelength.
    - **$k_B$:** Boltzmann constant.
- **Significance:** Resolved the ultraviolet catastrophe by introducing quantization, laying the foundation for quantum mechanics.
    

### Wien's Displacement Law

- **Equation:** $\lambda_{max} =\frac{b}{T}$
    - **$b$:** Wien's displacement constant ($2.897 \times 10^{-3} \ \text{m} \cdot \text{K}$).
- **Conceptual Use:** Determines the peak wavelength of emission from a blackbody at temperature $T$.

### Stefan-Boltzmann Law

- **Equation:** $R=\sigma T^4$
    - **$R$:** Radiated power per unit area.
    - **$\sigma$:** Stefan-Boltzmann constant ($5.670 \times 10^{-8} \ \text{W} / \text{m}^{2} \cdot \text{K}^{4}$).
- **Conceptual Use:** Calculates the total energy radiated per unit area from a blackbody.

---

## Photoelectric Effect

### Concept

- **Observation:** Emission of electrons from a material when it is exposed to light of sufficient frequency.
- **Key Findings:**
    - No electrons are emitted below a certain threshold frequency, regardless of light intensity.
    - Kinetic energy of emitted electrons depends on the frequency, not intensity, of the incident light.
- **Einstein's Explanation:**
    - Light consists of photons with energy $E = h f$.
    - A photon can eject an electron if $h f$ exceeds the work function $\phi$ of the material.

### Key Equations

1. **Einstein's Photoelectric Equation:** $K_{max}=hf-\phi$
    
    - **$K_{\text{max}}$:** Maximum kinetic energy of emitted electrons.
    - **$\phi$:** Work function of the material.
2. **Threshold Frequency:** $f_{0}= \frac{\phi}{h}$
    - **$f_{0}$:** Minimum frequency required to emit electrons.
3. **Stopping Potential:** $eV_{s}= K_{\text{max}}$
    - **$V_{s}$:** Stopping potential needed to prevent photoelectrons from reaching the anode.

### Conceptual Significance

- **Proves the Particle Nature of Light:** Demonstrates that light has quantized energy packets (photons).
- **Guidelines for Problems:**
    - Use the photoelectric equation when dealing with electron emission due to light.
    - Ensure frequency is above the threshold frequency for emission.
    - Stopping potential relates directly to the maximum kinetic energy.

---

## Compton Effect

### Concept

- **Observation:** X-rays scatter off electrons with a longer wavelength than the incident X-rays.
- **Explanation:** Photon collides with a stationary electron, transferring some energy and momentum, leading to an increase in the photon's wavelength.

### Key Equation

- **Compton Wavelength Shift:** $\Delta \lambda = \lambda ' - \lambda = \frac{h}{m_{e}c}(1-\cos\theta)$
    - **$\lambda$ and $\lambda'$:** Initial and scattered wavelengths.
    - **$\theta$:** Scattering angle.
    - **$\frac{h}{m_{e} c}$:** Compton wavelength of the electron ($2.43 \times 10^{-12} \ \text{m}$).

### Conceptual Significance

- **Confirms Dual Nature of Light and Matter:** Demonstrates the particle aspect of electromagnetic radiation.
- **Application:**
    - Use the Compton equation when dealing with photon scattering problems.
    - Applicable mainly for high-energy photons (X-rays, gamma rays).

---

## Atomic Models

### Early Models

1. **Thomson's Plum Pudding Model**
    
    - **Concept:** Electrons embedded in a positively charged sphere.
    - **Weakness:** Could not explain the results of scattering experiments.
2. **Rutherford's Nuclear Model**
    
    - **Concept:** Atom consists of a dense, positively charged nucleus surrounded by electrons.
    - **Experiment:** Gold foil experiment showed that some alpha particles were deflected at large angles.
    - **Weakness:** Could not explain atomic stability and discrete spectral lines.
3. **Bohr's Model**
    
    - **Concept:**
        - Electrons orbit the nucleus in quantized orbits with specific energies.
        - Angular momentum is quantized: $L = n \hbar$.
    - **Strengths:**
        - Explained spectral lines of hydrogen.
        - Introduced quantization into atomic structure.
    - **Weaknesses:**
        - Only accurately describes hydrogen-like atoms.
        - Does not account for electron-electron interactions or relativistic effects.

### Bohr Radius and Energy Levels

- **Bohr Radius:** $a_0 = \dfrac{\hbar^{2}}{m_e e^{2}} = 0.529 \ \text{Å}$
- **Energy Levels:** $E_n = - \dfrac{13.6 \ \text{eV}}{n^{2}}$
    - **$n$:** Principal quantum number.

### Electron Transitions

- **Energy Difference:** $\Delta E = E_{n_{f}}-E_{n_{i}}=hf$
- **Wavelength of Emitted/Absorbed Light:** $\frac{1}{\lambda}=R(\frac{1}{n_{f}^{2}}-\frac{1}{n_{i}^{2}})$

**Guidelines for Problems:**

- Use the Bohr model for hydrogen or hydrogen-like atoms.
- Calculate energy levels and transitions using the given equations.
- Remember that electron transitions to lower energy levels emit photons; transitions to higher levels absorb photons.

### Correspondence Principle

- **Concept:** Quantum mechanics must agree with classical physics in the limit of large quantum numbers.
- **Application:** Validates the use of quantum mechanics by showing consistency with classical predictions at macroscopic scales.

---

## Electron Shells and Moseley Plot

### Electron Shells

- **Concept:** Electrons occupy energy levels or shells around the nucleus.
- **Notation:** Shells labeled as K, L, M, N corresponding to $n = 1, 2, 3, 4$.

### Moseley's Law

- **Observation:** Characteristic X-ray frequencies emitted by elements are related to their atomic numbers.
- **Equation:** $\sqrt{f}\propto(Z-\sigma)$
    - **$f$:** Frequency of emitted X-ray.
    - **$Z$:** Atomic number.
    - **$\sigma$:** Screening constant.
- **Significance:** Provided evidence that the atomic number is the fundamental property organizing the periodic table.

---

## Bragg's Law and Bragg Planes

### Bragg's Law

- **Equation:** $n\lambda = 2d\sin\theta$
    - **$n$:** Order of reflection.
    - **$\lambda$:** Wavelength of incident wave.
    - **$d$:** Distance between crystal planes.
    - **$\theta$:** Angle of incidence/reflection.

### Conceptual Application

- **Used to determine crystal structures using X-ray diffraction.**
- **Guidelines for Problems:**
    - Apply Bragg's Law when dealing with diffraction patterns.
    - Ensure angles are correctly measured with respect to the crystal planes.

---

## De Broglie Waves

### Concept

- **Hypothesis:** Particles have wave-like properties, characterized by a wavelength.
- **De Broglie Wavelength:** $\lambda = \dfrac{h}{p} = \dfrac{h}{m v}$
- **Significance:** Introduced wave-particle duality for matter, fundamental to quantum mechanics.

### Applications

- **Electron Diffraction:** Explains diffraction patterns observed when electrons pass through crystals.
- **Guidelines for Problems:**
    - Use de Broglie's equation to calculate the wavelength associated with a particle.
    - Significant when the particle's wavelength is comparable to the dimensions of the system (e.g., electrons, neutrons).

---

## Properties of Wave Motion

### Phase Velocity ($v_p$)

- **Definition:** $v_{p}=\frac{\omega}{k}$
    - **$\omega$:** Angular frequency.
    - **$k$:** Wave number.

### Group Velocity ($v_g$)

- **Definition:** $v_{g}=\frac{d\omega}{dk}$
- **Significance:** Represents the velocity at which the overall shape of the waves' amplitudes—known as the modulation or envelope—propagates through space.

### Relation in Non-Dispersive Medium

- **In a non-dispersive medium:** $v_p = v_g$

### Guidelines for Problems

- **Phase Velocity:** Use when interested in the propagation of a single frequency component.
- **Group Velocity:** Use when dealing with wave packets or pulses composed of multiple frequencies.

---

## Uncertainty Principle

### Heisenberg's Uncertainty Principle

1. **Position-Momentum Uncertainty:** $\Delta x \Delta p \geq \frac{\hbar}{2}$
    
    - **$\Delta x$:** Uncertainty in position.
    - **$\Delta p$:** Uncertainty in momentum.
2. **Energy-Time Uncertainty:** $\Delta E \Delta t \geq \frac{\hbar}{2}$
    
    - **$\Delta E$:** Uncertainty in energy.
    - **$\Delta t$:** Uncertainty in time.

### Conceptual Significance

- **Fundamental Limit:** Cannot simultaneously know exact position and momentum (or energy and time) of a particle.
- **Implications:**
    - Affects measurements at quantum scales.
    - Justifies the energy spread of short-lived particles or states.

### Guidelines for Problems

- Use the uncertainty principle to estimate minimum uncertainties.
- Apply to scenarios like confined particles (particle in a box), energy levels of unstable particles.

---

## The Copenhagen Interpretation

### Key Principles

1. **Heisenberg's Uncertainty Principle:** Limits the precision of simultaneous measurements.
2. **Bohr's Complementarity Principle:** Objects have both particle and wave properties; the type of measurement determines which aspect is observed.
3. **Born's Statistical Interpretation:** The square of the wave function's magnitude gives the probability density of finding a particle.

### Conceptual Significance

- **Philosophical Framework:** Provides an interpretation of quantum mechanics emphasizing probabilistic outcomes and the role of the observer.
- **Applications:** Underpins the understanding of quantum phenomena and guides the interpretation of experimental results.

---

## Particle in a Box

### Concept

- **Model:** A particle confined in a one-dimensional box with infinitely high walls (infinite potential well).
- **Wave Function:** $\phi_{n}(x)=\sqrt{\frac{2}{L}}\sin(\frac{n\pi x}{L})$
    - **$n$:** Quantum number.
    - **$L$:** Length of the box.
- **Energy Levels:** $E_{n} = \frac{n^{2}\pi^{2}\hbar^{2}}{2mL^{2}}$

### Key Concepts

- **Quantization of Energy:** Only specific energy levels are allowed.
- **Nodes and Antinodes:** The wave function has $n-1$ nodes inside the box.

### Guidelines for Problems

- Use these equations when dealing with confined particles.
- The lowest energy (ground state) corresponds to $n = 1$.
- The energy difference between levels increases with $n$.

---

## Schrödinger Wave Equation

### General Form (Time-Independent)

$-\dfrac{\hbar^{2}}{2 m} \dfrac{d^{2} \psi(x)}{dx^{2}} + V(x) \psi(x) = E \psi(x)$

- **$\psi(x)$:** Wave function.
- **$V(x)$:** Potential energy function.
- **$E$:** Total energy of the system.

### Conceptual Significance

- **Foundation of Quantum Mechanics:** Describes how the quantum state of a physical system changes in space and time.
- **Applications:** Used to determine allowed energy levels and corresponding wave functions for quantum systems.

---

## Normalization of Wave Functions

### Concept

- **Normalization:** Ensuring the total probability of finding a particle in all space is 1.
- **Condition:** $\int\limits_{-\infty}^{\infty} |\psi(x)|^{2} dx = 1$

### Why It's Needed

- **Probability Interpretation:** The wave function's magnitude squared gives the probability density.
- **Physical Realism:** Probabilities must sum to one for a complete description.

### How to Normalize

1. **Calculate the Integral:** $\int\limits_{a}^{b} |\psi(x)|^{2}$
    - For the domain where $\psi(x)$ is non-zero.
2. **Set the Integral Equal to 1 and Solve for the Normalization Constant.**

---

## Boundary Conditions for Wave Equations

### Requirements

1. **Finite Wave Function:**
    
    - **Reason:** To avoid infinite probabilities.
    - **Application:** Ensure $\psi(x)$ is finite everywhere.
2. **Single-Valued Wave Function:**
    
    - **Reason:** [[Probability]] must be uniquely defined at each point.
    - **Application:** $\psi(x)$ cannot have multiple values at the same $x$.
3. **Continuity of Wave Function and Its Derivative:**
    
    - **Reason:** Ensures the second derivative in Schrödinger's equation is well-defined.
    - **Application:** At boundaries where potential changes, both $\psi(x)$ and $d\psi/dx$ must be continuous.
    - **Exception:** When potential is infinite, the derivative may be discontinuous.
4. **Normalization at Infinity:**
    
    - **Reason:** To ensure total [[Probability]] is finite.
    - **Application:** $\psi(x) \rightarrow 0$ as $x \rightarrow \infty$.

### Guidelines for Problems

- Apply boundary conditions when solving Schrödinger's equation.
- Use appropriate conditions based on the potential in the problem (finite or infinite).
- Remember that physical solutions must satisfy these conditions to be acceptable.