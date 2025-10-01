We often use [[Circuits/Operational Amplifier]]s to get the same effect as [[Inductors]] because [[Inductors]] are difficult to integrate onto an IC.

## Example
![[second_order_op_amp_example.png]]

Let's look at stage 1 first:
![[second_order_op_amp_stage_1.png]]
We get the following 2 equations
1. $\frac{V_{in}}{R_1}+C_1\frac{dV_A}{dt}+\frac{V_A}{R_2}=0$
2. $\frac{dV_A}{dt}+\frac{V_A}{R_2C_1}=-\frac{V_{in}}{R_1C_1}$

For the second stage:
![[second_order_op_amp_stage_2.png]]
We get the equation: $\frac{dV_\text{out}}{dt}+\frac{V_\text{out}}{R_4C_2}=-\frac{V_A}{R_3C_2}$

**Putting both stages together together:**

Substituting the equation from *stage 2* into the equation from *stage 1* we get:
$$\frac d {dt}(R_3C_2\frac{dV_\text{out}}{dt}+\frac{R_3V_\text{out}}{R_4})-\frac{R_3V_\text{out}}{R_2C_1}(\frac{dV_\text{out}}{dt}+\frac{V_\text{out}}{R_4C_2})=-\frac{V_\text{in}}{R_1C_1}$$

After a little cleaning up, the differential equation describing this circuit is:
$$\frac{d^2V_\text{out}}{dt^2}+(\frac1 {R_2C_1}+\frac 1 {R_4C_2})\frac{dV_\text{out}}{dt}+\frac{V_\text{out}}{R_2R_4C_1C_2}=\frac{V_\text{in}}{R_1R_3C_1C_2}$$
The associated characteristic equation is:
$$s^2+(\frac 1 {R_2C_1}+\frac 1 {R_4C_2})s+\frac{1}{R_2R_4C_1C_2}=0$$
The equation factors as
$$(s+\frac 1 {R_2C_1})(s+\frac 1 {R_4C_2})=0$$
Which has *real [[Electronics]]ot]]s* and means this circuit could produce either an *overdamped response* or possibly a *critically damped* response.

## Sallen-Key Circuit
![[sallen_key_circuit.png]]
The *Sallen-Key Circuit* can synthesize any [[Second Order Circuits]] provided the appropriate selection of component values.

To analyze, we do [[KCL]] at nodes marked with the green dot. 
1. $\frac{V_\text{in}-V_1}{R_1}+\frac{V_o-V_1}{R_2}+C_1\frac{d(V_o-V_1)}{dt}=0$
2. $\frac{V_o-V_1}{R_2}+C_2\frac{dV_o}{dv}=0$

Using equation 2, we solve for $V_1$ as:
$$V_1=V_o+R_2C_2\frac{dV_o}{dt}$$
Then, substitute this into equation 1, resulting in a single equation involving $V_o$ and $V_\text{in}$:
$$\frac{V_\text{in}-(V_o+R_2C_2\frac{dV_o}{dt})}{R_1}+\frac{V_o-(V_o+R_2C_2\frac{dV_o}{dt})}{R_2}+C_1\frac{d(V_o-(V_o+R_2C_2\frac{dV_o}{dt}))}{dt}=0$$
After cleaning up, this simplifies to:
$$\frac{d^2V_o}{dt^2}+(\frac 1 {R_1C_1} + \frac 1 {R_2C_2})\frac{dV_o}{dt}+\frac{V_o}{R_1C_1R_2C_2}=\frac{V_\text{in}}{R_1C_1R_2C_2}$$
The **characteristic equation** is:
$$s^2+(\frac 1 {R_1C_1}+\frac 1 {R_2C_1})s+\frac 1 {R_1C_1R_2C_2}=0$$
The roots are:
$$s=-(\frac 1 {2R_1C_1}+\frac 1 {2R_2C-1})\pm \sqrt{(\frac 1 {2R_1C_1}+\frac 1 {2R_2C_1})^2-\frac 1 {R_1C_1R_2C_2}}$$

By appropriate selection of component values, we can make the roots:
1. $\text{Real}\rightarrow\text{Overdamped}$
2. $\text{Complex}\rightarrow\text{Underdamped}$
3. $\text{Repeated}\rightarrow\text{Underdamped}$

**Additional Context:**
1. Natural resonant frequency: $\omega_o=\sqrt{\frac 1 {R_1C_1R_2C_2}}$
2. Damped resonant frequency: $\omega_d=\sqrt{\omega_o^2-(\frac 1 {2R_1C_1}+\frac 1 {2R_2C_1})^2}$
3. Q-Factor: $Q=\sqrt{\frac{R_1R_2C_1}{(R_1+R_2)^2C_2}}$
4. Roots: $s=\frac{\omega_0}{2Q}(-1\pm\sqrt{1-(2Q)^2}$
	1. $Q=\frac 1 2 \leftarrow\text{Critically Damped}$
	2. $Q>\frac 1 2 \leftarrow\text{Underdamped}$
	3. $Q < \frac 1 2 \leftarrow \text{Overdamped}$
*Note:*
If we define $R_s=R_1+R_2$ (series combination) and $R_p=\frac{R_1R_2}{R_1+R_2}$ (parallel combination) then the *Q-factor* can be written more conveniently as $Q=\sqrt\frac{R_pC_1}{R_sC_2}$

