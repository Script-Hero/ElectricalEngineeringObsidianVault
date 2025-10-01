Type of [[Circuits/Operational Amplifier]] that produces an output which is a *positive* multiple of the input signal (as opposed to the [[Inverting Amplifier]])

![[non_inverting_op_amp.png]]

$$v_o=\frac{R_f+R_s}{R_s}v_g$$
- Or I guess $V_o=(1+\frac{R_f}{R_s})v_g$

Derived from [[Circuits/Operational Amplifier]] characteristics:
1. $i_g=0, v_p=v_g$
2. $v_p=v_n=v_g$
3. $i_s=-\frac{v_g}{R_s},i_f=\frac{v_o-v_g}{R_f}$
4. $i_n=i_s+i_f=0$
5. $-\frac{v_g}{R_s}+\frac{v_o-v_g}{R_f}=0$
6. $v_o=\frac{R_f+R_s}{R_s}v_g$ which is the final relationship