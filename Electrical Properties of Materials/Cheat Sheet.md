# QUIZ CHEAT SHEET (Merged — everything in one place)

> Conventions: SI units unless otherwise stated. Inline math uses $\dots$. [[Vectors]] in **bold** when helpful; magnitudes usually implied. Effective mass $m^\ast$. Elementary charge magnitude $e$ (use $q=\pm e$ for sign).

---

## Physical constants (memorize)

- $e=1.602\times10^{-19}\ \mathrm{C}$ (elementary charge)  
- $m_0=9.11\times10^{-31}\ \mathrm{kg}$ (electron rest mass)  
- $\varepsilon_0=8.854\times10^{-12}\ \mathrm{F\,m^{-1}}$ (vacuum permittivity)  
- $c=2.998\times10^{8}\ \mathrm{m\,s^{-1}}$ (speed of light)  
- $N_A=6.022\times10^{23}\ \mathrm{mol^{-1}}$ (Avogadro)  
- Magnetic flux density: $1\ \mathrm{T}=1\ \mathrm{Wb\,m^{-2}}$  
- Weber: $1\ \mathrm{Wb}=1\ \mathrm{V\,s}$

---

## Core transport relations (Drude model & device-level)

### Field, current, conductivity, resistivity
- **Local Ohm’s law:** $\mathbf{J}=\sigma\,\mathbf{E}$  
  where $\mathbf{J}\,[\mathrm{A\,m^{-2}}]$, $\sigma\,[\mathrm{S\,m^{-1}}]$, $\mathbf{E}\,[\mathrm{V\,m^{-1}}]$.
- **Resistivity:** $\rho=1/\sigma$ with $\rho\,[\Omega\cdot\mathrm{m}]$.
- **Macroscopic resistance of a bar:** $R=\rho\,\dfrac{L}{A}$  
  $R\,[\Omega],\ L\,[\mathrm{m}],\ A\,[\mathrm{m^2}]$.
- **Cross-sectional area (rectangular):** $A=w\,t$ with width $w$, thickness $t$.
- **Current density from geometry:** $J=I/A=I/(w\,t)$.
- **Uniform field in a bar:** $E=V/L$ (if potential drops linearly).

### Microscopic relations (Drude)
- **Drift velocity:** $v_d=\mu\,E$ with $v_d\,[\mathrm{m\,s^{-1}}]$.
- **Current density from drift:** $J=n\,q\,v_d$ (equivalently $J=\sigma E$ after substitutions).
- **Conductivity (one carrier type):** $\sigma=n\,q\,\mu$.
- **Mobility–scattering link:** $\mu=\dfrac{q\,\tau}{m^\ast}\ \Rightarrow\ \tau=\dfrac{\mu\,m^\ast}{q}$  
  $\tau\,[\mathrm{s}]$ = collision/relaxation time.
- **Drude combined:** $\sigma=\dfrac{n\,q^2\,\tau}{m^\ast}$.
- **Mean free path:** $\ell=v\,\tau$ (pick appropriate speed $v$: thermal/Fermi for order‐of‐magnitude; drift is usually tiny).

### Two–carrier (semiconductor) conductivity
- **General:** $\sigma=e\,(n_e\mu_e+n_h\mu_h)$.  
  Here $n_e,n_h\,[\mathrm{m^{-3}}]$, $\mu_e,\mu_h\,[\mathrm{m^2\,V^{-1}\,s^{-1}}]$.
- **Solving when the mobility ratio is given:**  
  Let $r=\mu_e/\mu_h$. Then  
  $\dfrac{\sigma}{e}=n_e\mu_e+n_h\mu_h=\mu_h(r n_e+n_h)$  
  $\Rightarrow\ \mu_h=\dfrac{\sigma}{e(r n_e+n_h)},\ \ \mu_e=r\,\mu_h$.

### Getting $n$ from $\rho$ & $\mu$ (electron-dominated)
- If only electrons conduct appreciably:  
  $\boxed{n=\dfrac{1}{\rho\,e\,\mu_e}}$.

---

## Hall effect (slab of thickness $t$, current along $x$, $B=B_z\hat{\mathbf{z}}$)

- **Hall coefficient:**  
  $R_H=\dfrac{E_y}{J_x B_z}=\dfrac{1}{n\,q}$  
  Units: $\mathrm{m^3\,C^{-1}}$. Sign identifies carrier type (negative for electrons).
- **Hall voltage across width (a.k.a. transverse/Hall voltage):**  
  $U_y=V_H=R_H\,\dfrac{I_x\,B_z}{t}=\dfrac{B_z\,I_x}{n\,q\,t}$.
