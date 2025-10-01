[[Electronics/Operational Amplifier|Operational Amplifier]] that 

![[integrator_op_amp.png]]

# Time Domain
- $i_{in}=\frac{v_{in}}{R}$
- $i_C=i_{in}=C\frac{dv_C}{dt}$
- $v_o=-v_{C}=\frac 1 C\int i_{in}dt=\frac 1 {RC}\int v_{in}(t)dt$

# [[Frequency Response]]
The [[Transfer Function]] is $H(\omega)=-\frac 1 {j\omega R C}=\frac{+j}{\omega RC}$
- The magnitude response ([[Decibel]]s) changes by -20 dB as frequency increases 10 one decade (10 times)

Since the magnitude of the output voltage $v_O$ can't exceed the supply voltages , the values of $R$ and $C$ must be chosen carefully to avoid saturation.