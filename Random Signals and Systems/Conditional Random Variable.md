#Chapter7 
The conditional [[Probability Mass Function]] of [[Random Variable]] $X$ conditioned on [[Event]] $A$ where $P(A)>0$ is:
$$
p_{X|A}(x)=P(X=x|A)=P(\{X=x\}|A)=\frac{P\left( \{X=x\}\bigcap A \right)}{P(A)}
$$
### Total Probability Theorem
$\sum\limits_{x}P\left( \{X=x\}\bigcap A \right)=P(A)$
- Implies that $\sum\limits_{x}p_{X|A}(x)=1$ proving it's a legitimate PDF

### Conditioning *on* Random Variables
If $A$ is itself a [[Random Signals and Systems/Random Variable|Random Variable]], you can construct a [[Conditional Probability Mass Function]] as follows:
$$p_{Y|X}(y|x)=P(Y=y|X=x)=\frac{P\left( \{Y=y\}\bigcap P(\{X=x\}) \right)}{P(X=x)}=\frac{p_{X,Y}(x,y)}{p_{X}(x)}$$
