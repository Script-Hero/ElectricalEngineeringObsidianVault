#Chapter8 

[[Continuous Random Variable]] with [[Probability Density Function]] $f_{X}(x)=\frac{1}{\sqrt{ 2\pi}\sigma}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$
- $\mu$ (mean) and $\sigma$ ([[Standard Deviation]]) are parameters
- $-\infty<x<\infty$

1. Define $Y=\frac{X-\mu}{\sigma}$
2. Let's say $\mu=80$ and $\sigma=20$
3. $P(X\geq 80)=P(\frac{X-\mu}{\sigma}\geq \frac{80-\mu}{\sigma})=P(Y\geq 1)=1-P(Y\leq 1)=1-\Phi(1)$

**If a Gaussian [[Random Signals and Systems/Random Variable|Random Variable]] has $\mu=0$ and $\sigma^2=1$ it is a *standard normal [[Random Signals and Systems/Random Variable|Random Variable]]*.**


### Characteristics
- [[Expected Value]] $E[X]=\mu$
- [[Variance]] $Var[X]=\sigma^2$
- The [[Cumulative Distribution Function]] of a Gaussian [[Random Signals and Systems/Random Variable|Random Variable]] has no closed-form solution, instead it is expressed with $\Phi(\frac{x-m}{\sigma})$
	- Where $\Phi(\cdot)$ is the Standard Normal [[Cumulative Distribution Function]] $\Phi(x)=\frac{1}{\sqrt{ 2\pi }}\int\limits_{-\infty}^xe^{-\frac{v^2}{2}}dv$
- 