Type of [[Circuits/Operational Amplifier]] produces an (inverted) linear combination of the source voltages at the output.

![[summing_op_amp.png]]

$$v_o=-(\frac{R_f}{R_a}v_a+\frac{R_f}{R_b}v_b+\frac{R_f}{R_c}v_c)$$

This is derived from the [[Circuits/Operational Amplifier]] characteristics:
1. $v_p=v_n=0$
2. $i_a=\frac{v_a}{R_a},i_b=\frac{v_b}{R_b},i_c=\frac{v_c}{R_c}$ and $i_f=\frac{v_o}{R_f}$
3. $i_n=i_a+i_b+i_c+i_f$
4. $\frac{v_a}{R_a}+\frac{v_b}{R_b}+\frac{v_c}{R_c}+\frac{v_o}{R_f}=0$
5. $v_o=-(\frac{R_f}{R_a}v_a+\frac{R_f}{R_b}v_b+\frac{R_f}{R_c}v_c)$ which is the final equation