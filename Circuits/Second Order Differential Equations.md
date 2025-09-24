A general second order constant coefficient DEQ is of the form:
$$a\frac{d^2y}{dt^2}+b\frac{dy}{dt}+cy(t)=x(t)$$
Along with a pair of initial conditions:
$$y(0)=y_o,\frac{dy}{dt}(0)=y_1$$

We construct the full solution the same way we do with [[First Order Differential Equations]], by finding $y(t)=y_h(t)+y_p(t)$

## Finding the Homogenous Solution
$$a\frac{d^2y}{dt^2}+b\frac{dy}{dt}+cy(t)=0$$

1. Assume a solution of the form $y(t)=Ae^{st}$
2. Plug that into the original equation producing the *characteristic equation* $as^2+bs+c=0$
3. The solution (roots) will have one of three different forms and dictates the *homogenous solution*
	1. **Distinct real roots:** $A_1e^{s_1t}+A_2e^{s_2t}$
	2. **Complex roots $s=\sigma\pm j\omega$:** $B_1e^{\sigma t}\cos(\omega t)+B_2e^{\sigma t}\sin(\omega t)$
	3. **Repeated real roots:** $C_1e^{s_0t}+C_2te^{s_0t}$

These roots relate to the *damping* response of the circuit. See [[Damping]].

## Finding the Particular Solution
$$a\frac{d^2y}{dt^2}+b\frac{dy}{dt}+cy(t)=x(t)$$
We use the method of undetermined coefficients to find the particular solution by guessing the form of $y_p(t)$ based on the form of $x(t)$:
![[second_order_particular_solution_table.png]]


## Example Problem
$$\frac{d^2y}{dt^2}+3\frac{dy}{dt}+2y=4$$
With initial conditions:
- $y(0)=1$
- $\frac{dy}{dt}(0)=0$

### Homogenous Solution
$$\frac{d^2y}{dt^2}+3\frac{dy}{dt}+2y(t)=0$$
1. Characteristic equation is $s^2+3s+2=0$
2. The roots are $s_1=-1,s_2=-2$
3. The *homogenous solution* is $y_H(t)=A_1e^{-t}+A_2e^{-2t}$

### Particular Solution
1. Assume $y_p(t)=c$
	1. $\frac{dy_p}{dt}=0$
	2. $\frac{d^2y_p}{dt^2}=0$
2. Plug into the initial equation, and we get $2c=4$
	1. $c=2$
3. If $y_p(t)=c$ then $y_p(t)=2$

### Apply Initial Conditions
1. $y(t)=y_p(t)+y_H(t)$
2. $y(t)=A_1e^{-t}+A_2e^{-2t}+2$
3. Construct the system of equations:
	1. $y(0)=1\rightarrow A_1 + A_2 + 2 = 1$
	2. $\frac{dy}{dt}(0)=\rightarrow -A_1-2A_2=0$
4. Solving we find $A_1=-2, A_2=1$
5. Therefore the **final solution** to the differential equation is $y(t)=-2e^{-t}+e^{-2t}+2$

