#Chapter8 

A [[Probability Mass Function]] for [[Continuous Random Variable]]. Defined as:
$$
P(X\in[a,b])=\int\limits_{a}^b f_{X}(x)dx
$$

### Normalization Property
- $\int\limits_{-\infty}^\infty f_{X}(x)dx=1$
- $P(X\in A) = \int\limits_{x\in A}f_{X}(x)dx$

### Finding Outcomes
$$
P(x\leq X \leq x+\delta) = \delta \cdot f_{X}(x)
$$
Meaning that for $\delta=0$, $f_X = 0$
- The probability that an outcome is *exactly* $x$ is always $0$
	- You have to define a range $x$ can be in

### Derived Distribution
Computing the PDF of [[Functions of Random Variables]]
#### Example
Given $X\in[0,1]$ as a [[Uniform Random Variable]] and define $Y=e^X$, compute the Probability Density Function
- $f_{X}(x)=\begin{cases}1&\mbox{if } 0\leq x\leq 1\\0&\mbox{otherwise}\end{cases}$
- $F_{Y}(y)=P(Y\leq y)=P(e^X\leq y)=P(X\leq\log (y))=\int\limits_{x=0}^{\log(y)}1dx=\log(y)$
- Therefore $f_{Y}=\begin{cases}\frac{1}{y}&1\leq y\leq e\\0&\mbox{otherwise}\end{cases}$

**This process works with any given Probability Density Function**

### PDF of a Linear Function of a Random Variable
Finding the PDF of an [[Affine Function]] of [[Multiple Random Variables]]
- Let $X$ be a [[Continuous Random Variable]] with PDF $f_X$, and let $Y=aX+b$ for $a\neq 0$, then: 
	- $f_{Y}(y)=\frac{1}{|a|}f_{X}(\frac{y-b}{a})$
