#Chapter7 

A [[Probability Mass Function]] when a [[Conditional Random Variable]] is conditioned on a different [[Random Variable]]

$$p_{Y|X}(y|x)=P(Y=y|X=x)=\frac{P\left( \{Y=y\}\bigcap P(\{X=x\}) \right)}{P(X=x)}=\frac{p_{X,Y}(x,y)}{p_{X}(x)}$$

### Conditional PMF Properties
- **Valid** if $\frac{1}{p_{X}(X)}\sum\limits_{y}p_{X,Y}(x,y)=1$ 
- Probability that $Y\in S$ given that $X=x$, $P(Y\in S,X=x)=\sum\limits_{y\in S}p_{Y|X}(y|x)$
	- In other words, summing the conditional probability $p_{Y|X}(\cdot,\cdot)$ for all outcomes included in $S$

### Product Rule of Conditional Probability
- Relates the [[Joint Probability Mass Function]] $p_{X,Y}(x,y)$ to the Conditional PMF $p_{Y|X}(y|x)$
$$p_{X,Y}(x,y)=p_{X|Y}(x|y)p_{Y}(y)=p_{Y|X}(y|x)p_{X}(x)$$
## Expected Value
Use [[Conditional Expectation]] in place of [[Expected Value]] 