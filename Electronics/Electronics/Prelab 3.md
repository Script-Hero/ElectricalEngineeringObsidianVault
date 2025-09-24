# Inverting Amplifier

Neil Aylor 632007322
1. $V_\text{Inverting}=0=V_\text{Noninverting}$
2. Using KCL:
	1. $\frac{V_{In}-V_\text{Inverting}}{R_1}+\frac{V_{o1}-V_\text{Inverting}}{R_2}=0$
	2. $\frac{V_i}{R_1}+\frac{V_{o1}}{R_2}=0$
	3. $\frac{V_{o1}}{V_i}=-\frac{R_2}{R_1}$
**Voltage gain is:** $\frac{V_{o1}}{V_i}=-\frac{R_2}{R_1}$

# Noninverting Amplifier

Neil Aylor 632007322
1. $V_\text{Inverting}=V_\text{Noninverting}=V_\text{i}$
2. Using KCL:
	1. $\frac{V_\text{Inverting}-0}{R_3}+\frac{V_\text{Inverting}-V_{o2}}{R_4}=0$
	2. $\frac{V_i}{R_3}+\frac{V_i-V_\text{o2}}{R_4}=0$
	3. $\frac{V_{o2}}{V_i}=1+\frac{R_4}{R_3}$
**Voltage gain is:** $\frac{V_{o2}}{V_i}=1+\frac{R_4}{R_3}$

# Voltage Follower

Neil Aylor 632007322
1. $V_\text{Inverting}=V_\text{Noninverting}=V_\text{i}$
2. $V_\text{Inverting}=V_o$
3. So $V_i=V_o$
**Voltage gain is:** $\frac{V_o}{V_i}=1$


# Finding question 2 information:

.


Neil Aylor 632007322
For the inverting op-amp:
1. We found earlier $\frac{V_{o1}}{V_i}=-\frac{R_2}{R_1}$
2. Given $\frac{V_{o1}}{V_i}=-2.5$ and $R_1=5.6$k$\Omega$
3. $-2.5=\frac{R_2}{5.6k\Omega}$
4. $R_2=14.0\text{k}\Omega$

For the non-inverting op-amp:
1. We found earlier $\frac{V_{o2}}{V_i}=1+\frac{R_4}{R_3}$
2. Given $\frac{V_{o2}}{V_i}=7.5$ and $R_3=5.6$k$\Omega$
3. $7.5=\frac{R_4}{5.6k\Omega}+1$
4. $R_4=36.4\text{k}\Omega$
