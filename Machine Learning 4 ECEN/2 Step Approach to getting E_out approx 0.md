Together, these 2 conditions ensure $E_\text{out}\approx0$ 
1. $E_\text{out}(g)\approx E_\text{in}(g)$
	1. Must be verified using [[Hoeffding Inequality]]
2. $E_\text{in}(g)\approx0$
	1. We can ensure a low [[In-Sample Error]] using a method such as [[Perceptron Learning Algorithm]]

## [[Hypothesis]] Tradeoff
- Small $|H|\rightarrow E_\text{in}\approx E_\text{out}$
- Large $|H|\rightarrow E_\text{in}\approx0$ is more likely.


**If the function $f$ we want to approximate is simple, we can use a small $H$ to get $E_\text{in}\approx0$ and therefore need a smaller $N$**
- Complex target $f$ requires larger $H$ and therefore needs a larger $N$