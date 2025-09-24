Illustrates frequency response of circuits by plotting $\omega$ in a logarithmic scale on the x-axis and either $A$ or $\phi$ on the y-axis.
![[bode_plot_example.png]]
For magnitude:
$|H(j\omega)|^2=10\log_10|H(j\omega)|$ [[Decibel]]s

For phase:
$\angle [H(j\omega)]=\arctan(\frac{\Im[H(j\omega)]}{\Re[H(j\omega)]})\degree$

# Finding [[Transfer Function]]
1. The **poles** of the [[Transfer Function]] are the *roots of the denominator*.
	1. Meaning $(p_1,p_2,\dots,p_n)$ where $|H(s)|\rightarrow\infty$
	2. **Decreases** the *magnitude* by -20dB per decade after the pole location
	3. **Decreases** the *phase* by -90$\degree$ from $\frac 1 {10}$ the pole location to 10 times the pole location
2. The **zeros** of the [[Transfer Function]] are the *roots of the numerator*
	1. Meaning $(p_1,p_2,\dots,p_n)$ where $|H(s)|\rightarrow0$
	2. **Increases** the *magnitude* of +20dB per decade after the zero location
	3. **Increases** the *phase* by 90$\degree$ from $\frac 1 {10}$ the zero location to 10 times the zero location

	 