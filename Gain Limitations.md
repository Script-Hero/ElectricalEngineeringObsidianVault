The maximum gain of an [[Electronics/Operational Amplifier|Operational Amplifier]] is limited by its internals.
- Rolls of at -20 [[Decibel]]s / decade (due to internal capacitance)
- At high enough frequencies, gain is 1 (0 dB)
	- $A(\omega =2\pi f_{t)=1}V/V$

## Open Loop Gain
Open loop gain (meaning there is no feedback circuit) resembles a first order RC circuit with a low frequency pole at $\omega=2\pi f$ and DC gain $A_v(0)=A_{0}=200,000V/V$
- First Order [[Transfer Function]] is $A_v(\omega)=\frac{A_{0}}{\frac s {\omega_b}+1}=\frac{A_0}{1+j\frac{\omega}{\omega_b}}$


