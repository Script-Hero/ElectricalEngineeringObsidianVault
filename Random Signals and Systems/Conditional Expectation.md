#Chapter7 


The [[Expected Value]] of [[Random Variable]] $Y$ given $X=x$ with respect to the [[Conditional Probability Mass Function]] $p_{Y|X}(\cdot,x)$.
$$
E[Y|X=x]=\sum\limits_{y}yp_{Y|X}(y|x)
$$

- can be viewed as a function of $x$ such that $h(x)=E[Y|X=x]$
- can be defined as [[Random Variable]] so $h(X)=E[Y|X]$

### Tower Property of Conditional Expectation
The expected value of $E[Y|X]$ is equal to $E[Y]$ meaning:
- $E[E[Y|X]]=E[Y]$
Through this definition we find:
- $E[Y]=\sum\limits_{x}E[Y|X=x]p_{x}(x)$
