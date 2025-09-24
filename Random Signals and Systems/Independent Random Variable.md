#Chapter7 

Two [[Random Variable]]s $X$ and $Y$ are **independent random variables** if their [[Joint Probability Mass Function]] is:
$$
p_{X,Y}(x,y)=p_{X}(x)p_{Y}(y) \mbox{, for every } x,y
$$
- For arbitrary number $n$ of independent random variables, the [[Joint Probability Mass Function]] is $p_{\mathbf{\vec{x}}}(\mathbf{\vec{x}})=\prod\limits_{k=1}^np_{X_{k}}(x_{k})$

### Characteristics:
- [[Expected Value]] $E[XY]=E[X]E[Y]$
	- $E[g(X)h(Y)]=E[g(X)E[h(Y)]$ for any function $g$ and $h$
- [[Variance]] $Var[X+Y]=Var[X]+Var[Y]$
- **Sum** if $Z=X+Y$ then the PMF can be found with $\sum\limits_{x}p_{X}(x)p_{Y}(z-x)$
	- Called "discrete convolution" of the PMFs of $X$ and $Y$
- 
