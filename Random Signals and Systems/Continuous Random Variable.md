#Chapter8 

[[Random Variable]] with a continuous / infinite number of potential output values. 
- Counterparts with all [[Discrete Random Variable]] concepts and methods

Outcomes are predicted with a [[Probability Density Function]]

### Characteristics
- [[Expected Value]] $E[X]=\int\limits_{-\infty}^{\infty}xf_{x}(x)dx$
	- For a [[Functions of Random Variables]] $E[g(x)]=\int\limits_{-\infty}^{\infty}g(x)f_{X}(x)dx$
- [[Variance]] $Var[X]=\int\limits_{-\infty}^{\infty}(x-E[X])^2f_{X}(x)dx$
	- Using [[Moments]], Variance is $Var[X]=E[X^2]-(E[X])^2$
- [[Linearity of Expectation]] $E[aX + b] = aE[X]+b$
- 