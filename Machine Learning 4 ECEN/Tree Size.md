If we continue the [[Tree Building Process]] for a long time, we may get a low training error, *but is likely to overfit*, leading to poor test set performance.
- A smaller tree with fewer splits might lead to lower variance and better interpretation at the cost of a increased bias
- One possible alternative to the [[Tree Building Process]] is to grow the tree *only so long as the decrease in the RSS due to each split exceeds some (high) threshold*
	- Results in smaller trees **but is too short sighted**
	- A seemingly worthless split early on in the tree tree may be followed by a very good split that leads to a large reduction in RSS *later on*
- A better alternative is [[Tree Pruning]]