When voltages and currents are sinusoids, **power** will be a function of time:$$p(t)=i(t)v(t)$$
We refer to $p(t)$ as *instantaneous power*. 

Writing $i(t)$ and $v(t)$ as explicit sinusoids:
$$i(t)=I_m\cos(\omega t + \theta_i)$$
$$v(t)=V_m\cos(\omega t + \theta_v)$$
It is common to define a time reference so that the *current* has a positive maximum at $t=0$, requiring both sinusoids to be shifted by $\theta_i$:
$$i(t)=I_m\cos(\omega t)$$
$$v(t)=V_m\cos(\omega t + \theta_v-\theta_i)$$
After some trig identities, we come to a **definition for power**:
$$p(t)=\frac{I_mV_m}2\cos(\theta_v-\theta_i)+\frac{I_mV_m}2\cos(\theta_v-\theta_i)\cos(2\omega t)-\frac{I_mV_m}2\sin(\theta_v-\theta_i)\sin(2\omega t)$$
- Instantaneous power oscillates at twice the frequency of current / voltage
- Instantaneous power can be negative even though we are using passive (non-power-generating) components
- The *average value* of instantaneous power is $P=\frac{I_mV_m}{2}\cos(\theta_v-\theta_i)$
- Average power will be positive and depends not only on the peak current and voltage but also on the [[Phase Relationships]] between them

## Other Power Definitions
### Average Power (Real Power)
$$P=<p(t)>=\frac 1 T \int\limits_{t_0}^{t_0+T}p(t)dt=\frac{I_mV_m}{2}\cos(\theta_v-\theta_i)$$
- Measured in Watts
### Reactive Power 
$$Q=\frac{I_mV_M}2\sin(\theta_v-\theta_i)$$
### Instantaneous Power (Combinational Definition)
$$p(t)=P+P\cos(2\omega t)-Q\sin(2\omega t)$$

### RMS Power
$$P=I_\text{RMS}^2R=\frac{V_\text{RMS}^2}{R}$$
### Variables
- **Power Factor Angle** $\theta_v-\theta_i$
- **Power Factor** $\cos(\theta_v-\theta_i)$
- **Reactive Factor** $\sin(\theta_v-\theta_i)$
- **Lagging Power Factor** $\theta_v>\theta_i$
	- Means current lags voltage
	- $rf>0$
	- *Inductive Element*
- **Leading Power Factor** $\theta_i>\theta_v$
	- Means current leads voltage
	- $rf<0$
	- *Capacitive Element*

## Average and Reactive Power for Different Elements
### Resistors
- $\theta_v=\theta_i$
- $\cos(\theta_v-\theta_i)=1,\sin(\theta_v-\theta_i)=0$
- $P=\frac{I_mV_m} 2, Q=0$
- $p(t)=P+P\cos(2\omega t)$

### Inductors
- $\theta_v=\theta_i+90\degree$
- $\cos(\theta_v-\theta_i)=0,\sin(\theta_v-\theta_i)=1$
- $P=0,Q=\frac{I_mV_m}{2}$
- $p(t)=-\frac{I_mV_m}{2}\sin(2\omega t)$

### Capacitors
- $\theta_v=\theta_i-90\degree$
- $\cos(\theta_v-\theta_i)=0,\sin(\theta_v-\theta_i)=-1$
- $P=0,Q=-\frac{I_mV_m}{2}$
- $p(t)=+\frac{I_mV_m}{2}\sin(2\omega t)$

## Power Using [[Phasors]]
**Complex Power** (Measured in Volt-Amps)
$$S=P+jQ$$
**Apparent Power** (Measured in Volt-Amps)
$$|S|=\sqrt{P^2+Q^2}$$
![[complex_power.png]]

After some algebra magic, we can use phasors to represent:
$$S=\frac 1 2 \pmb{VI^*}$$
- Where $\pmb{I^*}$ is the conjugate of $\pmb I$

Alternatively, we can use RMS voltages and currents:
- $\pmb{V}_\text{RMS}=V_\text{RMS}e^{j\theta_v}=\frac{V_m}2e^{j\theta_v}$
- $\pmb{I}_\text{RMS}=I_\text{RMS}e^{j\theta_v}=\frac{I_m}2e^{j\theta_v}$
To get: $S=\pmb{V}_\text{RMS}\pmb{I^*}_\text{RMS}$

## Power using Impedance
For an element with impedance $Z$, the voltage and current phasors are related by: $$\pmb{V}_\text{RMS}=\pmb{I}_\text{RMS}Z$$
From this, various forms of the power expression are developed:
1. $P=|\pmb{I}_\text{RMS}|^2\Re[Z]$
2. $P=\frac{|\pmb{V}_\text{RMS}|^2\Re[Z]}{|Z|^2}$
3. $Q=|\pmb{I}_\text{RMS}|^2\Im[Z]$
4. $Q=\frac{|\pmb{V}_\text{RMS}|^2\Im[Z]}{|Z|^2}$

