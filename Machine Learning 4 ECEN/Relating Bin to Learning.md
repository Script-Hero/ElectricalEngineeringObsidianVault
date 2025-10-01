We can relate the [[Hoeffding Inequality]] to the [[BIN Model]] using the [[In-Sample Error]] and the [[Out-Of-Sample Error]]. 

$$P[|E_\text{in}(h)-E_\text{out}(h)|>\epsilon]\leq2e^{-2\epsilon^2 N}\text{, for any }\epsilon>0$$
$$P[|E_\text{in}(h)-E_\text{out}(h)|\leq\epsilon]>1-2e^{-2\epsilon^2 N}\text{, for any }\epsilon>0$$

$E_\text{in}$ is random but known; $E_\text{out}$ is fixed but unknown.

- If $E_\text{in}\approx0$ then $E_\text{out}\approx0$ with high [[Probability]]
	- Meaning $f\approx h$
- If $E_\text{in}\gg0$ we're out of luck
	- All we've learned is that $f\not\approx h$  
- See [[2 Step Approach to getting E_out approx 0]]