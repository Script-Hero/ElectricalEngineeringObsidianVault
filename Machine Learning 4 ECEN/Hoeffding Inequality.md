See [[BIN Model]]. Hoeffding proved that most of the time, $\nu$ cannot be too far from $\mu$.

$$
P[|\nu-\mu|>\epsilon]\leq2e^{-2\epsilon^2 N}\text{, for any }\epsilon>0
$$
$$
P[|\nu-\mu|\leq\epsilon]\geq1-2e^{-2\epsilon^2 N}\text{, for any }\epsilon>0
$$
We get to select any $\epsilon$ we want.

- Note that the bound $2e^{-2\epsilon^2N}$ does not depend on $\mu$ or the size of the bin.
	- Meaning the bin (population size) can be infinite
- The key player in the bound $2e^{-2\epsilon^2N}$ is $N$
	- If $N\rightarrow\infty,\mu\approx \nu$ but never $\mu=\nu$

## Example Application

Say $N=1000$, we draw a sample and observe $v$.
- $99\%$ of the time $\mu-0.05\leq \nu\leq \mu + 0.05$ if we set $\epsilon=0.05$
	- Because $2e^{-2\epsilon^2N}=0.99$ if $\epsilon=0.05$ and $N=1000$
- $99.9999996\%$ of the time $\mu-0.10\leq \nu \leq \mu + 0.10$ if we set $\epsilon=0.10$

This means that if I pick a sample of size 1000 and observe the sample mean $\nu$ and claim that the error on the population sample $\mu$ is $\pm0.05$, I will be right 99% of the time. 