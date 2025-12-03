# Machine Learning Basics Interview Questions

This folder contains fundamental Machine Learning interview questions covering core concepts, algorithms, and techniques.

## Topics Covered

1. **Supervised Learning**
2. **Unsupervised Learning**
3. **Model Evaluation and Validation**
4. **Feature Engineering**
5. **Regularization**

---

## Questions

### 1. What is the difference between supervised and unsupervised learning?
**Answer:** Supervised learning uses labeled data where the target variable is known, and the model learns to map inputs to outputs. Examples include classification and regression. Unsupervised learning works with unlabeled data and aims to find hidden patterns or structures, such as clustering and dimensionality reduction.

### 2. Explain the bias-variance tradeoff.
**Answer:** Bias refers to errors from overly simplistic assumptions in the learning algorithm (underfitting). Variance refers to errors from sensitivity to fluctuations in the training data (overfitting). The tradeoff is finding the right model complexity that minimizes total error (bias² + variance + irreducible error).

### 3. What is cross-validation and why is it used?
**Answer:** Cross-validation is a technique to assess model performance by splitting data into multiple folds. K-fold cross-validation trains the model K times, each time using K-1 folds for training and 1 fold for validation. It helps prevent overfitting and provides a more reliable estimate of model performance.

### 4. What is the difference between L1 and L2 regularization?
**Answer:** L1 (Lasso) regularization adds the absolute value of coefficients to the loss function, promoting sparsity and feature selection. L2 (Ridge) regularization adds squared coefficients, shrinking weights toward zero but not to exactly zero. L1 is better for sparse solutions; L2 is better when all features are relevant.

### 5. Explain precision, recall, and F1-score.
**Answer:** 
- **Precision** = TP / (TP + FP) - measures accuracy of positive predictions
- **Recall** = TP / (TP + FN) - measures ability to find all positive instances
- **F1-score** = 2 × (Precision × Recall) / (Precision + Recall) - harmonic mean of precision and recall, useful for imbalanced datasets

### 6. What is overfitting and how can you prevent it?
**Answer:** Overfitting occurs when a model learns noise in training data rather than the underlying pattern. Prevention methods include:
- Cross-validation
- Regularization (L1, L2)
- Early stopping
- Dropout (in neural networks)
- Reducing model complexity
- Increasing training data
- Data augmentation

### 7. What are the assumptions of linear regression?
**Answer:** 
1. Linearity between features and target
2. Independence of residuals
3. Homoscedasticity (constant variance of residuals)
4. Normality of residuals
5. No multicollinearity among features

### 8. What is gradient descent and how does it work?
**Answer:** Gradient descent is an optimization algorithm that minimizes the loss function by iteratively adjusting parameters in the direction of steepest descent. Steps: calculate the gradient of the loss function, update parameters by moving in the negative gradient direction scaled by the learning rate. Variants include batch, stochastic (SGD), and mini-batch gradient descent.

### 9. What is the curse of dimensionality?
**Answer:** As the number of features increases, the data becomes sparse in high-dimensional space, making it harder for algorithms to find patterns. Distance metrics become less meaningful, and more data is required to maintain statistical significance. Solutions include dimensionality reduction (PCA, t-SNE) and feature selection.

### 10. Explain the difference between bagging and boosting.
**Answer:** 
- **Bagging** (Bootstrap Aggregating): Trains multiple models independently on random subsets of data (with replacement) and combines predictions through voting/averaging. Reduces variance. Example: Random Forest.
- **Boosting**: Trains models sequentially, with each model focusing on errors from previous ones. Reduces bias. Examples: AdaBoost, XGBoost, LightGBM.
