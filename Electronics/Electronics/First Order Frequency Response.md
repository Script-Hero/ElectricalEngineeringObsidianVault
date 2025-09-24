Consider the following circuit if $V_\text{in}(t)=A\cos(\omega t + \phi)$
![[example_rc.png]]

**First, derive the output voltage $v_C(t)$**
1. $v_{R}(t)+v_C(t)=v_\text{in}(t)$
	1. "Loop rule" / KVL
	2. We know that $v_R(t)=i(t)\cdot R$
2. $RC\frac{dv_C}{dt}+v_C(t)=v_\text{in}(t)=A\cos(\omega t + \phi)$

**Next, solve with differential equation techniques.**
$v_o(t)=V_c(t)=Be^{-\frac{t}{RC}}+\frac{A}{\sqrt{1+(\omega R C)^2}}\cos(\omega t + \phi-\arctan(\omega RC)$
- The first term ($Be^{-\frac{t}{RC}}$) is the *transient response*
	- Meaning it goes to $0$ as $t\rightarrow\infty$
- The second term is the *sinusoidal **steady state output*** or *frequency response*
	- Same frequency as the input
	- Amplitude is scaled by a factor of $\frac 1 {\sqrt{1+(\omega RC)^2}}$
	- Phase has been shifted by $-\arctan(\omega RC)$

To study the **frequency response** of an AC circuit, we use the [[Transfer Function]]