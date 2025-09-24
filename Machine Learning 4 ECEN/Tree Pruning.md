Method for balancing [[Tree Size]] with RSS by building a large tree $T_0$ and then pruning it to obtain a *subtree*.

Intuitively, we should estimate the test error (using [[Cross Validation]] or the [[Validation Data Set]] approach)
- Too computationally intensive to test every possible subtree (many possible subtrees)
- Instead we use **Cost Complexity Pruning** to choose candidate subtrees before testing

## Cost Complexity Pruning
- We consider a sequence of trees indexed by a nonnegative tuning parameter (hyperparameter) $\alpha$
- For each value of $\alpha$, there exists a subtree $T$ that minimizes the loss $$\sum\limits_{m=1}^{|T|}\sum\limits_{x_i\in R_m}(y_i-\hat y_{R_m})^2+\alpha|T|$$
	- Where $|T|$ indicates the number of terminal nodes in $T$
- The tuning parameter $\alpha$ controls a trade-off between the subtree's complexity and its fit to the training data
- We select an optimal $\hat\alpha$ during [[Cross Validation]]
- We then return to the full data set and obtain the subtree corresponding to $\hat\alpha$