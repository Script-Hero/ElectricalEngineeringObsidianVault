We use the same **recursive binary splitting** [[Tree Building Process]] as we do in the regressive setting to grow a [[Classification]] Tree.
- However, in [[Classification]] **RSS cannot be used as the criterion for binary splits**
- An alternative is the **[[Classification]] error rate**
	- Not sensitive enough for tree growing
- Preferable alternatives:
	- **Gini Index**
	- **Cross Entropy**

## Classification Error Rate
$$E=1-\max\limits_k(\hat p_{mk})$$
- The fraction of of the training observations in that region that do not belong to the most common class
- $\hat p_{mk}$ represents the proportion of training observations in the $m$th region that are from the $k$th class

## Gini Index
$$G=\sum\limits_{k=1}^K\hat p_{mk}(1-\hat p_{mk})$$
- **GINI** is a measure of the total [[Random Signals and Systems/Variance|Variance]] across the $K$ classes
- Takes on a small value if all the $\hat p_{mk}$ are close to $0$ or $1$

## Cross Entropy
$$D=-\sum\limits_{k=1}^K\hat p_{mk}\log\hat p_{mk}$$
- [[Cross Entropy Error]]