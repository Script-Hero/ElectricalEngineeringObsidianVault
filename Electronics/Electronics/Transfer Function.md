The steady state [[First Order Frequency Response]] can be written as either
- $V_o(\omega)=H(\omega)\cdot V_{in}(\omega)$
- $V_o(\omega)=|H(\omega)|e^{j\phi(\omega)}\cdot Ae^{j\omega t}$

Where:
$H(\omega)=\frac{v_{out}(\omega)}{v_{in}(\omega)}$

![[transfer_function.png]]

Additionally:
1. The **poles** of the transfer function are the *roots of the denominator*.
	1. Meaning $(p_1,p_2,\dots,p_n)$ where $|H(s)|\rightarrow\infty$
	2. **Decreases** the *magnitude* by -20dB per decade after the pole location
	3. **Decreases** the *phase* by -90$\degree$ from $\frac 1 {10}$ the pole location to 10 times the pole location
2. The **zeros** are the *roots of the numerator*
	1. Meaning $(p_1,p_2,\dots,p_n)$ where $|H(s)|\rightarrow0$
	2. **Increases** the *magnitude* of +20dB per decade after the zero location
	3. **Increases** the *phase* by 90$\degree$ from $\frac 1 {10}$ the zero location to 10 times the zero location

# Solving using Laplace ($s$ domain)
We use the $s$ domain impedance calculations:
- $Z_R$=$R$
- $Z_C=\frac{1}{sC}$
- $Z_L=sL$
*Note* that $s=j\omega$

Example:
![[transfer_function_example.png]]
1. $H(s)=\frac{V_o(s)}{V_{in}(s)}=\frac{s\frac R L}{s^2+\frac R L s + \frac 1 {LC}}=\frac{s \frac R L}{(s+p_1)(s+p_2)}$
2. Poles are $p_{1,2}=\frac 1 2 (-\frac R L \pm \sqrt{(\frac R L)^2-4\frac 1 {LC}})$
3. Zeros are $z_1=0$ and $z_2=\infty$
