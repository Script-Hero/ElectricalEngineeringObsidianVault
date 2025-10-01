An [[Circuits/Operational Amplifier]] configuration that produces an output which is a linear combination (with opposite signs, meaning one is being subtracted from the other) of two input signals.

![[difference_amplifier.png]]

$$v_o=\frac{(R_f+R_a)R_g}{(R_g+R_b)R_a}v_b-\frac{R_f}{R_a}v_a$$

Derived from [[Circuits/Operational Amplifier]] characteristics:
1. $v_p=v_b\frac{R_g}{R_g+R_b}$
2. $v_n=v_p=v_b\frac{R_g}{R_g+R_b}$
3. $i_s=\frac{v_a-v_n}{R_s},i_f=\frac{v_o-v_n}{R_f}$
4. $i_n=i_s+i_f=0$
5. $\frac{v_a-v_n}{R_a}+\frac{v_o-v_n}{R_f}=0$
6. $v_o=\frac{(R_f+R_a)R_g}{(R_g+R_b)R_a}v_b-\frac{R_f}{R_a}v_a$

