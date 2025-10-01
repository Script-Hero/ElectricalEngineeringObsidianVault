A combination of [[Bagging]] and decision trees.

## Algorithm
1. **For** $b=1,\dots,B$
	1. Draw a new "data set" $\tilde{D}_n^{(b)}$ of size $n$ by sampling with replacement from $D_n$ 
	2. Build a tree on $\tilde{D}_n^{(b)}$ by recursively repeating the following until minimum node size $k$ is reached:
		1. Select $m$ features uniformly at random, *without* replacement, from the $d$ features
		2. Pick the best split dimension and split value among the $m$ features
		3. Build two children
2. **End for**
3. Return: average for regression; vote for [[Classification]]