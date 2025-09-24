[[First Order Circuits]] with *Alternating Current*, meaning that [[Voltage]] is sinusoidal:
$$v_\text{in}=A\cos(\omega t+\theta)$$
Where:
- $A$ is amplitude
- $\omega$ is frequency in *radians per second*
- $\theta$ is phase 

## Example (Series RC Circuit)
![[Pasted image 20250325002733.png]]
This circuit is described by $$RC\frac{dv_o}{dt}+v_o(t)=v_\text{in}(t)$$
1. The *homogenous solution* is $v_h(t)=Be^{-t/RC}$
2. The *particular solution* is found by using the method of undetermined coefficients
	1. Assume particular solution in the form $v_p(t)=D\cos(\omega t + \theta) + E\sin(\omega t + \theta)$
	2. $\frac{dv_p}{dt}=\omega E \cos(\omega t + \theta) - \omega D \sin(\omega t + \theta)$
	3. Plugging these into the original differential equation $\omega R C E\cos(\omega t + \theta) - \omega R C D\sin(\omega t + \theta) + D \cos(\omega t + \theta) + E \sin(\omega t + \theta) = A \cos(\omega t + \theta)$
	4. You can equate the $\sin$ and $\cos$ coefficients into a set of linear equations:
		1. $\omega R C E + D = A$
		2. $-\omega RCD + E = 0$
3. $v_o(t)=v_h(t)+v_p(t)$
4. $v_o(t)=Be^{-\frac{t}{RC}}+\frac{A\cos(\omega t + \theta)}{1+(\omega RC)^2}+\frac{A\omega RC\sin(\omega t + \theta)}{1 + (\omega RC)^2}$
	1. Using trig identities this can be rewritten as $v_o(t)=Be^{-\frac{t}{RC}}+\frac{A\cos(\omega t + \theta - \tan^{-1}\omega RC)}{\sqrt{1+(\omega RC)^2}}$

The *homogenous solution* is the transient (temporary) part of the solution, while the *particular solution* is the steady state output (as $t\rightarrow\infty$)

### Some interesting things to note from this solution:
1. The amplitude of the output has been scaled by a factor of $\frac{1}{\sqrt{1+(\omega RC)^2}}$. This is known as the *magnitude response* of the circuit 
2. The phase of the output has been shifted by $-\tan^-1(\omega RC)$ radians. This is known as the *phase response* of the circuit

So for low frequency inputs, $\omega\ll1/RC$ so that the *magnitude response* $\approx1$ and the *phase response* $\approx0$ and for high frequency inputs $\omega\gg1/RC$ the *magnitude response* $\approx0$ and the *phase response* $\approx-\frac{\pi}{2}$.

Therefore this circuit is known as a **low-pass filter** because it allows low frequencies to pass but attenuates high frequencies. 