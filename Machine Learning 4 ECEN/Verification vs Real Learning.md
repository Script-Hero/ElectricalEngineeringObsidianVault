
- Given $h\in H$ a sample can **verify** whether or not $h$ is good with respect to $f$
	- If $E_\text{in}$ is small, $h$ is good with high confidence 
	- If $E_\text{in}$ is large, $h$ is bad with high confidence 
- We have no control over $E_\text{in}$

- In learning, you actually **fit** the data, as with the [[Perceptron Learning Algorithm]].
	- $g$ results from searching an entire hypothesis set $H$ for a hypothesis with small $E_\text{in}$

## Verification
- Fixed single [[Hypothesis]] $h$ 
- $h$ to be certified
- $h$ does not depend on data $D$ 
- No control over [[In-Sample Error]]
- **Checking if $h(x)$ is good**

## Real Learning
- Fixed *hypothesis set* $H$
- $g$ to be certified 
- $g$ results after searching $H$ to fit $D$
- Pick best [[In-Sample Error]]
- **Searching for the best $g(x)\in H$**


# Relation to [[Hoeffding Inequality]]

$$
P[|v-\mu|>\epsilon]\leq2|H|e^{-2\epsilon^2 N}\text{, for any }\epsilon>0
$$
$$P[|v-\mu|\leq\epsilon]\geq1-2|H|e^{-2\epsilon^2 N}\text{, for any }\epsilon>0$$

**$E_\text{in}(g)\approx E_\text{out}(g)$ for finite $H$**
- We don't care how $g$ was obtained *as long as it is from $H$*

$$
E_\text{out}\leq E_\text{in}(g)+\sqrt{\frac 1 {2N}\log\frac{2|H|}{\delta}}
$$
- If $N\gg\ln|H|$ then $E_\text{in}(g)\approx E_\text{out}(g)$
	- Does not depend on $X$, $P(x)$, or how $g$ is found
	- Only requires $P(X)$ to generate the data points independently *and also* the test points