- **Useful algebraic solves:**  
  $n=\dfrac{B\,I}{|q|\,t\,|V_H|}$, \quad  
  $B=\dfrac{|V_H|\,t}{|R_H|\,I}$, \quad  
  $R_H=-\dfrac{1}{n e}$ (for electrons; the minus is sign info).

---

## Cyclotron resonance (effective mass via EM resonance)

- **Cyclotron frequency:** $\omega_c=\dfrac{|q|\,B}{m^\ast}$.
- **Resonance condition:** EM wave with $\omega$ drives resonance when $\omega=\omega_c\Rightarrow m^\ast=\dfrac{|q|\,B}{\omega}$.
- **Frequency/wavelength:** $\omega=2\pi f=\dfrac{2\pi c}{\lambda}$.
- **Mobility from scattering time:** $\mu=\dfrac{q\,\tau}{m^\ast}$.
- **Resonance sharpness criterion:** $\omega_c\tau\gg1$ (narrow line). If $\omega_c\tau\lesssim1$, broad/weak resonance.

---

## Free-electron plasma / optics (metals) — optional but handy

- **Plasma frequency from transparency/cutoff wavelength** $\lambda_c$:  
  $\omega_p=\dfrac{2\pi c}{\lambda_c}$.
- **Drude plasma relation:** $\omega_p^2=\dfrac{n e^2}{\varepsilon_0 m^\ast}\Rightarrow m^\ast=\dfrac{n e^2}{\varepsilon_0 \omega_p^2}$.

---

## Metal electron density & electrons per atom

- **Atoms per cubic meter:**  
  $n_{\text{atom}}=\dfrac{\rho_m\,N_A}{M}$  
  where $\rho_m\,[\mathrm{kg\,m^{-3}}]$ (mass density), $M\,[\mathrm{kg\,mol^{-1}}]$ (molar mass).
- **Conduction electrons per atom:**  
  $z=\dfrac{n}{n_{\text{atom}}}$.
- **Forward use (if $z$ is known or assumed):**  
  $n=\left(\dfrac{\rho_m\,N_A}{M}\right)z$.
- **Back-solve (if you measured $n$ e.g. via Hall):**  
  $z=\dfrac{n\,M}{\rho_m\,N_A}$.

---

## Electron waves & microscopy

- **De Broglie wavelength:** $\lambda=\dfrac{h}{p}$.
- **Nonrelativistic kinetic energy relation:** $E=\dfrac{p^2}{2m}\Rightarrow \lambda=\dfrac{h}{\sqrt{2mE}}$.
- **Electrons accelerated through $V$ volts:**  
  $E=eV\Rightarrow \lambda=\dfrac{h}{\sqrt{2 m_e e V}}$.  
  (For tens of kV, relativistic correction is better; above formula is the common first approximation.)
- **Diffraction-limited “best-case” resolution:** $d_{\min}\sim\dfrac{\lambda}{2}$.
- **Real TEM/SEM limiters (qualitative):** energy spread of electrons, lens aberrations (spherical & chromatic), and mechanical/electrical/vacuum stability.

---

## Geometry & consistency identities (bars/slabs)

- $\rho=\dfrac{R\,A}{L}=\dfrac{R\,w\,t}{L}$, \quad $\sigma=\dfrac{L}{R\,A}$.  
- $J=\dfrac{I}{A}=\dfrac{I}{w\,t}$, \quad $E=\dfrac{V}{L}$.  
- Consistency check for a sample: confirm $J\approx\sigma E$ from independent $I,V,w,t,L$.

---

## Unit conversions & quick numbers (all used in examples)

- $1\ \mathrm{S\,m^{-1}}=10^{-2}\ \Omega^{-1}\mathrm{\,cm^{-1}}$, \quad $1\ \Omega^{-1}\mathrm{\,cm^{-1}}=100\ \mathrm{S\,m^{-1}}$.  
- $1\ \mathrm{T}=10^{4}\ \mathrm{Gauss}$ (so $1000\ \mathrm{G}=0.1\ \mathrm{T}$).  
- $1\ \mathrm{Wb}=\mathrm{V\cdot s}$.  
- $1\ \mathrm{cm}^{-3}=10^{6}\ \mathrm{m}^{-3}$.  
- $1\ \mathrm{cm}^2\ \mathrm{V^{-1}\ s^{-1}}=10^{-4}\ \mathrm{m}^2\ \mathrm{V^{-1}\ s^{-1}}$.  
- Lengths: $100\,\mu\mathrm{m}=1.0\times10^{-4}\ \mathrm{m}$, $10\,\mu\mathrm{m}=1.0\times10^{-5}\ \mathrm{m}$, $2\,\mu\mathrm{m}=2.0\times10^{-6}\ \mathrm{m}$.

