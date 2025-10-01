***B**ootstrap **agg**regat**ing*** or bagging is a general-purpose procedure for **reducing the [[Random Signals and Systems/Variance|Variance]] of a statistical learning method.**

Consider a set of $n$ independent observations $x_1,x_2,\dots,x_n$ with mean $\mu$ and [[Random Signals and Systems/Variance|Variance]] $\sigma^2$
- Then the average $\bar x = \frac {(x_1,x_2,\dots,x_n)} n$ has:
	- Mean $\mu$
	- [[Random Signals and Systems/Variance|Variance]] $\frac{\sigma^2}{n}$
**Averaging a set of observations reduces [[Random Signals and Systems/Variance|Variance]]**
- The goal is to learn multiple trees from different data sets, and average their outcome
	- But this is not possible right away as we have limited data and do not have multiple independent training sets

## Algorithm
1. Training data $D_n$
2. **For** $b=1,\dots,B$
	1. Draw a new "data set" $\tilde{D}_n^{(b)}$ of size $n$ by sampling with replacement from $D_n$ 
	2. Train a predictor $\hat f^{(b)}$ on $\tilde{D}_n^{(b)}$
3. **end for**
- *For regression*: the predictor $\hat{f}_\text{bag}(x)=\frac 1 B \sum\limits_{b=1}^B\hat f ^{(b)}(x)$
- *For [[Classification]]*: predictor at a point is class with highest vote count at that point