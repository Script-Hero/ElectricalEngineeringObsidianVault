For [[Second Order Circuits]] that are RLC driven by sinusoidal (AC) currents, using [[Phasors]] the [[Voltage]]-[[Current]] relationship are all basically the same:
$$\pmb V = \pmb I Z$$
Where $Z$ is known as the complex impedance:
![[impedance_equations.png]]

**Cool trick for *capacitor*: $\frac 1 {j\omega C}=-j\cdot\frac 1 {\omega C}$**


We define $Z+x+jy$ as *impedance* where
- $x$ is *resistance*
- $y$ is *reactance*

We define $Y=\frac 1 Z = g+jh$ as *admittance* (reciprocal of impedance) where
- $g$ is *conductance*
- $h$ is *susceptance*

![[admittance_chart.png]]

[[Inductors]] and [[Capacitors]] have no resistive component and are called *reactive elements*. [[Inductors]] have a positive reactance while [[Capacitors]] have a negative reactance.
## Sinusoids in Resistors
1. Suppose the [[Current]] in a resistor is sinusoidal: $i(t)=I_0\cos(\omega t + \theta)$
2. Since $v(t)=R\cdot i(t)$ the [[Voltage]] will also be a sinusoid: $v(t)=RI_0\cos(\omega t + \theta)$
3. In terms of [[Phasors]], $\pmb I = I_0e^{j\theta}$ and $\pmb V = RI_0e^{j\theta}$

Therefore, [[Voltage]] and [[Current]] [[Phasors]] in a resistor are related by $\pmb V = \pmb I R$
- **That is, [[Ohm's Law]] still applies in the [[Phasors]] domain**


## Sinusoids in Inductors
1. Suppose the [[Current]] in an [[Inductors]] is sinusoidal: $i(t)=I_0\cos(\omega t + \theta)$
2. Since $v(t)=L\frac{di}{dt}$, the [[Voltage]] will be: $v(t)=-\omega L I_0\sin(\omega t + \theta)=-\omega L I_0\cos(\omega t + \theta - 90\degree)$
3. In terms of [[Phasors]]: $\pmb I = I_0e^{j\theta}$ and $\pmb V = -\omega LI_0e^{j(\theta -90\degree)}=-\omega LI_0e^{-j90\degree}e^{j\theta}=j\omega LI_0e^{j\theta}$

Therefore, [[Voltage]] and [[Current]] [[Phasors]] in an inductor are related by $$\pmb V=j\omega L \pmb I$$
- Notice that in the phasor domain, there is no longer a derivative in this relationship. It just looks like [[Ohm's Law]] where $R$ is replaced with $j\omega L$

## Sinusoids in [[Capacitors]]
1. Suppose the [[Voltage]] in a capacitor is sinusoidal: $v(t)=V_0\cos(\omega t + \theta)$
2. Since $i(t)=C\frac{dv}{dt}$, the [[Current]] will be: $i(t)=-\omega CV_0\sin(\omega t + \theta)=-\omega CV_0\cos(\omega t + \theta - 90\degree)$
3. In terms of [[Phasors]]: $\pmb V = V_0e^{j\theta}$ and $\pmb I = -\omega CV_0e^{j(\theta - 90\degree)}=-\omega CV_0e^{-j90\degree}e^{-j\theta}=j\omega C V_0e^{j\theta}$

Therefore, the [[Voltage]] and [[Current]] [[Phasors]] in a capacitor are related by $$\pmb I = j\omega C \pmb V$$ or $$\pmb V \frac {\pmb I}{j\omega C}$$
- Notice that in the phasor domain, there is no longer a derivative, it just looks like [[Ohm's Law]] with $R$ replaced by $\frac 1 {j\omega C}$

