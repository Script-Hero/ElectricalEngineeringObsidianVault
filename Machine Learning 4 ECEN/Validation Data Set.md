A validation set is a portion of our training set that we set aside for assessing model performance **while the model is still being trained**.

1. Train model on the training set
2. Assess performance on the validation set
3. Update model weights (based only on testing set evaluations)
4. Repeat
5. After training is done, assess final performance on the test set

![[validation_set.png]]

The use of multiple validation sets is called [[Cross Validation]]