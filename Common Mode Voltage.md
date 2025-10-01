Defined as:
$$
V_{cm}=\frac{v_\text{in+}+v_\text{in-}}{2}
$$

![[common_mode_voltage.png]]
Way to write differential signals in [[Electronics/Operational Amplifier|Operational Amplifier]]
- This allows us to express each input [[Voltage]] signal in terms of a single variable $V_{cm}$


This is typically used as follows
1. $v_\text{in+}=V_{cm}+\frac{v_d}2$
2. $v_\text{in-}=V_{cm}-\frac{v_d}{2}$
3. Therefore: $v_\text{in+}-v_\text{in-}=v_d$
	1. **No common mode [[Voltage]]** in this *ideal* example
	2. **IRL, Common Mode [[Voltage]] leaks into the differential signal**
	3. We measure this with the [[Common Mode Rejection Ratio]]

# The Input's CM $\neq$ Output's CM
![[common_mode_2.png]]
The ground for the subject does not have to be equal to the instrument's ground.

