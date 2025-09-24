#Chapter5 
Sometimes referred to as "marginal probability mass functions". Describes the outcomes of a [[Discrete Random Variable]] using $p_{X}(x)=P(\{X=x\})$
- Meaning "$p_X(x)$ is the probability of the event $\{X=x\}$"
- *Example:*
	- The probability mass function (PMF) of the number of heads of 2 independent tosses of a coin
	- $\begin{cases}\frac{1}{4}& \mbox{if x = 0 or x=2}\\ \frac{1}{2} & \mbox{if x=1} \\ 0 & \mbox{otherwise}\end{cases}$

## Normalization Property
$$
\sum_{x\in X}p_{X}(x)=1
$$
- Meaning adding the probability of each outcome will always equal 1
	- For the example above, $\frac{1}{4}+\frac{1}{4}+\frac{1}{2}+0=1$
- For any subset $S$, the probability that $X$ belongs in $S$, is $P(X\in S)=\sum_{x\in S}p_{X}(x)$
