1. We divide the feature space (the set of possible values for $x_1,x_2,\dots,x_p$) into $J$ distinct and non-overlapping regions $R_1,R_2,\dots,R_J$
2. For every observation that falls into the region $R_j$, we make the same prediction, which is simply the mean of the response values for the training observations in $R_j$

## Choosing regions $R1,\dots,R_J$
- In theory, the regions could have any shape 
- However, we choose to divide the predictor space into high-dimensional rectangles (boxes)
	- helps with interpretating the resulting predictive model
	- helps finding such a tree

**The goal is to find the $R1,R_2,\dots,R_J$ that minimizes the RSS (residual sum of squares)**
$$
\sum\limits_{j-1}^J\sum\limits_{i\in R_j}(y_i-\hat yR_j)^2
$$
Where $\hat{y}_{R_j}$ is the *mean response for the training observations within the $j$th box.*

- Unfortunately, it is computationally infeasible to consider every possible partition of the feature space into $J$ boxes.
- For this reason we take a **top down greedy approach** known as **recursive binary splitting**

### Recursive Binary Splitting
- *Top down* because it begins at the top of the tree and then successively splits the predictor space
	- each split is indicated via two new branches further down on the tree
- *Greedy* because at each step of the tree building the best split is made *for that particular step* without looking ahead and picking a split that will lead to a better tree in some future step
#### Steps
1. We select the predictor $X_j$ and the split point $s$ such that splitting the predictor space into the regions $\{X|X_j<s\}$ and $\{X|X_j>s\}$ leads to the greatest possible reduction in RSS
2. For any $j$ and $s$: $R_1(j,s)=\{X|X_j<s\}$ and $R_2(j,s)=\{X|X_j\geq s\}$
3. We see the values of $j$ and $s$ that minimizes: $$\sum\limits_{i:x_i\in R_1(j,s)}(y_i-\hat y_{R_1})^2+\sum\limits_{i:x_i\in R_2(j,s)}(y_i-\hat y_{R_2})^2$$
4. We repeat the process, finding the best predictor and best split point in order to split the data further so as to minimize the RSS within each of the resulting regions
	1. However, this time, instead of splitting the entire predictor space, we split one of the the two previously identified regions. We now have three regions
	2. Afterwards, we look to split one of these three regions further to continue to minimize RSS
5. The process continues until a stopping criterion is reached
	1. For example, we may continue until no region contains more than five observations
6. We predict the response for a given test observation using the mean of the training observations in the region to which that test observation belongs

![[tree_splitting_visualization.png]]

