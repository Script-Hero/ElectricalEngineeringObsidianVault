A sinusoidal [[Voltage]] signal has the general form (*polar*):
$$v(t)=V_o\cos(\omega t+\theta)$$
And is described by the parameters:
1. $V_o$ is *amplitude* in volts
2. $\theta$ is *phase* in radians or degrees
3. $\omega$ is *frequency* in radians per second (or $f=\frac \omega {2\pi}=$ frequency in Hz (cycles per second))
	1. $f=\frac 1 {T_o}$
	2. $\omega=2\pi f$


Note that $\cos(\theta)=\sin(\theta +90\degree)$


To convert from the *polar* form to *cartesian*:
$$v(t)=A_o\cos(\omega t) - B_o\sin(\omega t)$$
Where:
- $A_o=V_o\cos(\theta)$
- $B_o=V_o\sin(\theta)$


Alternative for *cartesian* to *polar*:
1. $x=r\cos(\theta)$
2. $y=r\sin(\theta)$
3. $\pmb Z = x + jy$


To convert from *cartesian* back to *polar*:
$$V_o=\sqrt{A_o^2+B_o^2}$$
and
$$\theta=\tan^{-1}(\frac{B_o}{A_o})$$
## Root Mean Squared
$$V_\text{RMS}=\sqrt{<v^2(t)>}$$
Where the brackets represent a time average:
$$<x(t)>=\frac 1 {T_o} \int\limits_{t_o}^{t_o+T_o}x(t)dt$$
- Where $T_o$ is the period and $t_o$ is any convenient starting point

For a *sinusoidal waveform* the *RMS* amplitude is $V_\text{RMS}=\frac{V_o} {\sqrt{2}}$
- Does not hold true for non-sinusoidal signals


## Phasors
Representing *sinusoidal waveforms* in terms of [[Complex Numbers]] greatly simplifies circuit analysis.

Recall:
- $\cos(\theta) = \Re[e^{j\theta}]$
- $\sin(\theta)=\Im[e^{j\theta}]$

We can represent voltage with phasors:
$$v(t)=\Re[Ve^{j\omega t}]$$ 
- Where $v(t)$ is the *sinusoidal signal* and $V$ is the *phasor*

### Combining waveforms
Consider $v(t)=V_1\cos(\omega t + \theta_1) + V_2\cos(\omega t + \theta_2)$
- The resulting waveform will be a sinusoid of the same frequency: $v(t)=V_0\cos(\omega t + \theta_0)$
- We can **easily** combine these two in phasor form: $V_0e^{j\theta_0}=V_1e^{j\theta_1}+V_2e^{j\theta_2}$ 

