# Logistic Regression

Logistic Regression is a statistical method used for binary classification tasks, where the goal is to predict the probability that an instance belongs to one of two possible classes. Despite its name, logistic regression is a classification algorithm, not a regression algorithm used for continuous target variables.

The basic idea behind logistic regression is to model the relationship between the input features (independent variables) and the probability of an instance belonging to a specific class (dependent variable) using a logistic function, also known as the sigmoid function.

The sigmoid function is defined as:

$\sigma(z) = {1 \over 1+e^{(-z)}}$

Where \( z \) is the linear combination of the input features and their corresponding weights, plus a bias term. Mathematically, it can be represented as:

$z = β_0 + β_1x_1 + β_2 +  ... + β_nx_n $

Here, $β_0$ is the bias term (also called the intercept), $β_1$, $β_2$ ..., $β_n$  are the coefficients (weights) associated with each input feature $( x_1, x_2, \ldots, x_n )$, respectively.

The sigmoid function maps the output \( z \) to a value between 0 and 1, which represents the probability that an instance belongs to the positive class (class 1). If the probability is greater than or equal to 0.5, the instance is classified as belonging to class 1; otherwise, it is classified as belonging to class 0 (negative class).

The logistic regression model is trained by finding the optimal values for the coefficients $β_1$, $β_2$ ..., $β_n$ that maximize the likelihood of the observed data. This process is usually done through optimization algorithms such as gradient descent.

One of the main advantages of logistic regression is its simplicity and interpretability. It is widely used in various fields, such as medicine, social sciences, finance, and machine learning, for tasks involving binary classification, like spam detection, disease diagnosis, or customer churn prediction.

It is essential to note that logistic regression assumes a linear relationship between the input features and the log-odds of the positive class. If the decision boundary is not linear, other classification algorithms like Support Vector Machines (SVM) or Decision Trees may be more appropriate.

## Important Notes
1. There are 3 ways.
    - Geometric way [+1, -1]
    - Probabilistic way [0, 1]
    - Loss-Minimization
2. Best used for Binary classification.
3. $y = wx + c$<br>
    $y = w_0 + w_1x_1 + w_2 +  ... + w_nx_n $ <br>
    $f(x) = w^Tx$<br>
4. Assumption - Data is linearly seperable
5. w_0 is 0 because plane is passing through origin.
5. Geometric Intuition:
    - $ y_iw^Tx_i > 0 => correctly\ classfied$
    - $ y_iw^Tx_i < 0 => incorrectly\ classified$
6. Mathematical Objective Function<br>
    $MOF = argmax(y_iw^Txi)$<br>
    $MOF = \sum_{i=1}^n y_iw^Tx_i$<br>
    Very sensitive to Outliers.
7. Sigmoid Function:<br>
    - Probabilistic manner
    - Squash between 0 and 1
    - Robust to outlier<br>
    $\sigma(y_iw^Tx_i) = {1 \over 1+e^{(-y_iw^Tx_i)}} $<br>
    $\sigma(z) = {1 \over 1+e^{(-z)}} $<br>
    $MOF = argmax(\sigma(y_iw^Tx_i))$<br>
    $MOF = argmax({1 \over 1+e^{(-y_iw^Tx_i)}} )$<br>
    $MOF = argmax(log({1 \over 1+e^{(-y_iw^Tx_i)}}))$<br>
    $MOF = argmax(-log(1+e^{(-y_iw^Tx_i)}))$<br>
    $MOF = argmin(log((1+e^{(-y_iw^Tx_i)})))$<br>
    $MOF = argmin(log(1) + log(e^{(-y_iw^Tx_i)}))$<br>
    $MOF = argmin(0 - {(-y_iw^Tx_i)})$<br>
    $MOF = argmax({y_iw^Tx_i})$<br>
8. Probabilistic Intuition:<br>
    $P = {1 \over 1 + e^{-y}}$<br>
    P is probability of something happening<br>
    $P(1+e^{-y}) = 1$<br>
    $P + e^{-y}P = 1$<br>
    $Pe^{-y} = 1-P$<br>
    $e^{-y} = {1-P\over P}$<br>
    Take ln on both sides<br>
    $ln(e^{-y}) = {ln({P\over 1-P})}$<br>
    $y = ln({P\over 1-P})$<br>
    Logit function => $y = ln(P) - ln(1-P)$<br>
9. LogLoss => $y_iP(y_i) - (1-y_i)P(1-y_i)$<br>
    P(1,0)<br>
10. Loss Minimization: To validate a log function<br>
    - 1 for correctly classified<br>
      0 for incorrectly classified<br>
    - discontinuity so cannot use Gradient Descent
    - Logistic loss function to minimize loss.
    - $W* = argmin(\sum_{i=1}^n log(1+e^{-yw^Tx_i}))$<br>
        Let, $zi = y_iw^Tx_i$<br>
    $W* = argmin(\sum_{i=1}^n log(1+e^{-z_i}))$<br>
11. Regularization: $\lambda$ => Hyperparameter<br>
    $W* = argmin(\sum_{i=1}^n log(1+e^{-z_i}) + \lambda W^Tw)$<br>
    - L1 or Lasso ||W||<br>
    $W* = argmin(\sum_{i=1}^n log(1+e^{-z_i}) + \lambda||W||)$<br>
    - L2 or Ridge $W^TW$ or $W_j^2$ or $||W||^2$<br>
    $W* = argmin(\sum_{i=1}^n log(1+e^{-z_i}) + \lambda||W||^2)$<br>
    - Elastinet L1 + L2<br>
    $W* = argmin(\sum_{i=1}^n log(1+e^{-z_i}) + \lambda_1||W|| + \lambda_2||W||^2)$<br>
12. Lasso
    - extract Important features
    - Can be used as feature selection.
    - Coefficient in Lasso are Laplace distributed
13. Ridge
    - Instead of going zero less important features have very low values.
    - Coefficient in Ridge are normal distributed
14. Column Standardization - Standardize columns before applying Logistic Regression.