

- **Softmax:** $p_k=\frac{e^{s_k}}{\sum\limits_{l=1}^Ke^{s_l}}$
- **tanh:** $\text{tanh}(x)=\frac{e^x-e^{-x}}{e^x+e^{-x}}$
# Vanishing gradient problem
- When gradients of the loss function become very small during backpropagation
### Causes
- Happens when using activation functions like *sigmoid* or *tanh*, where the numbers (and therefore their derivatives) are always less than 1, and as these small derivatives get multiplied layer by layer the gradient *shrinks exponentially*
- Lower layers receive tiny weight updates and the network barely learns at all
### Symptoms
- Training error decreases very slowly or plateaus
- Initial layers learn noting
- Weight layers stop updating effectively
### Solutions
- **Use ReLU activation (derivative = 1 for positive inputs and 0 for negative inputs)**
- Weight initialization (if exploding gradient happens at the beginning)
- Batch normalization
- Residual Connections (Skip Connections)
- **Gradient clipping**
	- Especially for RNNs
- LSTM

# Exploding gradient problem
- During backpropagation **the gradients become excessively large** causing:
	- Weights exploding, causing overflows, NaN, or oscillation between bad local minimums
	- Failure to converge
### Causes
- During backpropagation when you multiply the gradients of each layer, if the derivatives are > 1, their product *grows exponentially*

### Solutions
- **Gradient clipping**
- **Smaller learning rates**
- Batch normalization

# Gini Index
- AKA Gini Impurity
- Score of *impurity* or disorder used to score *each split* in a decision tree
	- The Gini Index is applied to a node that is the outcome of the split in question
$$\text{Gini}=1-\sum\limits_{i=1}^{k}p_i^2$$
- Where:
	- $p_i$ is the proportion of samples belonging to class $i$ in that node
	- $k$ is the total number of classes
- Basically, if the split point is so good that the node afterward only has 1 class, then it is a really good split.
	- If all the nodes that are the outcome of that decision have a Gini of 0, then it is a perfect split 
### Intuition
- Lower Gini = purer node (mostly one class)
	- All one class $\rightarrow$ Gini = 0
- Higher Gini = more mixed node (classes more evenly distributed)
	- Node is a perfect mix of outcomes $\rightarrow$ Gini = $\frac 1 k$ 

### Scoring a proposed split
- Let's say we're trying to score a split using criterion $X$ (which is a categorical variable that all the items in the dataset have) that can have 3 possible values ($X_1$,$X_2$, and $X_3$). The target variable can have 3 possible values too ($A$, $B$, and $C$)
	- Partition 1 is all the samples that have $X_1$ as their value of $X$. 
		- Compute the Gini Index by taking $1-p_A-p_B-p_C$ where $p_n$ is how many in node $X_1$ have target value $A$ compared to the total number of samples in node $X_1$
	- Repeat for each possible value of $X$
	- Add all the Gini's together as the weighted sum of the Gini for a branch and the percentage of nodes in that branch relative to the total nodes in all the other outcome nodes and you get the total Gini for the branch
		- $\text{Gini}_\text{split}=\sum\limits_{i=1}^k\frac{n_i}{n_\text{total}}\cdot\text{Gini}_i$
			- Where $n_i$ is the number of samples in node $i$

# k Nearest Neighbors Prediction
- Choose $k$ which is the number of nearby datapoints that "vote" to classify our unknown input
- We compute the Euclidean distance from each datapoint to the unknown point
	- This works in any number of dimensions
- Choose the $k$ nearest (smallest distance)
- Whatever the majority has as its class (binary) is the prediction you take
**Special case** is *bag of words* where each document (like an email) becomes a vector of word counts, where index $i$ of the vector is always the word counts of the same word $i$ across all documents
- Then you do normal KNN prediction for label