---

## Ready-to-use templates (from homework & example problems)

### Template A — From resistivity & mobility to density, then Hall field
**Given:** $\rho,\ \mu_e,\ V_H,\ I,\ t$ (electron-dominated)  
1. $n=\dfrac{1}{\rho e \mu_e}$.  
2. $R_H=-\dfrac{1}{n e}$.  
3. $B=\dfrac{|V_H|\,t}{|R_H|\,I}$ (or solve any of $n,B,V_H$ from the Hall equation $V_H=R_H I B/t$).

### Template B — Two-carrier mobility extraction
**Given:** $\sigma,\ n_e,\ n_h,\ r=\mu_e/\mu_h$  
- $\mu_h=\dfrac{\sigma}{e(r n_e+n_h)}$, \quad $\mu_e=r\,\mu_h$.

### Template C — Cyclotron effective mass
**Given:** resonance wavelength $\lambda$ and field $B$  
- $\omega=\dfrac{2\pi c}{\lambda}$, \quad $m^\ast=\dfrac{e B}{\omega}$.  
- If $\tau$ known: $\mu=\dfrac{e \tau}{m^\ast}$.  
- Check $\omega\tau\gg1$ for sharp resonance.

### Template D — Metal “electrons per atom”
**Given:** Hall $n$, density $\rho_m$, molar mass $M$  
- $z=\dfrac{n\,M}{\rho_m\,N_A}$.

### Template E — Resistor bar sanity chain
**Given:** $V,\ I,\ L,\ w,\ t$  
- $R=V/I$, $A=w t$, $J=I/A$, $E=V/L$, $\rho=R A/L$, $\sigma=1/\rho$, check $J\overset{?}{=}\sigma E$.

### Template F — Copper-like metal pipeline
**Given:** $\sigma,\ \rho_m,\ M,\ z,\ m^\ast$ (assume $z$ conduction $e^-$ per atom)  
- $n=(\rho_m N_A/M)z\ \Rightarrow\ \mu=\dfrac{\sigma}{n e}\ \Rightarrow\ \tau=\dfrac{\mu m^\ast}{e}\ \Rightarrow\ v_d=\mu E\ \Rightarrow\ J=\sigma E$.

### Template G — Intrinsic Si slab (two-carrier)
**Given:** $n,\ p,\ \mu_e,\ \mu_h,\ L,w,t$  
- $\sigma=e(n\mu_e+p\mu_h)\ \Rightarrow\ \rho=1/\sigma\ \Rightarrow\ R=\rho\,\dfrac{L}{w t}$.  
- **Units note (if using cm-based data):** $n,p$ in $\mathrm{cm^{-3}}$, $\mu$ in $\mathrm{cm^2/V\,s}$ yield $\sigma$ in $\Omega^{-1}\mathrm{\,cm^{-1}}$. Convert to SI if needed by $1\ \Omega^{-1}\mathrm{\,cm^{-1}}=100\ \mathrm{S/m}$.

---

## Variable glossary (with units)

- $\mathbf{E}\,[\mathrm{V/m}]$ electric field; $V\,[\mathrm{V}]$ voltage; $L\,[\mathrm{m}]$ length.  
- $\mathbf{J}\,[\mathrm{A/m^2}]$ current density; $I\,[\mathrm{A}]$ current; $A=w t\,[\mathrm{m^2}]$ cross-section.  
- $\sigma\,[\mathrm{S/m}]$ conductivity; $\rho\,[\Omega\cdot\mathrm{m}]$ resistivity; $R\,[\Omega]$ resistance.  
- $n\,[\mathrm{m^{-3}}]$ electron concentration; $p\,[\mathrm{m^{-3}}]$ hole concentration.  
- $\mu_e,\mu_h\,[\mathrm{m^2/V\,s}]$ electron/hole mobilities; $\mu$ generic mobility.  
- $q=\pm e\,[\mathrm{C}]$ carrier charge; $e$ is positive constant $1.602\times10^{-19}\ \mathrm{C}$.  
- $\tau\,[\mathrm{s}]$ collision (relaxation) time; $m^\ast\,[\mathrm{kg}]$ effective mass.  
- $v_d\,[\mathrm{m/s}]$ drift velocity; $\ell\,[\mathrm{m}]$ mean free path ($\ell=v\tau$).  
- $B\,[\mathrm{T}]$ magnetic flux density; $R_H\,[\mathrm{m^3/C}]$ Hall coefficient; $V_H=U_y\,[\mathrm{V}]$ Hall voltage.  
- $t\,[\mathrm{m}]$ sample thickness (direction of Hall voltage separation).  
- $\rho_m\,[\mathrm{kg/m^3}]$ mass density; $M\,[\mathrm{kg/mol}]$ molar mass; $z$ electrons per atom.  
- $\lambda\,[\mathrm{m}]$ wavelength; $\omega\,[\mathrm{s^{-1}}]$ angular frequency; $f\,[\mathrm{Hz}]$.  
- $\omega_p\,[\mathrm{s^{-1}}]$ plasma frequency.  
- $\lambda_{\mathrm{dB}}$ de Broglie wavelength (often just $\lambda$ in notes).  
- $d_{\min}$ diffraction-limited resolution scale $\sim\lambda/2$.

