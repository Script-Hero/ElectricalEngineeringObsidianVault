When solving for the *homogenous solution* the characteristic equation will have either:
1. **Distinct real roots:** $A_1e^{s_1t}+A_2e^{s_2t}\rightarrow\text{Overdamped Response}$
2. **Complex roots $s=\sigma\pm j\omega$:** $B_1e^{\sigma t}\cos(\omega t)+B_2e^{\sigma t}\sin(\omega t)\rightarrow\text{Underdamped Response}$
3. **Repeated real roots:** $C_1e^{s_0t}+C_2te^{s_0t}\rightarrow\text{Critically Damped Response}$

![[damping_graph.png]]
1. **Overdamped**: relatively slow to reach steady state value.
2. **Underdamped**: reacts to change in input quickly, but response "rings" (oscillates / bounces)
3. **Critically Damped**: quickest approach to steady state values without overshoot

## Example
![[parallel_rlc_circuit.png]]

*First, imagine that $R=\infty$* (pretend the resistor doesn't exist basically) This circuit is an example of a "simple harmonic oscillator" (like an ideal spring from physics class)
- **Differential Equation**: $\frac{d^2}{dt^2}+\frac{y(t)}{LC}=0$
- **Characteristic Equation**: $s^2+\frac 1 {LC}=0$
- **Roots**: $s=\pm j\sqrt{\frac 1 {LC}}$
- **Behavior**: $B_1\cos(\omega_0t)+B_2\sin(\omega_0t)$
	- Purely sinusoidal response (no damping)
- **Natural Resonant Frequency**: $\omega_0=\sqrt\frac{1}{LC}$

**As we add resistance to the circuit, the response becomes a *damped oscillation***
- **Differential Equation**: $\frac{d^2y}{dt^2}+\frac 1{RC}\frac{dy}{dt}+\frac{y(t)}{LC}=0$
- **Characteristic Equation**: $s^2+\frac 1 {RC}s + \frac 1 {LC}=0$
- **Roots**: $s=-\frac 1 {2RC}\pm j\sqrt{\frac 1 {LC} - (\frac 1 {2RC})^2}$
- **Damped Resonant Frequency**: $\omega_d =\sqrt{\omega_o^2-(\frac 1 {2RC})^2}$

## Q-Factor
The *Q-Factor* measures how underdamped or overdamped a second-order system is.
![[q_factor.png]]
For a series RLC circuit:
- **Differential Equation**: $\frac{d^2y}{dt^2}+\frac R L \frac{dy}{dt}+\frac{y(t)}{LC}=0$
- **Characteristic Equation**: $s^2 + \frac R L s + \frac 1 {LC} = 0$
- **Roots**: $s=-\frac R {2L} \pm \sqrt{(\frac R {2L})^2 - \frac 1 {LC}}$
- **Q-Factor**: $Q=\frac 1 R \sqrt{\frac L C}$
	- **Roots**: $s=\frac{\omega_o}{2Q}(-1\pm\sqrt{1-(2Q)^2}$

 *Critically Damped:* $Q=\frac 1 2$ 
 *Underdamped:* $Q>\frac 1 2$
	 $\omega_d=\omega_o\sqrt{1-(\frac 1 {2Q})^2}$
 *Overdamped:* $Q<\frac 1 2$

For a parallel RLC circuit: $Q=R\sqrt\frac C L$
