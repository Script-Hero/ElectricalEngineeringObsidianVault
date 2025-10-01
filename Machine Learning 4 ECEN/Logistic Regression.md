Good for [[Classification]] type problems, where the outputs will be a [[Probability]] between $0$ and $1$.
$$
h(x)=\sigma(\sum\limits_{i=0}^{d}w_ix_i)=\sigma(w^Tx)
$$
- Where $\sigma(\cdot)$ is the [[Sigmoid Function]] $\frac{1}{1+e^{-x}}$
- $h(x)\in[0,1]$
	- Therefore $y_n=\pm1$

We usually use [[Cross Entropy Error]] to measure accuracy.

