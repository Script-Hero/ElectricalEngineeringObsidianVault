![[cross_validation.png]]

To select a hyperparameter value via cross-validation:
1. List out several different "guesses" for the best hyperparameter
2. For each guess, run cross-validation to compute the cross-validation error for that choice of hyperparameter value
3. Select the hyperparameter with the lowest cross-validation error.


**Example: Guesses for learning rate are 0.1, 1, and 10. We decide to apply 3-fold cross-validation.**
![[3_fold_cross_validation.png]]
- We choose $\alpha=0.1$ because it has the lowest CV error