---

### Quick cross-check table (relationships at a glance)

- $J\leftrightarrow I$ via $J=I/A$.  
- $E\leftrightarrow V$ via $E=V/L$.  
- $J,E$ via $J=\sigma E$.  
- $\sigma$ via carriers: $\sigma=n q \mu=\dfrac{n q^2 \tau}{m^\ast}$.  
- $\mu$ via scattering: $\mu=q \tau/m^\ast$.  
- **Hall:** $R_H=1/(n q)$, $V_H=R_H I B/t$.  
- **Cyclotron:** $\omega_c=|q|B/m^\ast$, $m^\ast=|q|B/\omega$, $\omega=2\pi c/\lambda$.  
- **Plasma:** $\omega_p^2=n e^2/(\varepsilon_0 m^\ast)$.  
- **Electrons per atom:** $z=n/(\rho_m N_A/M)$.

---

## Common pitfalls & reminders (from worked solutions)

- Always track **signs** in Hall measurements: $R_H<0$ for electrons, $>0$ for holes. For many “numerical” questions the **magnitude** is used, but remember what the sign means.
- Keep **units consistent**: if densities and mobilities are in $\mathrm{cm^{-3}}$ and $\mathrm{cm^2/V\,s}$, your $\sigma$ naturally comes out in $\Omega^{-1}\mathrm{\,cm^{-1}}$. Convert to SI at the end if needed.
- When combining relations, it’s often faster to use the **template chains** above rather than starting from scratch (especially for $n$, $B$, $V_H$, and $m^\ast$ problems).
- **Mean free path** uses a **physical speed** (thermal/Fermi), **not** drift speed, unless the problem explicitly wants $v_d\tau$.

---

## Extra unit sanity (again—because mistakes here cost points)

- $1\ \mathrm{S/m}=10^{-2}\ \Omega^{-1}\mathrm{\,cm^{-1}}$.  
- $1\ \Omega^{-1}\mathrm{\,cm^{-1}}=100\ \mathrm{S/m}$.  
- $1\ \mathrm{T}=10^{4}\ \mathrm{G}$.  
- $1\ \mathrm{cm}^{-3}=10^{6}\ \mathrm{m}^{-3}$.  
- $1\ \mathrm{cm}^2/\mathrm{V\,s}=10^{-4}\ \mathrm{m}^2/\mathrm{V\,s}$.  
- $100\,\mu\mathrm{m}=10^{-4}\ \mathrm{m},\ 10\,\mu\mathrm{m}=10^{-5}\ \mathrm{m},\ 2\,\mu\mathrm{m}=2\times10^{-6}\ \mathrm{m}$.

---

### Micro “worked-example” skeletons (plug values quickly)

- **Bar sample:**  
  $R=V/I;\ A=w t;\ J=I/A;\ E=V/L;\ \rho=R A/L;\ \sigma=1/\rho;\ \text{check }J\overset{?}{=}\sigma E$.

- **Metal (Cu/Na-like):**  
  $n=(\rho_m N_A/M)z\ \to\ \mu=\sigma/(n e)\ \to\ \tau=\mu m^\ast/e\ \to\ v_d=\mu E\ \to\ J=\sigma E$.

- **Intrinsic Si slab:**  
  $\sigma=e(n\mu_e+p\mu_h)\ \to\ \rho=1/\sigma\ \to\ R=\rho L/(w t)$ (convert units if given in cm).

- **Hall (electrons):**  
  $R_H=-1/(n e),\ \ V_H=R_H I B/t$.  
  If you know $\rho$ and $\mu_e$ instead, first use $n=1/(\rho e \mu_e)$.
