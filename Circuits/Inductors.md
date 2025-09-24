- Passive device, meaning it stores and releases energy, but cannot create energy

$$v=L\frac{di}{dt}$$
- Voltage is *inductance* times the rate of change of current
- The current in an inductor cannot change instantaneously, or else an infinite voltage would appear
- When a circuit with an inductor reaches a *steady state*, the *voltage* across the inductor will be zero
	- In steady state, the inductor looks like a short circuit

The inverse relationship of the voltage formula allows us to find the current across the inductor as a function of time:$$i(t)=i(t_0)+\frac{1}{L}\int\limits_{t_0}^tv(u)du$$

The *power* of an inductor is $\frac{L}{2}\frac{d}{dt}(i^2(t))$
The *energy* of an inductor is $w(t)=\frac{L}{2}i^2(t)$

Inductors *in series* combine like resistors: $L_{eq} = L_1 + L_2$
Inductors *in parallel* combine like resistors: $\frac{1}{L_{eq}}=\frac{1}{L_1}+\frac{1}{L_2}$