# Logistic Regression
- Used for **binary classification**
- Predicts using function $$\hat p (y=1|\pmb x)=\sigma(\pmb w^T\pmb x+b)=\frac 1 {1+e^{-(\pmb w^T\pmb x+b)}}$$
- Where sigmoid (logistic) activation function has the formula: $\sigma(z)=\frac 1 {1+e^{-z}}$
	- Note that $\sigma(\sum\limits_{i=0}^d=\sigma(\pmb w^T\pmb x)$
- Make prediction of 1 (as opposed to 0) if $\hat p > 0.5$

# Neurons
- Take a weighted sum of all the inputs ($(w_1\cdot x_1+w_2\cdot x_2\dots)$), add the bias term $w_0$ to the result, then put the result into the activation function

# Support Vector Machine
- Finds the **best boundary (hyperplane)** that separates classes in a dataset
	- For *binary classification* it tries to find the **hyperplane that maximizes the margin** between the 2 classes
	- the **support vectors** are the training points **closest to the hyperplane** that "support" or *define the boundary*
## The Margin
Given:
- $\pmb w$ is the weight vector (defines orientation of the hyperplane)
- $b$ is the bias (defines position of the the hyperplane)
- $\pmb x\in R^n$ is the input vector
- $y\in\{-1,+1\}$ is the class label 

The **decision function** is:
$$f(x)=\text{sign}(\pmb w^T\pmb x+b)$$
and the SVM seeks the **hyperplane**:
$$\pmb w^T+b=0$$
that **maximizes the margin**:
$$\text{Margin}=\frac 2 {||\pmb w||}$$

## Solutions
### Hard Margin
**Assumes linearly separable data**
Optimization problem, we solve $$\min\limits_{w,b}\frac 1 2|
|\pmb w||^2$$
subject to:
$$y^{(i)}(\pmb w^T\pmb x^{(i)}+b)\geq1\text{ for all }i$$

Which means:
- All points are correctly classified
- All points are **outside or on the margin boundary**
	- **does not work for data that isn't perfectly separable**
### Soft Margin
**Allows slack to handle overlapping classes (non-linearly-separable data)**
If that data isn't perfectly separable we introduce *slack variables* $\xi_i$ and a penalty term $C$:
$$\min\limits_{\pmb w, b, \xi}\frac 1 2 ||\pmb w||^2+C\sum\limits_{i=1}^{n}\xi_i$$
subject to:
$$y^{(i)}(\pmb w^T\pmb x^{(i)}+b)\geq1-\xi_i\text{, for all }i$$


## Regularization
- $C$ controls the trade-off between maximizing the margin and minimizing the classification error
- Large $C$ = heavily penalizes misclassification = *hard margin*
- Small $C$ = allows more misclassifications = *wider margin*
![[regularization_visualization.png]]
- **Model A** has a larger $C$ because it allows fewer misclassifications (has a "harder" margin)
- **Model B** has a small $C$ = "soft" margin
## Example
For data:

| $x_1$ | $x_2$ | Class |
| ----- | ----- | ----- |
| 2     | 1     | +1    |
| 4     | 3     | -1    |

1. Break the equation into equations from the margin constraints
	1. *For point 1:* $(2w_1+1w_2+b)=+1$
	2. *For point 2:* $(4w_1+3w_2+b)=-1$
2. Solve the set of multiple linear equations for $w_1$ and $w_2$ *in terms of $b$*
	1. We get $w_1=2-b$ and $w_2=-3+b$ in this case
3. Choose $b$ that minimizes $||\pmb w||^2$
	1. $||\pmb w||^2=w_1^2+w_2^2=(2-b)^2+(-3+b)^2$
	2. This expands to $2b^2-10b+13$
	3. Set the derivative to 0 to find the minimum: $4b-10=0\rightarrow b=2.5$
		1. Plugging back into original $w$s:
			1. $w_1=-0.5$
			2. $w_2=-0.5$
			3. $b=2.5$
4. We find the *maximum margin hyperplane* is $-0.5x_1-0.5x_2+2.5=0$
	1. Simplifies to $x_1+x_2-5=0$

# k-Means
- Cluster $n$ datapoints into $k$ clusters
1. Choose $k$ random points as centroids 
2. Assign each datapoint to its *nearest centroid* (using Euclidean distance)
3. Define new centroid as the average of every datapoint in that centroids group
	1. As in, new centroid $n$ is the average of every datapoint most recently assigned to previous centroid $n$
4. Update until no datapoints change centroid


# Regularization
A penalty *added to the loss function* that *shrinks model parameters towards zero* to reduce overfitting.
- L2 regularization adds $\lambda(||\pmb w||^2+b^2)$ to the loss function where $\lambda$ is the bias parameter
- L1 regularization adds $\lambda(||\pmb w||+|b|)$ to the loss function where $\lambda$ is the bias parameter
## Fun Facts
Given the following loss formulation:
$$\sum\limits_{i=1}^N(h(\pmb x_i)-y_i)^2+\lambda\sum\limits_{i=1}^dw_i^2$$
- There are $N$ data points
- The data is $d$ dimensional
- Larger values of $\lambda$ imply increased regularization
- L2 (Ridge) regularization is used
The following are *not* true:
- This is a classification model
- L1 (Lasso) regularization is used

# Overfitting
- When a model has very high training accuracy but very bad testing accuracy 
- To reduce overfitting:
	- *Increase* number of training samples
	- *Increase* regularization constant
	- *Decrease* the number of hidden layers
	- *Decrease* the number of neurons in each hidden layer
	- The number of test data samples *has no effect on overfitting*
	- The number of nodes on the output layer *has no effect on overfitting*
- If the neural network loss curve is almost completely flat from the start, *the learning rate is probably too low*
	- Or if the model is *too deep*
	- Or if you have *vanishing gradients*

# RNNs
![[rnn.png]]
Where:
- $h_t=f(w_1x_t+w_2h_{t-1}+b_h)$
	- Updates the hidden state
	- $f$ is the activation function
- $y_t=w_3h_t+b_3$
	- Determines the output
## Fun Facts
- Training RNNs is difficult because of vanishing and / or exploding gradients
- RNNs differ from feed-forward neural networks in that they have an additional weight matrix connect hidden layers across time steps
- RNNs can process sequences of arbitrary length (while feed-forward neural networks cannot)

# Transformers
- Sequence to sequence
- Uses word embeddings
- *You have to send the entire hidden state of the encoder to the first timestep of decoder*
	- Because word $i$ of the input sequence may not correspond to word $i$ of the output sequence
	- the entire input sequence matters for each word of the output sequence
	- "Fails to capture sequence-level structure and disrupts temporal alignment"

# Model Curves
![[model_curves.png]]
1. Ridge regression with degree 10 polynomial features
	1. Still a degree-10 polynomial but has strong L2 regularization
	2. Doesn't overreact to every small change in the data
	3. Curve will follow the general shape/trend of the data but won't try to hit every point
	4. No wild oscillations near the edges
2. Linear regression with 10 polynomial features. Indicators are
	1. Curve passes exactly through almost every point
	2. Extreme oscillation, especially near edges
	3. "Wiggles" unnecessarily to fit the noise
	4. Highly sensitive to outliers or fluctuation in the noise
3. Linear regression
	1. Straight line with no curvature
	2. Misses many datapoints, underfit
**Rule of thumb is**:
- High-degree polynomial, no regularization : overfit, fits noise
- Low-degree (or linear) model : misses trend
- Good degree + regularization : smooth, fits general trend

# Perceptron
- Single-layer neural network for binary classification that performs: $\text{Output}=\text{sign}(\pmb w^T\pmb x + b)$
	- Classifies between $-1$ and $+1$ 
Training is as following:
1. Initialize weights $\pmb w=0$ and bias $b=0$
2. Repeat until convergence:
	1. For each training sample ($x,y$):
		1. Compute prediction: $\hat y =\text{sign}(\pmb w^T\pmb x +b)$
		2. If $\hat y \neq y$ (meaning misclassification)
			1. $\pmb w\leftarrow \pmb w+ y\pmb x$
				1. Note that $y\in\{-1,+1\}$ and *not* $\{0,1\}$ (this is often confused)
			2. $b\leftarrow b+y$

# Convolutional Neural Network
- Given a kernel ($m\times m$ matrix) with a bias term (scaler)
- Slide the kernel (small matrix) over patches of the big matrix
	- Multiply element wise and sum all values to get the output of the dot product kernel slidey multiplication, output should be a scaler
	- Reduces the original image size
- If the image is $n\times n$ and the filter is $m \times m$ and the bias is $1 \times 1$ and the stride is $S$ the size of the resulting feature layer is:
$$([\frac{n-m}{S}]+1)\times([\frac{n-m}{S}]+1)$$

---
---
---

## Decision Trees & k-NN Additions

### Overfitting in Trees
- Overfitting = tree too deep, memorizes data
- Causes: no pruning, noise, many splits

### k = 1 Decision Boundary
- For $k = 1$, decision boundary is a **piecewise linear surface** (Voronoi diagram in 2D)

### Training Error vs. Generalization
- $k = 1$ minimizes training error → likely overfits  
- Use **validation set** to select $k$ for generalization

---

## Naive Bayes Additions

### Prediction Formula
$\hat{y} = \arg\max_y P(y) \prod_i P(x_i \mid y)$

### Laplace Smoothing
$P(x_i \mid y) = \dfrac{\text{count}(x_i, y) + 1}{\text{count}(y) + k}$  
- $k$ = number of possible values for $x_i$

---

## SVM Additions

### Kernel Trick
If $\phi(x) = (x_1^2, \sqrt{2}x_1x_2, x_2^2)$, then:  
$k(x, z) = (x \cdot z)^2$

### Hard-Margin Limitation
- Hard margin SVM works only if data is **linearly separable**

### Adding Features
- Adding $x_2^2$ or $\|x\|^2$ can make data linearly separable

---

## PCA (Principal Component Analysis)

### Steps
1. Center data: $X_{\text{centered}} = X - \bar{X}$
2. Covariance matrix:  
   $\Sigma = \dfrac{1}{n} X^T X$
3. Compute eigenvalues and eigenvectors of $\Sigma$
4. Project to principal components:  
   $Z = XW$ where $W$ is matrix of top eigenvectors

---

## Neural Network & Backpropagation Additions

### Derivatives
- Sigmoid:  
  $\dfrac{d}{dx} \sigma(x) = \sigma(x)(1 - \sigma(x))$
- Tanh:  
  $\dfrac{d}{dx} \tanh(x) = 1 - \tanh^2(x)$

### Hidden Layer Gradient (Backprop)
$\dfrac{\partial L}{\partial w_{ij}} = \delta_j x_i$  
where $\delta_j = \left( \sum_k \delta_k w_{jk} \right) f'(z_j)$

---

## CNN (Convolutional Neural Networks)

### Output Size (no padding)
$\text{Output size} = \left\lfloor \dfrac{n - k}{s} + 1 \right\rfloor$  
- $n$: input size, $k$: filter size, $s$: stride

### Conv Layer Parameters
$\text{Params} = (k_H \cdot k_W \cdot C_{\text{in}} + 1) \cdot C_{\text{out}}$  
- $k_H, k_W$: kernel height & width  
- $C_{\text{in}}$: input channels  
- $C_{\text{out}}$: number of filters

### FC Layer Parameters
$\text{Params} = (\text{input dim} + 1) \cdot \text{output dim}$

---

## RNN Additions

### Binary Threshold Activation
$$f(x) =
\begin{cases}
1 & \text{if } x \geq 0 \\
0 & \text{if } x < 0
\end{cases}$$ 
$$g(x) = x$$

### Desired RNN Behavior
- If input becomes 0 → output remains 0 forever  
- One solution:  
  $w_1 = -1$, $w_2 = 1$, $b_2 = 0.5$  
  $w_3 = -1$, $b_3 = 1$

---
---
---
## Additional Key Facts & Formulas from ECEN 250 Review

### Forward & Backward Propagation
- **Forward propagation**: Compute neuron outputs and loss  
- **Backpropagation**: Update weights using gradient descent

### Loss Function
- Measures how far predicted values are from ground truth  
- Typical example (MSE): $L = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$

---

## Gradients & Learning Rate

### Learning Rate $\eta$
- Controls **step size** during gradient descent  
- Influences how much the weights change:  
  $\text{update: } w \leftarrow w - \eta \cdot \frac{\partial L}{\partial w}$

### Gradient of Loss (example):
$\frac{\partial L}{\partial w_1} = -2(y_i - \hat{y}_i) \cdot z_1$

---

## Neural Activations

### Sigmoid / Logistic
$\phi(z) = \frac{1}{1 + e^{-z}}$  
$\phi'(z) = \phi(z)(1 - \phi(z))$

### ReLU
$\phi(z) = \max(0, z)$  
$$\phi'(z) =
\begin{cases}
1 & \text{if } z > 0 \\
0 & \text{if } z \leq 0
\end{cases}$$

---

## CNN Operations

### Output Size (Convolution)
$W_{\text{out}} = \left(\frac{W_{\text{in}} - F + 2P}{S}\right) + 1$  
- $F$: filter size, $P$: padding, $S$: stride  
- Depth of output = number of filters

### Output Size (Pooling)
Same formula as convolution but applied after pooling  
(e.g., $2 \times 2$ filters, stride 2 → halves dimensions)

---

### CNN Parameters
- **Conv layer params**:  
  $n_{\text{params}} = (F_H \cdot F_W \cdot D_{\text{in}} + 1) \cdot N_{\text{filters}}$
- Example: $5 \times 5$ filter, depth 3, 10 filters →  
  $5 \cdot 5 \cdot 3 = 75$ + 1 bias = 76 → $76 \cdot 10 = 760$ parameters

---

## Pooling

- **Max pooling**: Outputs max value in window  
- **Average pooling**: Outputs mean of values in window

### Example
- Max pooling on:  
  $\begin{bmatrix} 6 & 8 \\ 3 & 4 \end{bmatrix} \rightarrow 8$  
- Average pooling:  
  $\begin{bmatrix} 6 & 8 \\ 3 & 4 \end{bmatrix} \rightarrow \frac{6+8+3+4}{4} = 5.25$

---

## Naive Bayes & Laplace Smoothing

- Naive Bayes assumes features $F_1, F_2, \dots, F_n$ are conditionally independent given class $Y$
- Laplace smoothing: add 1 to each count to avoid zero probability  
  $P(x_i \mid y) = \frac{\text{count}(x_i, y) + 1}{\text{count}(y) + k}$

---

## Activation Functions (Identification)
Not valid: **Laplacian**  
Valid: ReLU, Sigmoid, Tanh

---

## Supervised vs. Unsupervised
- **Supervised**: Learn from labeled data (e.g., regression, classification)  
- **Unsupervised**: No labels; e.g., clustering or dimensionality reduction

---

## RNN Key Facts
- Used for **sequential data**  
- Suffer from **exploding gradients** (clip them), and **vanishing gradients**
- Can handle variable-length sequences

---

## Convolution Filters

### Sobel Filters
- X (vertical edges):  
  $\begin{bmatrix} -1 & 0 & 1 \\ -2 & 0 & 2 \\ -1 & 0 & 1 \end{bmatrix}$  
- Y (horizontal edges):  
  $\begin{bmatrix} -1 & -2 & -1 \\ 0 & 0 & 0 \\ 1 & 2 & 1 \end{bmatrix}$

### Prewitt Filters
- X:  
  $\begin{bmatrix} -1 & 0 & 1 \\ -1 & 0 & 1 \\ -1 & 0 & 1 \end{bmatrix}$  
- Y:  
  $\begin{bmatrix} -1 & -1 & -1 \\ 0 & 0 & 0 \\ 1 & 1 & 1 \end{bmatrix}$

---

## Early Stopping (Diagram Key)
1. Vertical axis = Loss  
2. Horizontal axis = Epochs  
3. Minimum validation loss  
4. Optimal epoch  
5. Validation curve  
6. Training curve

---

## Image Filter Construction
- To detect a 3×3 red cross in RGB image:  
  Design a filter like:
  - Red channel: $\begin{bmatrix} 0 & 1 & 0 \\ 1 & 1 & 1 \\ 0 & 1 & 0 \end{bmatrix}$  
  - Green/Blue: all zeros

---

## LeNet-5 Specifics
- Input: $32 \times 32$  
- Layer S2: 6 maps, $14 \times 14$  
- Layer C3: 16 maps, $10 \times 10$  
- Each filter: $5 \times 5 \times 6 = 150$ weights + 1 bias  
- Total params in C3: $151 \cdot 16 = 2416$

---

## Gini Index
$G = 1 - \sum_{i=1}^{k} p_i^2$  
Weighted Gini of split:
$G_{\text{split}} = \sum_{j} \frac{n_j}{n_{\text{total}}} G_j$

---

## Max Pooling: Interpretive Insight

- **(i)** Max pooling increases receptive field — ✅ True  
  Max pooling reduces spatial resolution, so neurons in deeper layers see a larger portion of the input. This increases the **effective receptive field** of subsequent layers.

- **(ii)** Max pooling does not increase parameter count — ✅ True  
  Max pooling is a **parameter-free** operation. It performs fixed aggregation (e.g., max, avg) over regions and introduces **no learnable weights**.

- **(iii)** Max pooling decreases positional sensitivity — ❌ False  
  Max pooling actually **reduces positional precision**, not sensitivity. It introduces **translation invariance**, meaning small shifts in input may not affect the output, but this makes the network **less sensitive to exact positions**, not more.

→ **Correct conclusion:** Statements **(i)** and **(ii)** are true. Statement **(iii)** is false.

---

## Overfitting Diagnosis
- If training error = 0 and test error is high → **overfit**
- Solution: **increase regularization**, **early stopping**, or **simpler model**

---

## Miscellaneous

- CNNs process **local regions**; FCNNs use **global input**
- Early stopping uses validation loss to halt training before overfit
- Data augmentation ≠ adding metadata (e.g., photo date)
- Data cleansing ≠ adding polynomial features
---
---
---


## RNN Example: Step-by-Step and Logic Behavior

### 🔁 Standard RNN: Numerical Computation

- Hidden update: $h_t = \tanh(w_1 x_t + w_2 h_{t-1} + b_h)$  
- Output: $y_t = w_3 h_t + b_3$

Let:  
$w_1 = 1$, $w_2 = 1$, $b_h = 0$  
$w_3 = 2$, $b_3 = 0$  
Initial: $h_0 = 0$, input $x_1 = 1,\ x_2 = 0$

**Step 1:**  
$h_1 = \tanh(1 + 0) = \tanh(1) \approx 0.761$  
$y_1 = 2 \cdot 0.761 \approx 1.522$

**Step 2:**  
$h_2 = \tanh(0 + 0.761) \approx 0.642$  
$y_2 = 2 \cdot 0.642 \approx 1.284$

---

### ✅ Logic RNN: "Output 1 until input is 0, then output 0 forever"

Use binary state & threshold activation:  
$f(z) = \begin{cases} 1 & z \geq 0 \\ 0 & z < 0 \end{cases}$

- Hidden: $h_t = f(w_1 x_t + w_2 h_{t-1} + b_h)$  
- Output: $y_t = h_t$ (direct passthrough)

Let:  
$w_1 = -1$, $w_2 = 1$, $b_h = 0.5$

**Behavior:**
- Initially $h = 0$  
- If $x = 1$: $h \to 1$, stays 1  
- If $x = 0$: $h \to 0$, stays 0  
- Output $y_t = h_t$

**Example input:** $[1, 1, 0, 1]$ → Output: $[1, 1, 0, 0]$

---
