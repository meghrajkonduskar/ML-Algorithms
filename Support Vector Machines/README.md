# Support Vector Machines
SVM stands for Support Vector Machine, and it is a popular supervised machine learning algorithm used for classification and regression tasks. It is particularly effective for problems where the data is linearly separable, meaning it can be separated into different classes by a straight line (in 2D), a plane (in 3D), or a hyperplane (in higher dimensions).

The main objective of SVM is to find the optimal hyperplane that best divides the data points into different classes while maximizing the margin between the classes. The margin is the distance between the hyperplane and the nearest data points of each class; the larger the margin, the better the generalization of the model and its ability to handle new, unseen data.

Here's a step-by-step explanation of how SVM works for a binary classification problem:

1. Data Preparation: SVM takes labeled training data, where each data point is associated with a class label (either 0 or 1 for a binary classification problem).

2. Feature Space: Each data point in the dataset is represented as a feature vector in an n-dimensional space, where n is the number of features. SVM tries to find a hyperplane that separates these data points into two classes as best as possible.

3. Linear Separability: SVM assumes that the data is linearly separable. If the data is not separable by a hyperplane in the original feature space, SVM can use the "kernel trick" to map the data into a higher-dimensional space, where it might become linearly separable.

4. Maximizing Margin: The main goal of SVM is to find the hyperplane that maximizes the margin between the closest data points of each class. These closest data points are called "support vectors," and they play a crucial role in defining the optimal hyperplane.

5. Soft Margin (C parameter): In real-world scenarios, data might not be perfectly separable due to noise or overlapping classes. SVM allows for some misclassifications by introducing a "soft margin." The C parameter controls the trade-off between maximizing the margin and allowing misclassifications. A large C value will enforce a strict margin, potentially leading to overfitting, while a small C value will allow more misclassifications, possibly leading to underfitting.

6. Classification: Once the optimal hyperplane is found, new data points can be classified based on which side of the hyperplane they lie.

7. Kernel Trick: As mentioned earlier, SVM can transform the data into a higher-dimensional space using a kernel function, which allows the algorithm to find a hyperplane that would not be linearly separable in the original feature space. Popular kernel functions include the linear kernel, polynomial kernel, radial basis function (RBF) kernel, and sigmoid kernel.

SVM is widely used in various applications, including text categorization, image classification, bioinformatics, and more. However, it is worth noting that SVM might not be the best choice for extremely large datasets due to its time complexity, which grows with the number of training examples. In such cases, other algorithms like stochastic gradient descent or neural networks might be more suitable.

## Important Notes
1. Plane to divide the data into different classes assuming data is linearly seperable.
. Create 2 hyper planes such that distance between plane and data point is maximum
3. Equation of plane:<br>
 $W^Tx + b = 0$<br>
 $\pi^+ => W^T + b = 1$<br>
 $\pi^-1 => W^T + b = -1$<br>
 Substract above equations<br>
 $W^T(x_2 - x_1) = 2$<br>
 Normalizing<br>
 ${W^T\over||w||} (x_2-x_1) = {2\over||w||}$<br>
 $(x_2 - x_1) = {2\over||w||}$
4. MOF $f(x)_{(w,b)} = argmax({2\over||w||})$<br>
For each point in negative zone<br>
$W^Tx + b < 0$<br>
For each point in positive zone<br>
$W^Tx + b > 0$<br>
Multiply by y<br>
$f(x) = y_i(W^Tx_i+b)$
5. Rephrase MOF:
$f(x)_{(w,b)} = argmax({2\over||w||})$<br>
such that $y_i(W^Tx_i+b) > 0$
6. Soft Margin SVM: To measure how far a datapoint is in opposite direction from the right plane, we introduce $\epsilon_i$<br>
$\epsilon_i = 1- y_i(w^Tx + b)$<br>
$\epsilon_i = 1- z_i$
7. MOF = $argmax_{(w,b)}{2\over||w||} + c \sum_{i=1}^n \epsilon_i$<br>
$argmin{(w,b)}{2\over||w||} + c \sum_{i=1}^n \epsilon_i$<br>
such that, $y_i(W^Tx_i+b) >= 1 - \epsilon_i$<br>
C increases, Overfitting.<br>
C decreases, Underfiiting.<br>
8. Hinge loss: $\epsilon_i = 1- z_i$<br>
    $max(0,1-z_i)$
9. Kernels:
 - Polynomial - ${(x_1^Tx_2 + c)}^d$
 - Radial basis function - $k(x_1, x_2) = exp{(-(||x_1 - x_2||)^2)\over 2\sigma^2}$<br>
 $||x_1 - x_2||^2 = distance$<br>
 $k(x_1, x_2) = e^{-d^2 \over 2\sigma^2}$<br>
 $k(x_1, x_2) = {1\over{e^{d^2 \over 2\sigma^2}}}$<br>