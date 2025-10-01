#Chapter7 

Relates 2 [[Discrete Random Variable]]s $X$ and $Y$ with a single [[Probability Mass Function]]
$$
P_{X,Y}(x,y)=P(\{X=x\}\cap\{Y=y\})=P(X=x, Y=y)
$$

In general, $p_{X_{1},X_{2},\dots,X_{n}}(x_{1},x_{2},\dots,x_{n})=P\left( \prod\limits_{k=1}^n \{X_{k}=x_{k}\}\right)$
- If the random variables are [[Independent Random Variable]] their Joint PMF reduces to $p_{\mathbf{\vec{x}}}(\mathbf{\vec{x}})=\prod\limits_{k=1}^np_{X_{k}}(x_{k})$

Same properties as normal [[Probability Mass Function]], including Normalization and the relationship of normalization for $P((X,Y)\in A)$ 

### Relationship to Marginal [[Probability Mass Function]]
- $p_{X}(x)=P(X=x)=\sum\limits_{y}P(X=x,Y=y)=\sum\limits_{y}p_{X,Y}(x,y)$
	- $p_{X}(x)=\sum\limits_{y}p_{X,Y}(x,y)$
	- $p_{Y}(y)=\sum\limits_{x}p_{X,Y}(x,y)$
- The marginal [[Probability]] can be found by *summing* the joint probabilities over all possible values of $Y$
	- Like "collapsing" the two-dimensional joint [[Probability]] distribution to just one dimension for $X$ by summing all possibilities across $Y$

### Finding a Joint PMF
- Construct a table where the top row is X values and the left column is Y values, then fill in the cell with the [[Probability]] of that $x$ and $y$ occurring.
	- To find $p_X$ (marginal PDF of $X$) you add just 1 column of values
	- For $p_Y$ add 1 row of values

**Alternatively** you can use the [[Conditional Probability Mass Function]]'s "Product Rule of Conditional [[Probability]]" to construct a Joint PMF from a Marginal PMF


